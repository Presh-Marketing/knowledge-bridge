### TD SYNNEX Digital Bridge – ConnectWise PSA Connector  
**Product Sync Template**

This article focuses on the **Product Sync** template, one of the pre‑built integrations available after connecting the TD SYNNEX Digital Bridge connector to ConnectWise PSA.  Use this template to populate your ConnectWise product catalog with up‑to‑date SKUs from TD SYNNEX.

#### Purpose

The **Product Sync** template synchronises items from the TD SYNNEX catalog into your ConnectWise environment.  A synchronised catalog allows quoting and ordering directly from ConnectWise using official TD SYNNEX SKUs and descriptions.

#### Configuration

1. **Enable the template.** In the **Integration Templates** tab of Connector Bridge, locate **Product Sync** and toggle it to **Active**.  A green switch indicates the template is enabled.  
   
   ![Enable Product Sync](/public/assets/images/configure-productsync-step1.jpeg)

2. **Select product categories.** Click **Change Settings** to choose which categories or vendors to sync.  Use the category tree to select up to 20,000 SKUs and refine the import by vendor or product type.  
   
   ![Select product categories](/public/assets/images/configure-productsync-step2.jpeg)

3. **Schedule a daily sync.** The template automatically schedules a daily job to update your catalog.  You can also initiate a manual sync from the Sync Activity Log if needed.

4. **Import larger sets (optional).** If you need to import more than 20,000 SKUs, request a price‑file template from TD SYNNEX.  Upload the completed file through the connector support team to bulk‑load additional products.

#### How it works

After activation, the template calls the TD SYNNEX API to retrieve product details and creates or updates matching catalog items in ConnectWise.  During each sync it:

* Compares existing ConnectWise products to the TD SYNNEX catalog and updates descriptions and pricing.
* Adds new items for selected categories and vendors.
* Maintains the link between your internal product records and TD SYNNEX SKUs to support other templates (e.g., price lookups and order submissions).

Once the initial import completes, daily synchronisations keep your catalog current with minimal effort.