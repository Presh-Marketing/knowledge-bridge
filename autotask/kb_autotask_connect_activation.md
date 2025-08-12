# TD SYNNEX Digital Bridge – Autotask PSA Connector: Connecting & Activation

After you’ve gathered your Autotask API credentials (user name, secret and tracking identifier), you can connect the **Autotask** connector within the TD SYNNEX Digital Bridge portal.  The connection process establishes trust between TD SYNNEX and your Autotask instance so that data can flow automatically.

## Before you begin

* Ensure you’ve created an API‑only user in Autotask and noted the **User Name** (API key), **Secret** (password), and **tracking identifier** (*ApiIntegrationCode*).  If you haven’t done this yet, follow the steps in the prerequisites article.
* The **Email** you enter on the connection form should correspond to an active Autotask resource (often the same email used when creating the API user).  TD SYNNEX uses this to associate orders with your account.

## Step 1 – Open the Autotask connector

1. Log into the **TD SYNNEX Digital Bridge** portal.
2. In the top navigation bar, click **Connector Bridge** and then **Manage Connectors**.
3. Select **Autotask** from the list of available connectors.  If this is your first time setting up the integration, the connector status will show *Not Connected*.

## Step 2 – Provide your credentials

Click **Connect** (or **Reconnect** if you previously disconnected) to launch the authorization form.  You will see a screen similar to the following:

![Enter Autotask credentials](/public/assets/images/autotask_connect_form.png)

Fill out the form as follows:

| Field | Description |
|------|-------------|
| **Email** | The email address of the Autotask administrator or API user.  It must correspond to an active resource in your PSA. |
| **User Name** | The user name (API key) generated when you created the Autotask API user. |
| **Secret** | The secret (password) generated for the API user.  Use the eye icon to reveal or hide the value. |

Once all fields are completed, click **Connect to Autotask**.  TD SYNNEX will validate your credentials and establish the connection.

If authentication fails, confirm that the user name, secret and tracking identifier are correct and that the API user has access to the necessary modules.  Also ensure your browser allows pop‑ups, as Autotask may require zone confirmation.

## Step 3 – Review the integration templates

After a successful connection, the **Integration Templates** tab will display the available templates: **Product Sync**, **Create Orders from Autotask**, and **Get Order Status**.  Initially these templates are disabled.  You must configure and enable each one individually.

![Autotask integration templates](/public/assets/images/autotask_templates.png)

Proceed to the template-specific articles to configure product synchronization, order submission and order status sync.