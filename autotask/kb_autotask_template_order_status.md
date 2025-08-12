# Template 3 – Get Order Status

The **Get Order Status** template updates Autotask purchase orders with the latest status and shipment information from TD SYNNEX.  Once enabled, the connector writes back processing, shipped, partial and back‑ordered states to the corresponding PO lines and populates tracking numbers and invoice references.  This closes the loop on the order‑lifecycle without manual entry.

## Before you start

* Ensure that the **Create Orders from Autotask** template is enabled and submitting orders successfully.  Order status updates apply only to POs that have been submitted via the connector.
* The API user must have permission to update purchase orders and purchase order line items.

## Step 1 – Configure status mapping

In the **Integration Templates** tab, locate the **Get Order Status** tile and click **Learn More** or **Change Settings**.  The configuration wizard lets you define how status codes and tracking information are mapped into Autotask.

### Map status fields

In the first step, specify which Autotask fields should receive status updates.  For example, you might map the TD SYNNEX status **Processing** to a custom Autotask field called *Vendor Status*, and map the **Shipped** and **Partial** states to status values on the purchase order.  You can also choose whether partial shipments update the purchase order’s status or remain as separate notes.

![Map order status fields](/public/assets/images/order_status_step1.jpeg)

### Configure tracking and invoice references

In the second step, select how tracking numbers, shipping dates and invoice references are written back to Autotask.  Typically you will map the TD SYNNEX tracking number to the **Tracking Number** field on your purchase order and choose a memo or note field for the invoice number.  If your workflow uses custom fields, map them accordingly.

![Configure tracking and invoice mapping](/public/assets/images/order_status_step2.jpeg)

After completing the mappings, click **Save** to return to the template overview.

## Step 2 – Enable the template

Turn on the **Get Order Status** toggle to start syncing status and tracking information.  The connector will periodically query TD SYNNEX for updates on open orders and write the latest status back to your Autotask POs.  Completed or cancelled orders are not updated further.

## Notes

* Status updates typically occur within a few minutes of TD SYNNEX processing an order but may vary depending on API load.
* Only purchase orders submitted through the connector are updated; manual orders or orders submitted through other channels are ignored.
* If you create custom status fields in Autotask, ensure the API user has permission to write to those fields.

Use the **Sync Activity Log** tab to monitor status updates and troubleshoot any issues.