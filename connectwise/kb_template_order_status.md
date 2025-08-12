### TD SYNNEX Digital Bridge – ConnectWise PSA Connector  
**Get Order Status Template**

This article focuses on the **Get Order Status** template, which polls TD SYNNEX for shipping information and updates your ConnectWise purchase orders.

#### Purpose

After you submit a purchase order to TD SYNNEX (either manually or via the Create Orders template), this template retrieves the latest shipping status and tracking information.  It updates the ConnectWise purchase order so you can see whether an order is processing, shipped or back‑ordered.

#### Configuration

1. **Enable the template.** Find **Get Order Status** in the **Integration Templates** tab and toggle it to **Active**.

   ![Enable Get Order Status](/public/assets/images/configure-orderstatus-step1.jpeg)

2. **Review activation details.** When enabling the template, review the activation panel.  It outlines the order flow, status field, fields sent and actions.  Agree to enable TD SYNNEX order integration and allow order data to be sent automatically.

   ![Order Status activation details](/public/assets/images/configure-orderstatus-step2.jpeg)

3. **Configure the Send to TDS field.** Ensure your ConnectWise purchase order form includes a boolean field **Send to TDS**.  Set this field to **true** on orders that you want the connector to monitor.

#### How it works

* **Scheduled polling.** The template uses a scheduled job to query open purchase orders with Send to TDS set to true.  It calls the TD SYNNEX API using the sales‑order number and retrieves the latest status.
* **Updating the PO.** The returned status (e.g., Processing, Shipped, Back‑ordered) and tracking numbers are written into the custom **Status** field and shipping fields on the ConnectWise purchase order.

This automation eliminates the need to manually check order status, ensuring your team has up‑to‑date delivery information within ConnectWise.