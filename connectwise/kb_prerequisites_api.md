### TD SYNNEX Digital Bridge – ConnectWise PSA Connector  
**Prerequisites & API setup**

This article provides administrators with the required background before connecting the TD SYNNEX Digital Bridge connector to **ConnectWise PSA**.  It covers the connector’s purpose, necessary credentials, and how to configure an API member with the correct permissions.

#### Overview

The Digital Bridge connector allows ConnectWise users to obtain real‑time TD SYNNEX pricing, submit purchase orders and receive automated order status updates directly within ConnectWise.  Installing the connector requires a TD SYNNEX account, a ConnectWise API user and appropriate permissions.

![API Member permissions matrix](/public/assets/images/cw-psa-permissionsmatrix.png)

#### Prerequisites

1. **TD SYNNEX EC credentials.** You must have a valid account on the TD SYNNEX Electronic Commerce (EC) platform.
2. **ConnectWise PSA API member.** You need to create a dedicated API user in ConnectWise (System → Members → API Members).  Assign a role that meets the permissions matrix below and click **Save**.
3. **API keys and company ID.** After creating the API member, open its profile and generate a **public key** and **private key** on the API Keys tab.  Record the keys and the company ID – these values are required when connecting the app.
4. **Permission matrix.** Ensure that the API user has the minimum rights defined below.

##### API Member permissions

| Module / Function               | Add | Edit | Inquire | Delete | Close | Notes / Why |
|---------------------------------|:---:|:----:|:------:|:------:|:-----:|-------------|
| Sales → Opportunities           | ✔   | ✔    | ✔       |        |       | Update line items (price/availability) |
| Procurement → Product Catalog   | ✔   | ✔    | ✔       |        |       | Create/maintain SKUs tied to the TD SYNNEX vendor |
| Procurement → Purchase Orders   | ✔   | ✔    | ✔       | ✔      | ✔     | Create PO, write TD SYNNEX sales‑order number and close when shipped |
| Company → Companies/Contacts    | ✔   | ✔    | ✔       |        |       | Auto‑create TD SYNNEX vendor; read ship‑to/bill‑to information |
| System → Callback Entries       | ✔   | ✔    |         |        |       | Manage webhooks for “PO Created / PO Status Changed” |
| System → Table Setup            |     | ✔    | ✔       |        |       | Required to create custom fields and add/edit PO‑status values |

The permissions matrix ensures your API member has sufficient rights to create products, purchase orders, and manage callbacks in ConnectWise.  If any permission is missing, the installation will fail during validation.

##### Next steps

Once you have gathered your EC credentials, created a ConnectWise API member and generated the API keys, proceed to [Article 2: Connecting & activating the connector](./kb_connect_activation.md) to link your environment through the Connector Bridge.