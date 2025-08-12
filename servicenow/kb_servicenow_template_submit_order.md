# Template 2 – Create Orders from ServiceNow (Submit Order)

The **Create Orders from ServiceNow** template (often labelled **Submit Order**) automatically converts ServiceNow purchase orders into TD SYNNEX sales orders.  This automation eliminates manual re‑keying and accelerates order fulfilment.  Orders are triggered when the **Tds Order status** is set to *Send to TDS*.

## Before you start

* Confirm that the **Product Sync** template is enabled and has completed its initial synchronisation.  Order submission relies on SKUs existing in ServiceNow.
* Make sure your users understand which requests should be converted into purchase orders.  Only purchase orders with a *Send to TDS* status are submitted.
* The integration user must have permission to create, read and update purchase orders and purchase‑order line items.

## Step 1 – Create a purchase order in ServiceNow

1. In ServiceNow, navigate to **All → Procurement → Purchase Orders** and click **New**.
2. Fill in the purchase‑order header information.  Set **Vendor** to **TD SYNNEX**, choose the shipping location, and optionally enter a description.  Save the record.
3. Add one or more products to the purchase order using the **Purchase Order Line Items** related list.

![Create a purchase order](/public/assets/images/submit_order_step1.png)

## Step 2 – Submit the order to TD SYNNEX

1. Change the **Tds Order status** field on the purchase order to **Send to TDS**.  This indicates that the order is ready for submission.
2. The connector listens for this status change, sends the purchase order to TD SYNNEX via API and creates a **Customer Purchase Order (CPO)** record in the TD SYNNEX system.
3. Once TD SYNNEX receives the order, the connector updates the **Tds Cpo Id** field on the purchase order with the distributor’s order number.

Orders will only be submitted when the status flips to *Send to TDS*.  Draft or on‑hold purchase orders are ignored.

## Step 3 – Enable the template

In the Digital Bridge portal, return to the **Integration Templates** tab.  Locate the **Create Orders from ServiceNow** tile and use the toggle to turn the template **On**.  When enabled:

1. The connector monitors ServiceNow for purchase orders where **Tds Order status** = *Send to TDS*.
2. When such a purchase order is detected, it is converted into a TD SYNNEX sales order automatically.
3. Submission events appear in the **Sync Activity Log** along with any errors.

## Tips for successful order submission

* Ensure that all line items on the purchase order have been synchronised via the Product Sync template.  If a SKU has not been synced, the order will fail.
* Only approved purchase orders (status *Send to TDS*) are sent.  Orders in *Draft*, *On Hold* or other statuses are ignored.
* If you temporarily disable automatic submission, your team can set the status and then use a scheduled job or manual trigger to send orders in batches.