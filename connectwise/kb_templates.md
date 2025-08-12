### TD SYNNEX Digital Bridge – ConnectWise PSA Connector  
**Article 3: Configuring Integration Templates**

The ConnectWise PSA connector includes four pre‑built templates.  Each template automates a specific part of the Quote → PO → Order status workflow.  This article explains what each template does and how to configure it.

#### Template overview

| Template                      | Purpose / what it does                                                                                                                      | Key configuration steps |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|
| **Product Sync**   | Synchronises TD SYNNEX products into your ConnectWise product catalog (up to 20,000 SKUs).  Useful for building a vendor catalog with official TD SYNNEX SKUs. | – Choose product categories or vendors to filter SKUs.  \\– Schedule a daily sync to keep your catalog up to date.  \\– To load >20,000 SKUs, request a price file template from TD SYNNEX. |
| **Get Product Price & Availability** | Provides real‑time pricing and stock availability when you add TD SYNNEX SKUs to an Opportunity.  | – Applies automatically to any Opportunity containing synced products.  \\– No additional configuration once the template is activated.  \\– Pricing is checked in real time when adding products and immediately before PO submission. |
| **Create Orders from ConnectWise** | Converts an approved Sales Order into a TD SYNNEX purchase order and submits it to TD SYNNEX. | – The workflow runs automatically every **30 minutes**.  \\– After submission, the connector populates order number, ship date and tracking information on the ConnectWise PO. |
| **Get Order Status**          | Polls TD SYNNEX for shipping status and updates the ConnectWise purchase order. | – Requires a boolean field **Send to TDS** on the PO; set manually or via automation.  \\– Uses product mappings from the Opportunity to submit the order. |


#### 1  Product Sync

This template synchronises products from TD SYNNEX into your ConnectWise product catalog.  You can select categories such as cell phones, consumer electronics or compute accessories, and the system will import the corresponding SKUs.  A daily schedule keeps the catalog in sync, and a price‑file import is available for larger sets.

The following images show the **Product Sync** template. The first card enables the product sync template, and the second panel lets you choose product categories.

![Enable Product Sync](/public/assets/images/configure-productsync-step1.jpeg)

![Select product categories](/public/assets/images/configure-productsync-step2.jpeg)

#### 2  Get Product Price & Availability

When you add a TD SYNNEX product to an Opportunity, this template calls TD SYNNEX in real time to obtain current pricing and inventory.  There is no additional configuration beyond activation; the template automatically triggers on any Opportunity containing a synced product.  Pricing is re‑checked immediately before order submission to ensure the PO is valid.

![Enable Price & Availability](/public/assets/images/configure-priceavail-step1.jpeg)

#### 3  Create Orders from ConnectWise

After an Opportunity is marked **Won** in ConnectWise, a Sales Order (SO) is created.  This template watches for new SOs and, every 30 minutes, converts them into TD SYNNEX purchase orders.  Once enabled, no further configuration is required; the integration writes the TD SYNNEX sales‑order number, shipping date and tracking information back to the ConnectWise PO.

Below are the card panels for the remaining templates.  The first image shows the **Create Orders from ConnectWise** template toggle, and the second and third images show the **Get Order Status** template and its activation panel.

![Enable Create Orders](/public/assets/images/configure-createorder-step1.jpeg)

![Enable Get Order Status](/public/assets/images/configure-orderstatus-step1.jpeg)

![Order Status activation details](/public/assets/images/configure-orderstatus-step2.jpeg)

#### 4  Get Order Status

For purchase orders already submitted to TD SYNNEX, this template regularly polls for updates.  It looks up orders marked with the custom boolean field **Send to TDS**, then calls the TD SYNNEX API to retrieve shipping status.  The returned status (e.g., “Processing”, “Shipped”) and tracking details are written into the PO record.  To use this template, create the **Send to TDS** custom field and set it to **true** on any PO you want monitored.

##### Next steps

After configuring the desired templates, proceed to [Article 4: Managing & Troubleshooting](./kb_management_troubleshooting.md) to learn how to monitor the integration and resolve errors.

For detailed instructions on each template, refer to the dedicated articles:

* [Product Sync Template](./kb_template_products.md)
* [Get Product Price & Availability Template](./kb_template_price_availability.md)
* [Create Orders from ConnectWise Template](./kb_template_create_orders.md)
* [Get Order Status Template](./kb_template_order_status.md)