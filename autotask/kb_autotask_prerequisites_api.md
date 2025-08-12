# TD SYNNEX Digital Bridge – Autotask PSA Connector: Prerequisites & API Setup

## Purpose and Features

The **Autotask PSA connector** for TD SYNNEX Digital Bridge allows partners to embed live catalog data, automate purchase orders, and track the full order lifecycle within Autotask PSA—eliminating the need to switch between portals.  Once configured, the connector feeds SKU, cost, inventory and tracking data from TD SYNNEX directly into Autotask and can automatically submit purchase orders back to TD SYNNEX.

The connector includes three integration templates (Product Sync, Submit Order, and Get Order Status).  This article covers prerequisites and API configuration.  Subsequent articles outline how to activate the connector and configure each template.

![Autotask connector overview](/public/assets/images/autotask_overview.png)

### Key Features

* **Daily Catalog Sync** – Up to **20 000 SKUs** are synced with cost, availability and promotions each day.  Your quotes always start with the right numbers.
* **Flexible Order Automation** – Purchase orders can be triggered manually, on a schedule or via a custom workflow, converting Autotask opportunities into TD SYNNEX orders in a single click.
* **Order Status & Tracking Sync** – Processing, shipped, partial and back‑order states (including tracking numbers) write back to the original purchase‑order lines in Autotask.
* **Error Logging & Retry** – Detailed logs plus automatic retries help to gracefully handle transient API errors.

### Data Flow

**TD SYNNEX → Autotask PSA**

* Product catalog (SKU, description, specifications)
* Cost and promotional pricing
* Inventory levels
* Order status and tracking numbers
* Invoice and CPO (customer purchase order) references

**Autotask PSA → TD SYNNEX**

* Purchase Orders
* Purchase Order Line Items

## Prerequisites

### TD SYNNEX Requirements

* You must be an authorized TD SYNNEX partner with access to the Digital Bridge portal and have the **Autotask** connector enabled under Connector Bridge.
* Ensure that your organization has the appropriate permissions to create and manage integrations.

### Autotask Requirements

* **API‑only user:**  Autotask’s REST API can only be accessed using a dedicated API user with the **API User (API‑only)** security level.  This role provides full system administrator access to modules and data via the API but **cannot log into the UI**.  There is no per‑seat charge for API‑only users and there is no limit to the number you may create.
* **Tracking identifier:**  Every API‑only user must have a **tracking identifier** (also called the *ApiIntegrationCode*) assigned.  The identifier distinguishes between integrations and is required for all requests.
* **API credentials:**  During setup you must generate a **user name** and **secret** (API password).  These credentials are used in the HTTP headers to authenticate requests.
* **Permissions & line‑of‑business assignments:**  Ensure that the API user has appropriate access to Products, Purchase Orders, Inventory and other modules needed by your integration.  Without proper line‑of‑business assignments, API calls may return no results.

## Create an Autotask API User

Follow these steps to create an API account and obtain the credentials required by the connector:

1. **Log in as an administrator.**  Only administrators can create API users in Autotask.
2. Navigate to **Admin → Resources/Users** (or **Integration Center → Add API User** depending on your version).  Click **New API User**.
3. In the **General** section, enter a first name, last name and email address.  Select **API User (API‑only)** for the security level.  This role allows full API access while preventing the user from logging into the application.
4. On the **Security** tab, assign a **tracking identifier**.  Choose the vendor identifier for TD SYNNEX if available or create a custom (internal) integration identifier.
5. Generate the credentials:
   * Click **Generate Key** (may be labelled *User Name*).  This produces the API user’s unique user name.
   * Click **Generate Secret** to create a password.  Copy the **User Name** and **Secret** to a secure location; they will not be shown again.
6. Save the API user.  Make sure the user is **active** and associated with the correct line of business.  An API user with restricted module access may receive no response to a valid API call.

### Recommended permissions

The **API User (API‑only)** security level provides full access to all Autotask modules via the REST API.  While you can restrict this level, the connector requires at least the following permissions to operate.  If you choose to customise the security level, ensure the API user retains these rights:

| Module / Feature | Access required | Used by | Purpose |
|-----------------|-----------------|---------|---------|
| **Product Catalogue** | **Read** | Product Sync | Allows the connector to create and update products in Autotask. |
| **Inventory** | **Read** | Product Sync | Required to write available quantities and cost/promotional pricing. |
| **Purchase Orders** | **Create, Read, Update** | Submit Order & Get Order Status | Enables the connector to generate POs and update their status in Autotask. |
| **Purchase Order Line Items** | **Create, Read, Update** | Submit Order & Get Order Status | Used to add line items when submitting orders and to update tracking and shipping details. |
| **Companies / Contacts** | **Read** | Submit Order | Needed to assign billing and shipping contacts to orders. |
| **User-Defined Fields** (if used) | **Update** | All | Allows writing to custom fields for status or tracking numbers. |

Using the built‑in **API User (API‑only)** level is the simplest option because it grants the necessary permissions and has no per‑seat charge.  If you choose to clone and restrict the security level, verify that the above modules remain accessible or the integration may fail.

## API Authentication and Headers

Autotask’s REST API uses a simple header‑based authentication scheme.  Each request must include the following HTTP headers:

| Header | Description |
|-------|-------------|
| **ApiIntegrationCode** | Your Autotask tracking identifier (vendor or custom). |
| **UserName** | The user name of the API user you created. |
| **Secret** | The secret (password) generated for the API user. |
| **Content-Type** | `application/json` for JSON payloads. |

When constructing requests manually (for example in Postman), add these headers to every call.  The API requires TLS 1.2 encryption and does not support Single Sign‑On (SSO).

Once you have the API user name, secret and tracking identifier, proceed to the next article to connect and activate the Autotask connector within TD SYNNEX Digital Bridge.