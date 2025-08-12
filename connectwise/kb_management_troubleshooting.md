### TD SYNNEX Digital Bridge – ConnectWise PSA Connector  
**Managing & Troubleshooting the Integration**

This article explains how to monitor the ConnectWise PSA connector once it is deployed and how to address common errors.

#### Monitoring integration status

In the Connector Bridge dashboard, each integration appears as a **connector card**.  The card’s status colour and label indicate the current state:

* **Active (green)** – the connector is running; the card shows **Manage**.
* **Inactive (grey)** – the connector is installed but not enabled; the card shows **Complete Setup**.
* **Error (red)** – the connector encountered a problem; the card shows **Integration error** with a prompt to check API configuration.

Connector status refreshes automatically every 30 minutes with updates from TD SYNNEX.  You can open the card to review sync‑activity logs, check API connection status or modify templates.

![Integration status cards and error example](/public/assets/images/installation_guide_page7-7.png)

#### Error categories

Errors encountered during installation or runtime generally fall into two categories:

1. **Installation permission errors.** These occur immediately after the API credentials are validated.  The system verifies that your API member has the required rights (see Article 1).  If a permission is missing (for example, access to the Purchase Orders module), the integration displays an error explaining what needs adjustment.
2. **Workflow sync errors.** These appear when something unexpected happens during a live sync, such as:
   * Product pricing lookups
   * Purchase‑order submissions
   * Order‑status updates

   Many issues are flagged within the Connector Bridge interface, but some exceptions are monitored by TD SYNNEX and may not be visible.

An example of a workflow error banner and the troubleshooting section from the installation guide are shown below.

![Workflow sync error and troubleshooting](/public/assets/images/installation_guide_page7-7.png)

#### Troubleshooting & support

If you encounter problems during activation or synchronisation, follow these troubleshooting steps:

1. **Verify credentials.** Double‑check your TD SYNNEX username/password and ConnectWise API keys.
2. **Confirm API keys are active.** Make sure the API member is not disabled and both keys are current.
3. **Review error messages.** Read the detailed text on the Manage page; it will indicate missing permissions or invalid fields.

If the steps above do not resolve the issue, contact TD SYNNEX support at **digitalbridge@tdsynnex.com** and provide any relevant error codes or logs.  For further information, visit [tdsynnex.com/na/us/digital‑bridge](https://tdsynnex.com/na/us/digital-bridge).

---

With these management and troubleshooting guidelines, you should be able to maintain a healthy integration and quickly address any issues that arise.  Return to earlier articles for details about prerequisites, connection steps and template configuration.