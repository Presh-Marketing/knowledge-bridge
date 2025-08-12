# Template 1 – Product Sync

The **Product Sync** template automatically imports product data from TD SYNNEX into ServiceNow.  By aligning SKU, cost, availability and promotional pricing, you ensure that quotes in ServiceNow always start with accurate catalogue information.  This template runs on a schedule and supports **up to 15 000 products per day**.

## Before you start

* Verify that the ServiceNow connector is connected and authorised in the Digital Bridge portal (see the Connect & Activation article).
* Make sure your integration user has access to the **Product Model** table and the custom fields created during setup.
* Determine how you want to categorise TD SYNNEX products in ServiceNow (for example, mapping hardware vs. subscriptions to specific model categories).

## Step 1 – Open product‑sync settings

On the **Integration Templates** tab, locate the **Product Sync** tile.  Click **Change Settings** to launch the configuration wizard.  The wizard guides you through mapping product categories and choosing sync options.

### Step 1a – Map product categories

The first page of the wizard allows you to map TD SYNNEX categories to your ServiceNow product‑model categories.  Use the drop‑down menus to select a category for each product type (for example, *Hardware*, *Software*, *Services*).  You can also specify a **Business Unit** to group products if your ServiceNow environment uses them.

![Map categories for product sync](/public/assets/images/product_sync_step1.png)

After mapping categories, click **Next**.

### Step 1b – Configure pricing and inventory options

On the next page, fine‑tune how pricing, cost and inventory values are handled:

* **Sync cost and inventory:** Enable this option to update ServiceNow with TD SYNNEX cost, promotional pricing and available quantities.  Disabling it will only import SKUs and descriptions.
* **Currency handling:** Choose whether to use your default currency or the currency returned by TD SYNNEX.
* **Update existing items:** Decide whether to overwrite existing ServiceNow product‑model descriptions and categories when they already exist.

![Pricing and inventory options](/public/assets/images/product_sync_step2.png)

After configuring the options, click **Save** to close the wizard and return to the template overview.

## Step 2 – Enable the template and run the initial sync

Use the toggle on the **Product Sync** tile to turn the template **On**.  The first synchronisation will begin immediately and may take some time depending on the number of SKUs.  Subsequent runs will incrementally update changed products.

You can monitor progress from the **Sync Activity Log** tab.  If errors appear, ensure that your integration user has sufficient permissions and that category mappings are correct.