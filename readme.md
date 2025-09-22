# Odoo 15 – Customized Branch Documentation

This repository documents the **customized** branch of our Odoo 15 instance.  
It contains all **custom modules**, **third-party paid apps**, and **OCA/free modules** integrated into our system, along with notes on whether they are currently needed.

The documentation is organized by **module type**:

1. Custom plugins (from scratch)  
2. Paid plugins from Odoo App Store  
3. Paid plugins with customization  
4. Free plugins (Odoo App Store / OCA)

- **Needed**:  
  - ✅ → In active use / required  
  - ❌ → Legacy / deprecated / not required  

---

## Module Inventory

> **📖 Documentation Note**: Click on any **custom module name with a hyperlink** to view extended documentation detailing exactly what customizations and changes were implemented for that specific module.

| Name | Technical Name | Description | Type | Needed |
|------|----------------|-------------|------|--------|
| Account User Access | `account_user_access` | Limit access for specific users on bank/cash journals. Could be replaced by *Journal Restriction on Users*. | Custom (1) | ❌ |
| Customize Excel Reports | [`customize_excel_reports`](docs/modules/customize_excel_reports.md) | – | Custom (1) | ✅ Partially |
| Looome Base | [`looome_base`](docs/modules/looome_base.md) | (TBD – base module for Looome brand) | Custom (1) | ✅ |
| Partner Address Fields | `partner_address` | Adds extra address fields on partners. | Custom (1) | ❌ |
| Pick Pack Ship | [`pick_pack_ship`](docs/modules/pick_pack_ship.md) | Custom workflow for picking, packing, and shipping. | Custom (1) | ✅ |
| QR Code Product | `qr_code_product` | Generate QR codes for products. | Custom (1) | ❌ |
| Barcode in Sales/Purchase/Picking | [`sis_barcode`](docs/modules/sis_barcode.md) | Adds a smart button linking barcodes with other picking-related modules. | Custom (1) | ✅ |
| Stock Barcode Screen – Restrict Over QTY/Line | [`sis_barcode_screen_restrict`](docs/modules/sis_barcode_screen_restrict.md) | Restricts barcode scanning so employees can only increase qty up to demand; cannot validate until demand is met. | Custom (1) | ✅ |
| Sismatix Core | `sismatix_core` | (Legacy core from vendor) | Custom (1) | ❌ |
| Pharmaceuticals Products | [`pharmaceuticals_products`](docs/modules/pharmaceuticals_products.md) | Creates automatic journal entries for consignment/deals products on invoice/credit note creation or cancellation. | Custom (1) | ✅ |
| Stock Move Line Report | `stock_move_line_report` | Adds fields (cost, valuation value) to stock move line. | Custom (1) | ❌ |
| Yuehlia Base | [`yuhelia_base`](docs/modules/yuhelia_base.md) | Core module for Yuehlia brand customizations. | Custom (1) | ✅ |
| Stock FSN Analysis & Non Moving Report | `bi_fsn_report` | FSN & non-moving product reports (no longer available). | Paid (2) | ❌ |
| Dashboard Ninja | `ks_dashboard_ninja` | Advanced dashboards & KPIs. | Paid (2) | ✅ |
| Purchase Bonus Quantity | `purchase_bonus_qty` | Adds FOC field (number/%) for bonus qty. Compatible with discounts & costing. Used in `yuhelia_base`. | Paid (2)) | ✅ |
| Journal Restriction on Users | `pw_restrict_account_journal` | Restrict access to journals per user. | Paid (2) | ✅ |
| Common Connector Library | [`common_connector_library`](docs/modules/common_connector_library.md) | Base library for connectors. | Paid + Customized (3) | ✅ |
| Shopify Odoo Connector | [`shopify_ept`](docs/modules/shopify_ept.md) | Connector with Shopify. | Paid + Customized (3) | ✅ |
| WooCommerce Odoo Connector | [`woo_commerce_ept`](docs/modules/woo_commerce_ept.md) | Connector with WooCommerce. | Paid + Customized (3) | ✅ |
| Hide Sale and Cost Price | `abs_hide_sale_cost_price` | Hides product sale & cost prices for restricted users. | Free (4) | ✅ |
| Customer Products Code | `bi_product_customer_code` | Customer-specific product codes. | Free (4) | ✅ |
| Export Product Stock in Excel | `export_stockinfo_xls` | Export product stock in XLS. | Free (4) | ✅ |
| Hide Menu | `kg_hide_menu` | Hide menus per user. | Free (4) | ✅ |
| Hide Create/Delete/Archive/Export | `model_access_rights` | Restrict CRUD/export per model. | Free (4) | ✅ |
| QR Code Base | `ehcs_qr_code_base` | QR code base utility. | Free (4) | ❌ |
| Purchase Order Lines with Discounts | `purchase_discount` | Adds discounts to purchase order lines. | Free (4) | ✅ |
| Base Report XLSX | `report_xlsx` | Support for xlsx reports. | Free (4) | ✅ |
| Product Variant Sale Price | `product_variant_sale_price` | Variant-specific sale prices. | Free (4) | ✅ |
| Purchase Order General Discount | `purchase_order_general_discount` | General discount field on purchase orders. | Free (4) | ✅ |
| Sale Discount on Total Amount | `sale_discount_total` | General discount on sale orders. | Free (4) | ✅ |
| Sales Profit & Loss Report | `sales_profit_loss_report` | Profit & loss report for sales. | Free (4) | ❌ |
| Stock Move Cost Value Report | `stock_move_value_report` | Adds cost value to stock moves. | Free (4) | ❌ |
| Top/Least Selling Product Report | `top_selling_product_report` | Sales analytics report (top/least sellers). | Free (4) | ✅ |
| Print Journal Entries Report | `topaz_print_journal_entries` | Printable journal entries report. | Free (4) | ✅ |
| Website Block Indexing | `web_noindex` | Block indexing for selected website pages. | Free (4) | ✅ |

---

## Other Requirements
- [Other Requirements and Issues](docs/modules/other_requirements.md)