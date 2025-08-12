# Managing & Troubleshooting the Autotask PSA Connector

Proper monitoring and maintenance ensure that your Autotask integration remains healthy over time.  This article summarises how to manage the connector, interpret logs and resolve common issues.

## Integration management

### Monitor the Sync Activity Log

The **Sync Activity Log** tab in the Digital Bridge portal lists every action performed by the connector—product synchronizations, order submissions and status updates.  Each entry includes the date, template name, operation type and result.  Use the filter options to narrow the log by date or template.

* **Success:** Indicates that the operation completed without errors.
* **Partial success:** Some items may have completed while others failed.  Review the details to identify the affected SKUs or orders.
* **Failed:** The operation encountered an error.  Click the entry to view the error message and recommended resolution.

You can export log entries to CSV for auditing or support purposes.  TD SYNNEX retains logs for a limited period, so capture them periodically if you require long‑term retention.

### Disconnecting or reconnecting

The **Reconnect** button on the Autotask connector overview page can be used to refresh your credentials without resetting template configurations.  This is useful when you rotate the API user’s secret.  The **Disconnect** button will disable all templates and stop data flow.  After disconnecting, you’ll need to re‑enter credentials to resume synchronization.

## Common errors and resolutions

| Error | Possible cause | Resolution |
|------|----------------|-----------|
| **401 Unauthorized** | Incorrect user name, secret or missing tracking identifier. | Verify that the API user’s **User Name**, **Secret** and **ApiIntegrationCode** are correct.  Confirm that the user is active and assigned the API‑only security level. |
| **403 Forbidden or no results** | API user lacks permission to access certain modules or line‑of‑business data. | Adjust the API user’s security level or line‑of‑business associations to include Products, Purchase Orders and Inventory. |
| **Invalid SKU during order submission** | Product was not synced or category mapping is incorrect. | Run the **Product Sync** template to ensure the SKU exists in Autotask and verify category mappings. |
| **Partial shipments not updating** | Status mapping not configured correctly. | Edit the **Get Order Status** template to ensure partial shipments are mapped to an appropriate status or note field. |
| **No orders created** | Purchase orders not reaching the required status or automatic submission disabled. | Confirm that POs are marked as ready/approved in Autotask and that the **Create Orders from Autotask** template is enabled.  If you use manual submission, run the submission job on schedule. |

## Support

If you continue to experience issues, gather the relevant log entries and reach out to your TD SYNNEX support representative.  Provide details about the affected template, the time of the error and the Autotask tenant ID.  Additional resources are available via the **Setup Guide** and **Connector Documentation** links in the Autotask connector overview page.