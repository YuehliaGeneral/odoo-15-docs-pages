# Partner Ledger Restructure - Customizations

**Module**: `partner_ledger_restructure`  
**Type**: Custom (1)  
**Status**: ✅ In active use

## Overview

This module enhances the accounting views to improve traceability and reconciliation efficiency. It adds the Source Document context to the Reconciliation screen and surfaces key identifiers on the Partner Ledger report.

## What Changed

- **Reconciliation View**
  - Added field: **Source Document** (`source_document`)

- **Partner Ledger**
  - Added column: **Customer Invoice** (`move.name`)
  - Added column: **Source Document** (`move.invoice_origin`)

## Why This Matters

- **Faster reconciliation**: See originating document context directly while reconciling
- **Better traceability**: Partner Ledger shows invoice reference and its originating document side-by-side
- **Reduced context switching**: Fewer clicks to find origins of entries during review

## UI Locations

- Reconciliation: Source Document displayed alongside move information
- Accounting › Reports › Partner Ledger: new columns for Customer Invoice and Source Document

## Technical Notes

- Reconciliation view extended to include `source_document`
- Partner Ledger report view/model extended to add `move.name` and `move.invoice_origin`
- No changes to totals or grouping logic

## Purpose

- **Operational clarity**: Provide immediate context for entries during reconciliation and ledger reviews
- **Auditability**: Make source documents visible in key accounting views without drilling down
