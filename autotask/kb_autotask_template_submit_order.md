# Template 2 – Create Orders from Autotask (Submit Order)

The **Create Orders from Autotask** template (often labelled **Submit Order**) automatically converts Autotask purchase orders into TD SYNNEX sales orders.  This automation eliminates re‑keying and accelerates order fulfilment.  You can trigger orders manually or on a recurring schedule.

## Before you start

* Confirm that the **Product Sync** template is enabled and has completed its initial synchronization.  Order submission relies on SKUs existing in Autotask.
* Ensure that your Autotask users know which opportunities or quotes should be converted into purchase orders.  Only purchase orders (POs) are sent to TD SYNNEX.
* The API user must have permission to read and update purchase orders and order line items.

## Step 1 – Open the order submission settings

From the **Integration Templates** tab, locate the **Create Orders from Autotask** tile and click **Learn More** or **Change Settings** (depending on your UI version).  This opens the configuration wizard.

### Configure default order options

On the first page, choose default settings for all outgoing orders:

* **Billing & shipping contacts:**  Select which Autotask resource or contact should appear as the billing and shipping contact on TD SYNNEX orders.  You can choose *Use company default* or a specific contact.
* **Payment terms:**  Choose the default payment terms (for example, *Net 30*).  This should match the terms you have negotiated with TD SYNNEX.
* **Manual vs. automatic submission:**  Decide whether orders will be sent automatically when a purchase order is created, or if you prefer to review and submit orders manually on a schedule.

![Configure order submission options](/public/assets/images/submit_order_step1.jpeg)

After configuring these options, click **Next** (or **Save**) to return to the template overview.

## Step 2 – Enable the template

Once configuration is complete, use the toggle on the **Create Orders from Autotask** tile to turn the template **On**.  When enabled:

1. The connector monitors Autotask for new purchase orders that meet your criteria.
2. When a PO is detected, it converts the PO into a TD SYNNEX order and sends it to TD SYNNEX automatically or based on your schedule.
3. You will see the order submission in the **Sync Activity Log** tab along with any errors.

## Tips for successful order submission

* Only purchase orders in **an approved status** are sent.  Draft or on‑hold POs are ignored.
* Ensure that all line items on the PO have been successfully synchronized from the product catalogue.  If a SKU has not been synced, the order will fail.
* If you choose manual submission, a user with the proper permissions must click **Submit** to send the order to TD SYNNEX.  Scheduled submissions can be configured to run daily, weekly or on a custom cadence.

If you encounter errors, review the log details and verify that the API user has permission to create orders and that your TD SYNNEX account is configured for electronic ordering.