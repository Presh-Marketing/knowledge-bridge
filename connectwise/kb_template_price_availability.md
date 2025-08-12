### TD SYNNEX Digital Bridge – ConnectWise PSA Connector  
**Get Product Price & Availability Template**

This article covers the **Get Product Price & Availability** template.  This template provides real‑time TD SYNNEX pricing and stock availability for items that you have synchronised into your ConnectWise catalog.

#### Purpose

When a TD SYNNEX product is added to an Opportunity, this template performs an on‑demand lookup to return the latest price and available quantity.  It ensures that quotes reflect current market conditions and that purchase orders are submitted only for items in stock.

#### Configuration

1. **Enable the template.** In the **Integration Templates** tab, toggle **Get Product Price & Availability** to **Active**.  Once enabled, it automatically applies to any Opportunity containing synced products.

   ![Enable Price & Availability](/public/assets/images/configure-priceavail-step1.jpeg)

2. **No further setup required.** There are no additional settings or parameters to configure.  The template is designed to work out of the box.

#### How it works

* **Daily sync with on-demand checks:** The product sync template provides daily synchronization of pricing and availability for up to 20,000 SKUs. This template allows you to trigger on-demand price/availability checks through the "TDS SYNC price" field in ConnectWise on the opportunity object, which initiates a callback to TD SYNNEX for the TD SYNNEX products associated with the opportunity.