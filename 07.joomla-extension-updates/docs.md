---
title: 'Joomla Extension Updates'
taxonomy:
    category:
        - docs
routes:
    aliases:
        - /setup/software-update-download-ids
---

If you develop Joomla extensions and sell them through Documents Seller, you can let customers install new releases from their own Joomla administrator area. Joomla discovers releases from the update feed you publish. When a customer installs an update, Documents Seller checks their Download ID and purchase before serving the ZIP.

## Upload and select an update package

1. In your store's Joomla administrator, go to **Documents Seller → Configuration → General** and find **Documents Path**. Make sure `zip` is included in **Allowed File Types**.
2. Using SFTP or your hosting file manager, create an `updates` subfolder inside **Documents Path**. Upload the installable update ZIP directly to that subfolder. With the default path, the ZIP goes in `documents/updates` under your Joomla site root.
3. Go to **Documents Seller → Documents** and open the document for the extension you sell. On **General Information**, select the ZIP in **Update Package** and save. **Choose File** controls what customers receive when they download from their order. When no **Update Package** is assigned, the update endpoint serves that standard file from **Documents Path**.
4. Find the document's numeric **ID** in the **Documents** list. Use this value as `document_id` in the update feed for that extension. Keep the same document when releasing new versions so existing purchases continue to qualify for updates.

If **Documents Path** is inside your site's web root, verify that your web server blocks direct requests for ZIPs in the `updates` subfolder. Customers should receive the ZIP through the Documents Seller endpoint so their purchase is checked.

Documents Seller checks for a paid order containing that document. The order must match the Joomla account that owns the Download ID, by user ID or email address. To offer updates for a set period after purchase, select **After X days** under **Prevent Download Type** and set **Number Days**. The update endpoint applies this limit from the order's payment date.

## Define the Joomla update server

### Publish the update feed

Create a publicly accessible XML file, for example `https://store.example.com/updates/example.xml`. The feed announces the release and points to the Documents Seller download endpoint. This example announces version `1.2.0` of the Joomla package `pkg_example`, sold as document `42`.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<updates>
    <update>
        <name>Example Package</name>
        <element>pkg_example</element>
        <type>package</type>
        <client>site</client>
        <version>1.2.0</version>
        <downloads>
            <downloadurl type="full" format="zip">https://store.example.com/index.php?option=com_dms&amp;task=download_update_package&amp;document_id=42</downloadurl>
        </downloads>
        <targetplatform name="joomla" version="(4\.4|5\.[0-9]+|6\.[0-9]+)" />
    </update>
</updates>
```

Replace the example store URL and document ID with your own. If your store is installed in a subdirectory, include that path before `index.php`. Keep the URL on one line and use `&amp;` for query separators in XML. Set `element`, `type`, and `client` to match the installed extension. For a package with `<packagename>example</packagename>`, the installed element is `pkg_example`. Set `version` to the version in the update ZIP's manifest and adjust `targetplatform` to the Joomla versions the release supports. See Joomla's [Update Servers documentation](https://manual.joomla.org/docs/5.4/building-extensions/install-update/update-server/) for compatibility fields and examples for other extension types.

### Register the update site in the extension manifest

Add these elements inside the root `<extension>` element of the extension's installation manifest, for example `pkg_example.xml`. Ship an installation package with this manifest so Joomla registers the update site on each customer's website. Customers running a version that predates the integration can install this package manually once to register the update site.

```xml
<updateservers>
    <server type="extension" priority="1" name="Example Package Updates">https://store.example.com/updates/example.xml</server>
</updateservers>
<dlid prefix="dlid=" />
```

The `<dlid>` element tells Joomla to show a **Download Key** field for the update site and append the saved key as `dlid` when downloading the ZIP. The Documents Seller endpoint accepts `dlid` or `download_id`. See Joomla's [Download Keys documentation](https://manual.joomla.org/docs/5.4/building-extensions/install-update/installation/manifest/#download-keys).

## Configure domain validation

Documents Seller validates domains by default. Turn it off to use Joomla's built-in Download Key without an installer plugin, or keep it enabled to limit each Download ID to one domain.

### Use Joomla's Download Key without an installer plugin

1. On the store, create `administrator/components/com_dms/view/configuration/tmpl/default_custom_settings.php` relative to the Joomla site root. If the file already exists, add the **Validate Domain** control to it alongside your existing settings.

    ```php
    <?php
    defined('_JEXEC') or die;

    $validateDomain = (int) $this->config->get('validate_domain', 1);
    ?>
    <div class="control-group">
        <div class="control-label">
            <label for="validate_domain">Validate Domain</label>
        </div>
        <div class="controls">
            <select name="validate_domain" id="validate_domain" class="form-select">
                <option value="1"<?= $validateDomain === 1 ? ' selected' : '' ?>>Yes</option>
                <option value="0"<?= $validateDomain === 0 ? ' selected' : '' ?>>No</option>
            </select>
        </div>
    </div>
    ```

2. In the Joomla administrator, go to **Documents Seller → Configuration → Custom Settings**, set **Validate Domain** to **No**, and save. This saves `validate_domain` as `0`. Keep the custom settings file in place so later configuration saves continue to submit that value.
3. On a customer site, enter the Download ID in the extension's **Download Key** field. Joomla sends the key when it requests the ZIP. With domain validation off, the same ID can be used on multiple sites. Documents Seller still checks the account's paid order and the document's update period.

### Send the customer site's domain

With domain validation enabled, Documents Seller requires a `domain` parameter and binds each Download ID to the first domain used in an eligible request. Subsequent requests with that ID must supply the same domain. Documents Seller treats `www.example.com` and `example.com` as the same domain. A customer can use the ID for multiple extensions they have bought from your store on that domain and needs a separate ID for each additional domain.

Joomla's Download Key supplies the ID. An installer plugin on the customer's site can add the site's hostname before Joomla requests the update ZIP.

1. Download the [sample installer plugin](plg_installer_dmsupdatedomain.zip) for Joomla 4.4, 5, and 6. It uses a Joomla service provider and subscribes to `onInstallerBeforePackageDownload`. See [Joomla Installer Events](https://manual.joomla.org/docs/5.4/building-extensions/plugins/plugin-events/installer/#oninstallerbeforepackagedownload).
2. Install the ZIP on a test customer site. In **System → Manage → Plugins**, open **Installer - Documents Seller Update Domain**. Enter your store's HTTPS base URL in **Store URL**, including the subdirectory if applicable, as in `https://store.example.com/shop`. Use the same base URL as the package link in your feed. Save and enable the plugin.
3. Enter the Download ID in the update site's **Download Key** field and test an update. The plugin adds `domain` to requests for that store's Documents Seller update endpoint.

To distribute the integration with your extension, adapt the sample and include it in your Joomla package. Set the `store_url` default in `dmsupdatedomain.xml` to ship it with your store URL prefilled. The plugin must be enabled on customer sites before they install updates.

## Let customers manage their Download IDs

On your store, [create a Joomla menu item](/frontend-menu-options#create-a-menu-item) of type **Documents Seller → Download Ids**. Set **Access** to **Registered** and give it a title such as **Manage Download IDs**. When a signed-in customer with a paid order opens the page, Documents Seller creates an ID if their account has none. Customers can generate up to five more IDs at a time with **Process**. If the store uses domain validation, the page shows the domain associated with each ID after use.

Under **Documents Seller → Messages**, use **Download IDs Manage Message** to display these steps on that page for your customers.

1. Sign in to the store, open **Manage Download IDs**, and copy a Download ID. If the store uses domain validation, use the ID assigned to that site or generate a new ID for a new domain.
2. In the Joomla administrator of that website, go to **System → Update → Update Sites**. Open the update site for the extension, paste the ID into **Download Key**, and save.
3. Go to **System → Update → Extensions**. Click **Check For Updates**, select the extension when a new release is available, and click **Update**.

Store administrators can look up IDs under **Documents Seller → Download IDs** by ID, domain, or Joomla username.

## Publish and test a new release

1. Upload the new ZIP, select it in **Update Package** for the same document, and save. If you also want customers to receive the new ZIP when they download from an order, update **Choose File** separately.
2. Publish the new version in the XML feed. The `document_id` stays the same when the new ZIP replaces the previous update package for that document.
3. On a test Joomla site, install an older version of the extension with the update site registered. If you enabled domain validation, enable your installer plugin. Use a Download ID from a store account with a paid order for the extension. Check that Joomla finds the new release and installs it. To test purchase checks, start from the older version again and use an ID from an account that has a paid order for a different product. Verify that the update download is denied.

If Joomla shows the release but cannot download it, check the saved Download Key, the customer's purchase and update period, and the selected ZIP on the store. When domain validation is enabled, also check the installer plugin and the domain associated with the ID. If Joomla does not list the release, check the feed URL, installed extension identifiers, release version, and compatibility requirements in the XML.
