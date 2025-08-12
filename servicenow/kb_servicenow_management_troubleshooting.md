# Managing & Troubleshooting the ServiceNow Connector

Proper monitoring and maintenance ensure that your ServiceNow integration remains healthy over time.  This article summarises how to manage the connector, interpret logs and resolve common issues.

## Integration management

### Monitor the Sync Activity Log

The **Sync Activity Log** tab in the Digital Bridge portal lists every action performed by the connector—product synchronisations, order submissions and status updates.  Each entry includes the date, template name, operation type and result.  Use the filter options to narrow the log by date or template.

* **Success:** Indicates that the operation completed without errors.
* **Partial success:** Some items may have completed while others failed.  Review the details to identify the affected SKUs or orders.
* **Failed:** The operation encountered an error.  Click the entry to view the error message and recommended resolution.

You can export log entries to CSV for auditing or support purposes.  TD SYNNEX retains logs for a limited period, so capture them periodically if you require long‑term retention.

### Disconnecting or reconnecting

The **Reconnect** button on the ServiceNow connector overview page can be used to refresh your credentials without resetting template configurations.  This is useful when you rotate the Client Secret.  The **Disconnect** button disables all templates and stops data flow.  After disconnecting, you must re‑enter credentials to resume synchronisation.

## Common errors and resolutions

| Error | Possible cause | Resolution |
|------|----------------|-----------|
| **401 Unauthorized** | Incorrect Instance ID, Client ID or Client Secret. | Verify that the values match those generated in ServiceNow and that the integration user is active.  Regenerate the credentials if necessary. |
| **403 Forbidden or no results** | The integration user lacks permission to access certain tables or fields. | Adjust the user’s roles or groups to include access to product models, purchase orders and custom TD SYNNEX tables. |
| **Invalid SKU during order submission** | The product was not synchronised or category mapping is incorrect. | Run the **Product Sync** template to ensure the SKU exists in ServiceNow and verify category mappings. |
| **Partial shipments not updating** | Status or tracking fields are not mapped correctly. | Edit the **Get Order Status** template to ensure partial shipments and tracking numbers are mapped to the correct fields. |
| **No orders created** | Purchase orders not reaching the required status or template disabled. | Set the **Tds Order status** to *Send to TDS* and confirm that the **Create Orders from ServiceNow** template is enabled. |

## Support

If you continue to experience issues, gather the relevant log entries and reach out to your TD SYNNEX support representative.  Provide details about the affected template, the time of the error and your ServiceNow instance ID.  Additional resources are available via the **Setup Guide** and **Connector Documentation** links on the ServiceNow connector overview page.