# Submit Order Template

## What This Template Does

The Submit Order template automatically converts your Autotask purchase orders into TD SYNNEX orders. When you create a purchase order in Autotask with TD SYNNEX products, this template handles the submission process automatically.

![Autotask Purchase Order Creation](/public/assets/images/autotask-new-purchase-order.png)

### Key Features

**Automatic Order Submission**: Converts Autotask purchase orders to TD SYNNEX orders without manual intervention.

**Order Validation**: Checks order details before submission to prevent errors.

**Status Updates**: Updates the Autotask purchase order with TD SYNNEX order numbers and status.

**Error Handling**: Retries failed orders and logs issues for review.

## Prerequisites

**Product Sync Required**: The Product Sync template must be enabled and running first.

**API Permissions**: Your Autotask API user needs full access to Purchase Orders and Purchase Order Line Items.

**TD SYNNEX Products**: Orders must contain products that were synced from TD SYNNEX.

## How Submit Order Works

### Order Processing Flow

1. **Order Detection**: The template monitors Autotask for new purchase orders with TD SYNNEX products
2. **Validation**: Checks that all products are valid TD SYNNEX SKUs with current pricing
3. **Order Preparation**: Formats the order data according to TD SYNNEX requirements
4. **Submission**: Sends the order to TD SYNNEX via Digital Bridge APIs
5. **Confirmation**: Updates the Autotask purchase order with TD SYNNEX order number and status

### What Gets Submitted

**Order Information**:
- Purchase order number and details
- Customer billing and shipping information
- Order date and requested delivery date
- Special instructions and notes

**Product Details**:
- TD SYNNEX SKU numbers
- Quantities ordered
- Unit prices and extended totals
- Product descriptions and specifications

**Customer Information**:
- Company name and contact details
- Billing address and payment terms
- Shipping address and delivery instructions
- Customer purchase order references

## Configuration Steps

### Step 1: Enable the Template

1. **Navigate to Integration Templates**
   - Go to your Autotask connector in Digital Bridge
   - Click the **Integration Templates** tab

2. **Configure Submit Order**
   - Find the **Submit Order** template tile
   - Click **Change Settings** if configuration is needed
   - Use the toggle to turn the template **On**

### Step 2: Set Processing Options

**Order Processing Schedule**:
- **Immediate**: Orders are submitted as soon as they're created
- **Scheduled**: Orders are processed at specific times
- **Manual**: Orders are submitted only when manually triggered

**Validation Rules**:
- **Product Validation**: Ensures all products are valid TD SYNNEX SKUs
- **Pricing Validation**: Checks that pricing is current and accurate
- **Customer Validation**: Verifies customer information is complete

**Error Handling**:
- **Retry Attempts**: Number of times to retry failed orders
- **Error Notifications**: Who receives alerts about failed orders
- **Manual Review**: Whether failed orders require manual intervention

## Creating Orders in Autotask

### Order Requirements

**TD SYNNEX Products Only**: The purchase order must contain only products that were synced from TD SYNNEX.

**Complete Information**: All required fields must be filled out, including customer details and shipping information.

**Valid Pricing**: Product prices should match current TD SYNNEX pricing.

**Proper Status**: The purchase order should be in the correct status for submission.

### Order Creation Process

1. **Create New Purchase Order**
   - Go to **Inventory → Purchase Orders** in Autotask
   - Click **New** to create a new purchase order
   - Select TD SYNNEX as the vendor

2. **Add Product Line Items**
   - Add TD SYNNEX products to the order
   - Verify quantities and pricing
   - Include any special instructions

3. **Complete Order Details**
   - Fill in customer billing and shipping information
   - Set delivery dates and terms
   - Add any special instructions or notes

4. **Submit for Processing**
   - Save the purchase order
   - The Submit Order template will detect and process it automatically

![Autotask Purchase Order Search](/public/assets/images/autotask-purchase-order-search.png)

## Monitoring Order Submission

### Sync Activity Log

The Sync Activity Log shows:
- Orders that have been submitted to TD SYNNEX
- Submission status and results
- Any errors or warnings
- Processing times and performance metrics

### Order Status Updates

**Submitted**: Order has been sent to TD SYNNEX successfully.

**Accepted**: TD SYNNEX has received and accepted the order.

**Failed**: Order submission encountered an error.

**Pending**: Order is waiting to be processed.

## Troubleshooting

### Common Issues

**Orders Not Submitting**:
- Verify products are TD SYNNEX SKUs from Product Sync
- Check that customer information is complete
- Ensure API user has proper permissions

**Validation Errors**:
- Review product SKUs and pricing
- Check customer address format
- Verify all required fields are filled

**Network Issues**:
- Check internet connectivity
- Verify Digital Bridge connection status
- Review firewall and security settings

### Best Practices

**Order Preparation**: Always verify order details before saving.

**Product Selection**: Use only products synced from TD SYNNEX.

**Customer Data**: Ensure shipping and billing information is accurate and complete.

**Monitoring**: Regularly check the Sync Activity Log for issues.

## Next Steps

Once Submit Order is working:

1. **Test with Small Orders**: Start with simple orders to verify the process
2. **Train Your Team**: Show staff how to create orders properly
3. **Enable Order Status**: Add order tracking capabilities
4. **Monitor Performance**: Watch for any issues or improvements needed

The Submit Order template automates the ordering process, saving time and reducing errors when purchasing from TD SYNNEX through Autotask PSA.

