# TD SYNNEX Digital Bridge – ServiceNow Connector: Prerequisites & API Setup

## Purpose and Features

The **ServiceNow connector** for TD SYNNEX Digital Bridge allows partners to embed live catalog data, automate purchase orders and invoices, and track the full order lifecycle within ServiceNow.  By synchronising product data, purchase‑order automation, and inventory updates from TD SYNNEX into ServiceNow, the connector eliminates manual entry and keeps your records accurate.

![ServiceNow connector overview](/public/assets/images/servicenow_overview.png)

### Key Features

* **Daily Product Sync** – Setup once and get daily updates on new SKUs, cost and available inventory mapped to ServiceNow products.  The sync handles up to **15 000 products** per day.
* **Automated Order Submission** – When a purchase order’s status is set to *Send to TDS*, the connector automatically sends it to TD SYNNEX and records the distributor order number.
* **Status, Tracking & Invoice Sync** – Adaptive polling updates purchase‑order lines with shipping status, tracking numbers, partial shipments and PDF invoices.
* **Lifecycle Visibility** – Shipment, partial fill, back‑order, invoice and tracking number updates flow back into the same ServiceNow record.
* **Error Logging & Retry** – Detailed logs plus automatic retries help gracefully handle transient API errors.

### Data Flow

**TD SYNNEX → ServiceNow**

* Product catalog (SKU, description, specifications)
* Cost and promotional pricing
* Inventory quantities
* Order status and tracking numbers
* Invoice number and date

**ServiceNow → TD SYNNEX**

* Purchase Orders
* Purchase‑order line items (products and quantities)

## Prerequisites

### TD SYNNEX Requirements

* You must be an authorised TD SYNNEX partner with access to the Digital Bridge portal and have the **ServiceNow** connector enabled under **Connector Bridge**.
* Ensure that your organisation has the appropriate permissions to create and manage integrations.

### ServiceNow Requirements

* **ServiceNow Instance:** You need an active ServiceNow instance with administrative access.  The connector writes to custom tables and fields, so ensure you have rights to create tables, fields and business rules.
* **Integration User:** Create a dedicated integration user for TD SYNNEX.  Assign the following roles:

  | Role / Scope | Purpose |
  |-------------|---------|
  | `x_tds.db_connector` (custom) | Provides access to the custom TD SYNNEX tables for product, purchase orders and invoices. |
  | `import_transformer` | Allows the user to import data sets and run transformations (used by Product Sync). |
  | `rest_api_explorer` | Grants access to the REST API Explorer for testing and troubleshooting API calls. |
  | `asset` (read/write) | Enables updates to Configuration Management (CMDB) items created by Product Sync. |
  | `procurement_user` | Allows creation and modification of purchase orders and purchase‑order line items. |

* **Activate Required Plugins:** Make sure the **Import Set** and **OAuth 2.0** plugins are enabled in your instance.  The connector uses import sets for product data and OAuth for authentication.
* **Create Initial Objects:** After enabling the ServiceNow connector in Digital Bridge, the workflow automatically creates the following in ServiceNow:

  - A **company** named *TD SYNNEX* of type *Vendor*.
  - Business rules that trigger when a purchase order is sent to or received from TD SYNNEX.
  - Custom fields on the product model table (`TdsQty`, `TdsNetPrice`, `TdsSugRetailPrice`, `TdsWeight`) and purchase‑order table (`TdsCpoId`, `TdsOrderStatus`).
  - Custom **purchase‑order statuses** including *Send to TDS*, *TDS Received*, *TDS Accepted*, *TDS Released*, *TDS Shipped*, *TDS Invoiced* and *TDS Closed*.
  - A **TDS Invoice** custom table with fields for invoice number, type, reseller number, total, purchase‑order number and ship‑to information.

## API Authentication and OAuth Setup

The connector authenticates to ServiceNow using OAuth 2.0.  To generate the credentials:

1. In your ServiceNow instance, navigate to **All → System OAuth → Application Registry**.
2. Click **New** to create a new application registry.
3. Select **Create an OAuth API endpoint for external clients**.
4. Give the registry a meaningful name (for example, “TD SYNNEX”) and leave the **Client Secret** field blank.  Click **Submit**.
5. Open the newly created entry.  Copy the **Client ID** and reveal the **Client Secret** by clicking the padlock icon.  Store these values securely – you will need them in the next step.
6. Determine your **Instance ID**.  This is the hostname of your ServiceNow instance (for example, `mycompany.service-now.com` → `mycompany`).

The **Instance ID**, **Client ID** and **Client Secret** will be required when connecting the connector.

Proceed to the next article to connect and activate the ServiceNow connector within TD SYNNEX Digital Bridge.