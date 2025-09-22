# Customize Excel Reports - Customizations

**Module**: `customize_excel_reports`  
**Type**: Custom (1)  
**Status**: ✅ Partially (Only 1 out of 3 reports required)  

## Overview
Custom report

## Customizations Added

### 1. Slow-moving Items Report
**Required Report**: Only this report is actively used in the system

- **Description**: Excel report for analyzing slow-moving inventory items
- **Location**: Inventory > Reporting > Slow-moving Items Report
- **Files**:
  - `customize_excel_reports/wizards/slow_moving_items_report.xml`
  - `customize_excel_reports/wizards/slow_moving_items_report.py`
- **Purpose**: Identifies inventory items that have low movement or are becoming obsolete
- **Use Case**: Helps in inventory management decisions, clearance sales, and stock optimization

### 2. Other Reports (Not Required)
The module contains additional reports that are not currently needed:
- Additional Excel report types that are not in active use
- These can be removed or disabled if not required for future operations

## Purpose
The Customize Excel Reports module provides:
- **Inventory Analysis**: Slow-moving items identification for better stock management
- **Excel Integration**: Excel format output

## Dependencies
- Base Odoo 15 modules
- pharmaceuticals_products

## Status Note
**Partially Required**: Only the Slow-moving Items Report is currently needed. The other reports in this module are not required and can be considered for removal if they're not needed for future operations.
**Note**: The other reports are flawed, not showing correct values, may be considered to be redeveloped in later stages.
