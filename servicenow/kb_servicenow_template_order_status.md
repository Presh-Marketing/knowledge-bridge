# Template 3 – Get Order Status

The **Get Order Status** template updates ServiceNow purchase orders with the latest status and shipment information from TD SYNNEX.  Once enabled, the connector writes back processing, shipped, partial and back‑ordered states to the corresponding purchase‑order lines and populates tracking numbers and invoice references.  This closes the loop on the order lifecycle without manual entry.

## Before you start

* Ensure that the **Create Orders from ServiceNow** template is enabled and submitting orders successfully.  Order‑status updates apply only to purchase orders that have been sent via the connector.
* The integration user must have permission to update purchase orders and purchase‑order line items, as well as write to the custom status and invoice fields created during setup.

## Step 1 – Configure status mapping

In the **Integration Templates** tab, locate the **Get Order Status** tile and click **Change Settings**.  The configuration wizard lets you define how TD SYNNEX status codes map into ServiceNow fields.

### Map status fields

On the first page, specify which ServiceNow fields should receive status updates.  For example, you might map the TD SYNNEX status **TDS Released** to a custom ServiceNow field called *Vendor Status*, and map **TDS Shipped** and **TDS Partial** shipments to the purchase order’s status field.  You can choose whether partial shipments change the purchase‑order status or remain as separate notes.

![Map order status fields](/public/assets/images/order_status_step1.png)

### Configure tracking and invoice references

On the second page, select how tracking numbers, shipping dates and invoice references are written back to ServiceNow.  Typically you will map the TD SYNNEX tracking number to the **Tracking Number** field on your purchase order and choose a memo or note field for the invoice number and date.

![Configure tracking and invoice mapping](/public/assets/images/order_status_step2.png)

After completing the mappings, click **Save** to return to the template overview.

## Step 2 – Enable the template

Turn on the **Get Order Status** toggle to start synchronising status and tracking information.  The connector will periodically query TD SYNNEX for updates on open orders and write the latest status back to your ServiceNow purchase orders.  Completed or cancelled orders are not updated further.

## Notes

* Status updates typically occur shortly after TD SYNNEX processes an order but may vary depending on API load.
* Only purchase orders submitted through the connector are updated; manually created orders or orders submitted through other channels are ignored.
* If you create custom status or invoice fields in ServiceNow, ensure the integration user has permission to write to those fields.

Use the **Sync Activity Log** tab to monitor status updates and troubleshoot any issues.