# TD SYNNEX Digital Bridge – ServiceNow Connector: Connecting & Activation

After gathering your ServiceNow credentials (**Instance ID**, **Client ID** and **Client Secret**), you can connect the **ServiceNow** connector within the TD SYNNEX Digital Bridge portal.  This process establishes trust between TD SYNNEX and your ServiceNow instance so that data can flow automatically.

## Before you begin

* Ensure you’ve created the OAuth API endpoint in ServiceNow and noted the **Instance ID**, **Client ID** and **Client Secret**.  If you haven’t done this yet, follow the steps in the prerequisites article.
* The **Email** you enter on the connection form should correspond to an active ServiceNow user (often the same account used when creating the integration user).  TD SYNNEX uses this to associate orders with your account.

## Step 1 – Open the ServiceNow connector

1. Log into the **TD SYNNEX Digital Bridge** portal.
2. From the top navigation bar, select **Connector Bridge** → **Manage Connectors**.
3. Choose **ServiceNow** from the list of available connectors.  If this is your first time configuring the integration, the connector status will show *Not Connected*.

## Step 2 – Provide your credentials

Click **Connect** (or **Reconnect** if you previously disconnected) to open the authorization form.  You will see a screen like the following:

![Enter ServiceNow credentials](/public/assets/images/servicenow_connect_form.png)

Fill out the form as follows:

| Field | Description |
|------|-------------|
| **Instance ID** | The short name of your ServiceNow instance (for example, `mycompany` if your URL is `https://mycompany.service-now.com`). |
| **Client ID** | The Client ID generated when you created the OAuth API endpoint. |
| **Client Secret** | The Client Secret associated with the OAuth endpoint.  Use the eye icon to reveal or hide the value. |

After entering all values, click **Connect to ServiceNow**.  TD SYNNEX will verify your credentials and establish the connection.  If authentication fails, double‑check your Instance ID, Client ID and Client Secret and ensure that the integration user has the roles outlined in the prerequisites article.

## Step 3 – Review the integration templates

Once connected, the **Integration Templates** tab displays the available templates: **Product Sync**, **Create Orders from ServiceNow** and **Get Order Status**.  Initially these templates are disabled.  You must configure and enable each one individually.

Proceed to the template‑specific articles to set up product synchronisation, order submission and order‑status updates.