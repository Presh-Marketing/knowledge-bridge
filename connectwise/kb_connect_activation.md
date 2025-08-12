### TD SYNNEX Digital Bridge – ConnectWise PSA Connector  
**Connecting & Activating the Connector**

After preparing your credentials and API member (see Article 1), the next step is to connect and activate the TD SYNNEX connector within the **Connector Bridge** portal.

#### Connecting the app

1. **Access Connector Bridge.** Navigate to TD SYNNEX’s Connector Bridge on the web and locate the **ConnectWise PSA** connector.
2. **Click Connect.** Press **Connect** to open the connection form.
3. **Enter credentials.** Provide your **TD SYNNEX EC username/password**, the **ConnectWise domain**, **company ID**, **public key** and **private key** generated for the API member.
4. **Connect.** Submit the form.  The system validates your credentials and, once authorised, establishes the connection.

During the connection process the system verifies your API permissions; if any required permission is missing, an error message is displayed (see Article 4 for troubleshooting).

To visualise this step, the first screenshot below shows the **ConnectWise PSA Integration Connector** overview page and the **Connect** button.  The second screenshot displays the connection form where you enter your domain, company ID and API keys.

![Connector overview](/public/assets/images/connecting-step1.jpeg)

![Connection form](/public/assets/images/connecting-step3.jpeg)

#### Activation

Once the connection succeeds, the integration automatically enters an **activation** phase.  Activation performs several tasks within your ConnectWise tenant:

* **Creates required custom fields** (e.g., Send to TDS) and tables within ConnectWise.
* **Verifies the API connection** to confirm that all endpoints are reachable.
* **Configures webhooks** so that ConnectWise sends events (such as “Opportunity updated” or “Purchase order created”) back to the connector.

You do **not** need to manually create fields or callbacks.  Activation completes when all tasks succeed.

The screenshot below shows the **Sync Activity Log** after activation.  This page confirms that the connection is established and summarises the number of records synced or pending.

![Sync activity log](/public/assets/images/connecting-step4.jpeg)

#### Selecting templates

After activation you must decide which integration templates to enable.  Each template addresses a specific use case such as product synchronisation or order submission.  Enable a template by toggling its switch to **Active**.  A high‑level overview of each template is provided in Article 3.

The following screenshot illustrates the **Integration Templates** tab showing the four available templates and their toggle switches.

![Integration templates overview](/public/assets/images/configure-step5.jpeg)

##### Next steps

With the connector activated, continue to [Article 3: Configuring Integration Templates](./kb_templates.md) to learn how to configure and use each template.