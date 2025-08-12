### TD SYNNEX Digital Bridge – ConnectWise PSA Connector  
**Create Orders Template**

This article describes the **Create Orders from ConnectWise** template.  Use this template to automate the submission of approved Sales Orders to TD SYNNEX.

#### Purpose

When an Opportunity is marked **Won** and a Sales Order (SO) is generated in ConnectWise, this template automatically converts the SO into a TD SYNNEX purchase order and submits it.  It eliminates manual order entry and ensures order details (such as items, quantities and pricing) are transmitted accurately.

#### Configuration

1. **Enable the template.** In the **Integration Templates** tab, locate **Create Orders from ConnectWise** and toggle it to **Active**.

   ![Enable Create Orders](/public/assets/images/configure-createorder-step1.jpeg)

2. **No additional settings.** Once enabled, the workflow runs automatically every 30 minutes.  There are no custom fields or filters to configure for this template.

#### How it works

* **Automatic polling.** Every 30 minutes the connector checks for new Sales Orders marked “Won” in ConnectWise.  If found, it converts them into TD SYNNEX purchase orders.
* **Order submission.** The connector calls the TD SYNNEX API to submit the order; TD SYNNEX returns a sales‑order number and acknowledgement.
* **Updates back to ConnectWise.** After submission, the template writes back information such as order number, ship date and tracking details to the ConnectWise purchase order.

Because the workflow is fully automated once enabled, you simply monitor the **Sync Activity Log** and PO records for updates.