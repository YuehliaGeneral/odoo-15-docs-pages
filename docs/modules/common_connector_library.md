# Common Connector Library - Customizations

**Module**: `common_connector_library`  
**Type**: Paid + Customized  
**Status**: ✅ In active use  
**Commit**: [e3371a72f3b529e1c0e424b45f4a7f17852b8377](https://github.com/YuehliaGeneral/odoo-15-docs/commit/e3371a72f3b529e1c0e424b45f4a7f17852b8377)

## Overview
The Common Connector Library serves as the base library for all connector operations in our Odoo instance. This module has been customized to extend its functionality beyond the standard paid version to support additional business requirements.

## Customizations Added

### 1. Product Brands Compatibility
- **Description**: Enhanced support for product brand management across connector operations
- **Impact**: Enables seamless handling of product brands when syncing data between Odoo and external platforms
- **Use Case**: Maintains brand consistency across multiple sales channels

### 2. Areas Compatibility
- **Description**: Added compatibility for geographic area handling in connector workflows
- **Impact**: Supports location-based operations and regional business logic
- **Use Case**: Handles area-specific pricing, shipping, and delivery rules

### 3. Custom Fields Support
Extended connector functionality to handle additional custom fields:

| Field | Purpose | Description |
|-------|---------|-------------|
| `delivery_date` | Custom delivery date field from woocommerce | Allows specification of preferred delivery dates |
| `customer_note` | Customer-specific notes field from woocommerce | Captures customer instructions and preferences |
| `delivery_time` | Delivery time preferences from woocommerce | Specifies preferred delivery time windows |
| `shipping_method` | Shipping method selection from woocommerce | Enables customer choice of shipping options |

![Custom Fields Screenshot](../screenshots/delivery%20date%20-%20delivery%20time%20-%20scheduled%20date%20-%20shipping%20method.png)

*Screenshot showing the custom fields: delivery date, delivery time, scheduled date, and shipping method in the system*

## Purpose
These customizations extend the base connector library to support additional business requirements specific to our operations, ensuring seamless integration with external platforms while maintaining data consistency across all connector modules.

## Related Modules
- `shopify_ept` - Shopify connector (also customized)
- `woo_commerce_ept` - WooCommerce connector (also customized)
