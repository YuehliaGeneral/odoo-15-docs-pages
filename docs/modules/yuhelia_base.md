# Yuehlia Base - Customizations

**Module**: `yuhelia_base`  
**Type**: Custom (1)  
**Status**: ✅ In active use  

## Overview
The Yuehlia Base module serves as the core foundation module for Yuehlia brand customizations. It provides essential functionality that integrates and enhances multiple business processes including inventory management, sales, purchases, and e-commerce operations.

## Dependencies
- `pick_pack_ship` - Custom workflow for picking, packing, and shipping
- `woo_commerce_ept` - WooCommerce connector
- `purchase_discount` - Purchase order discounts
- `common_connector_library` - Base connector library
- `purchase_bonus_qty` - Purchase bonus quantity functionality

## Customizations Added

### 1. Stock Picking Enhancements

#### 1.1 Delivery Information Fields
- **delivery_date**: Custom delivery date field
- **delivery_time**: Delivery time preferences
- **shipping_method**: Shipping method selection
- **customer_note**: Customer-specific notes
- **payment_gateway_id**: Related payment gateway from sale order

Note: See the screenshot added in section 1.3 for how these delivery date/time fields display on pickings; the same columns are also added to the sale orders list view.

#### 1.2 Package Management
- **pkg_one**: Single package count field
- **no_of_boxes**: Computed field for total package count
- **runsheet_state**: Related runsheet state (draft, handover, confirmed, done, cancelled)

![Picking Fields (PICK type)](../screenshots/yuehlia_base_picking_fields.png)

Screenshot for the Picking operation of type "PICK" showing relevant fields.

![Picking Fields (OUT type)](../screenshots/yuehlia_base_picking_OUT_fields.png)

Screenshot for the Picking operation of type "OUT" showing relevant fields.

#### 1.3 Scheduled Date Logic
- **Automatic scheduling**: Delivery date and time affect the scheduled_date field
- **Timezone handling**: Converts local time to UTC for proper scheduling
- **Move line updates**: Updates stock move lines with new scheduled dates

![Delivery Time & Date on Picking](../screenshots/yuehlia_base_delivery_time_date_picking.png)

Note: The same delivery date/time columns are also added to the Sale Orders list view.

### 2. Product Management Enhancements

#### 2.1 Product Template Extensions
- **product_code**: Related vendor product code from seller information
- **product_name**: Related vendor product name from seller information
- **woo_product_template_ids**: One2many relationship with WooCommerce products
- **product_brand_ids**: Many2one relationship with product brands
- **product_categ_ids**: Related WooCommerce categories

![Product Template – Product Name](../screenshots/yuehlia_base_product_template_product_name.png)

![Product Brand on Product](../screenshots/yuehlia_base_product_product_brand.png)

Note: Brand field is synced from WooCommerce. Only English products should sync this field. There is an issue where not all products in Odoo show a brand value even though WooCommerce has it for all; this should be fixed.

![Sales Reporting – Group by Brand](../screenshots/yuehlia_base_sales_reporting_dashboard_brand.png)

Note: Brand value is available to group sales reports by brand.

![Purchase Form – Brand](../screenshots/yuehlia_base_purchase_form_brand.png)

Note: Brand value is added to the Purchase form as well.

#### 2.2 Product Search Enhancement
- **Enhanced search**: Includes product name, default code, barcode, and vendor product name in search
- **Multi-field search**: Searches across multiple product identification fields

![Sales Reporting – Search by Brand](../screenshots/yuehlia_base_sales_reporting_dashboard_search_brand.png)

Note: Brand value is searchable.

### 3. Purchase Order Enhancements

#### 3.1 Purchase Order Line Extensions
- **total_qty**: Computed field showing total quantity (qty + bonus qty)
- **product_brand_ids**: Related product brand information
- **Price automation**: Automatically sets price unit to product standard price: yuhelia_base/models/purchase.py:16-21, if the price is 0 then use the product_id.standard_price

![Purchase Form – Brand](../screenshots/yuehlia_base_purchase_form_brand.png)

Note: Brand value is added to the Purchase form.

![Purchase Total Qty](../screenshots/yuehlia_base_purchase_total_qty.png)

Note: The total qty field was created because we have a bonus qty (FOC) customization from the `purchase_bonus_qty` module.

#### 3.2 Purchase Order Extensions
- **po_type**: Selection field for PO Type (WSP, RSP)
- **amount_discount**: Computed field for total discount amount

![Purchase PO Type](../screenshots/yuehlia_base_purchase_po_type.png)

Note: This is a simple drop-down to indicate which pricing type the PO is using; no further logic depends on it.

### 4. Sale Order Enhancements

#### 4.1 Partial Credit Note Functionality
- **partial_credit_note()**: Method to open WooCommerce return order wizard
- **WooCommerce integration**: Seamless integration with WooCommerce cancellation process

![Sale Order – Partial Credit Note Shortcut](../screenshots/yuehlia_base_so_partial_credit_note.png)

Note: Create credit note button shortcut – Not used; can be removed.

#### 4.2 Customer Notes
- **customer_note**: Field for customer-specific notes in sale orders

![Sale Order – Customer Notes](../screenshots/yuehlia_base_so_customer_notes.png)

### 5. WooCommerce Integration

#### 5.1 Stock Update Automation
- **auto_update_all_prod_stock()**: Method to update all product stock to WooCommerce - Can be removed as its note used (function: auto_update_all_prod_stock, cron: ir_cron_update_woo_stock_all)
- **Cron job**: Automated daily stock update (currently disabled)
- **Instance-based updates**: Updates stock for specific WooCommerce instances

### 6. Runsheet Enhancements

#### 6.1 Internal Driver Support
- **emp_driver_id**: Many2one field for internal driver assignment - Its already defined in pick_pack_ship module, not sure if needed in yuehlia_base. (reference: yuhelia_base/models/runsheet.py)

### 7. Stock Move Line Enhancements

#### 7.1 Automatic Lot Generation
- **lot_name**: Auto-generated lot/serial numbers using sequence, not needed and can be removed (reference: yuhelia_base/models/stock.py:80-83)
- **pro_image**: Related product image for visual identification

![Picking Line – Product Image](../screenshots/yuehlia_base_picking_line_image.png)

#### 7.2 Stock Move Extensions
- **vendor_product_code**: Related vendor product reference number - can be removed as "report_vendor_receipt_document"(pick_pack_ship/report/delivery_receipt_temp.xml) report from pick_pack_ship module is not used (Reference: yuhelia_base/models/stock.py:90)
- **vendor_product_name**: Related vendor product name - can be removed as "report_vendor_receipt_document"(pick_pack_ship/report/delivery_receipt_temp.xml) report from pick_pack_ship module is not used (Reference: yuhelia_base/models/stock.py:91)
- **pro_image**: Related product image

![Picking Line – Product Image](../screenshots/yuehlia_base_picking_line_image.png)

### 8. View Customizations

#### 8.1 Product Views
- **Search enhancement**: Added product code and name to search fields
- **Tree view**: Added product code and name columns
- **Purchase tab**: Restricted access to specific user groups

![Product Search – Vendor Code & Name](../screenshots/yuehlia_base_product_product_code_name_search.png)

Note: Vendor product code and name are included in the search to help the purchasing department find products faster.

#### 8.2 Purchase Views
- **Order line enhancements**: Added total quantity and product brand columns
- **PO type field**: Added purchase order type selection
- **Report customization**: Added barcode to purchase order reports

![Purchase Form – Brand](../screenshots/yuehlia_base_purchase_form_brand.png)

Note: Brand value is added to the Purchase form.

![Purchase Total Qty](../screenshots/yuehlia_base_purchase_total_qty.png)

Note: The total qty field was created because of the bonus qty (FOC) customization from the `purchase_bonus_qty` module.

![Purchase PO Type](../screenshots/yuehlia_base_purchase_po_type.png)

Note: This is a simple drop-down to indicate which pricing type the PO is using; no further logic depends on it.

![Purchase Order Print](../screenshots/yuehlia_base_po_print.png)

![Purchase Order Print with Bonus Qty](../screenshots/yuehlia_base_po_print_with_bonus_qty.png)

Note: The print layout differs when a PO contains bonus qty values.

#### 8.3 Stock Views
- **Product image**: Added product image widget in picking operations
- **Delivery information**: Added delivery date, time, and shipping method fields
- **Package management**: Simplified package count interface (only pkg_one visible)
- **Vendor information**: Added vendor product code and name in move lines

#### 8.4 Sale Views
- **Customer notes**: Added customer note field
- **Partial credit note**: Added button for WooCommerce partial credit note process

### 9. Security and Access Control

#### 9.1 User Groups
- **group_contacts_show**: Controls visibility of contacts menu
- **group_product_template_show**: Controls access to product purchase tab

### 10. Data and Sequences

#### 10.1 Sequence Generation
- **stock.move.line**: Auto-generated sequence for lot/serial numbers

#### 10.2 Cron Jobs
- **WooCommerce stock update**: Automated daily stock synchronization (disabled by default)

## Purpose
The Yuehlia Base module provides:
- **Core Integration**: Seamless integration between multiple business modules
- **Enhanced Workflows**: Improved picking, packing, and shipping processes
- **E-commerce Support**: Enhanced WooCommerce integration and automation
- **Data Consistency**: Unified product and vendor information across modules
- **User Experience**: Improved interfaces and user controls

## Business Benefits
- **Operational Efficiency**: Streamlined workflows across all business processes
- **Data Integration**: Consistent product and vendor information
- **E-commerce Automation**: Automated stock updates and order processing
- **User Control**: Enhanced access control and user experience
- **Process Standardization**: Unified processes across different modules

## Technical Implementation
- **Model Inheritance**: Extends multiple Odoo models with custom fields and methods
- **View Customization**: Modifies existing views to add new functionality
- **Security Integration**: Implements user group-based access control
- **Cron Automation**: Automated processes for stock synchronization
- **Sequence Management**: Auto-generation of lot/serial numbers
