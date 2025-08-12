# Template 1 – Product Sync

The **Product Sync** template automatically imports product data from TD SYNNEX into Autotask PSA.  By aligning SKU, cost, availability and promotional pricing, you ensure that quotes in Autotask always start with accurate catalog information.  This template runs on a schedule and supports **up to 20 000 SKUs per day**, with incremental updates for changes.

## Before you start

* Verify that the Autotask connector is connected and authorized in the Digital Bridge portal (see the Connect & Activation article).
* Make sure your Autotask API user has access to Product Catalogue and Inventory modules.
* Determine how you want to categorize TD SYNNEX products in Autotask (for example, as **Hardware** and **Software** product types).

## Step 1 – Open product sync settings

On the **Integration Templates** tab, locate the **Product Sync** tile.  Click **Change Settings** to open the configuration wizard.  The wizard guides you through mapping product categories and choosing sync options.

### Step 1a – Map product categories

In the first step of the wizard, map TD SYNNEX categories to corresponding **Autotask Item Categories**.  Choose how imported products should be classified within Autotask (for example, **Materials** for hardware and **Service** for subscriptions).  You can also specify a **Business Unit** to group products if your Autotask environment uses them.

![Map categories for product sync](/public/assets/images/product_sync_step1.jpeg)

Use the drop‑down menus to select a category for each product type.  When finished, click **Next**.

### Step 1b – Configure pricing and inventory options

The second page allows you to fine‑tune how pricing, cost and inventory values are handled:

* **Sync cost and inventory:**  Enable this option to update Autotask with TD SYNNEX cost, promotional pricing and available quantities.  Disabling it will only import SKUs and descriptions.
* **Currency handling:**  Choose whether to use your default currency or the currency returned by TD SYNNEX.
* **Update existing items:**  Decide whether to overwrite existing Autotask item descriptions and categories when they already exist.

![Pricing and inventory options](/public/assets/images/product_sync_step2.jpeg)

After configuring the options, click **Save**.  The wizard will close and return you to the Integration Templates page.

## Step 2 – Enable the template and run the initial sync

Use the toggle on the **Product Sync** tile to turn the template **On**.  The first synchronization will begin immediately and may take some time depending on the number of SKUs.  Subsequent runs will incrementally update changed products.

You can monitor progress from the **Sync Activity Log** tab.  If errors appear, ensure that your Autotask API user has sufficient permissions and that category mappings are correct.