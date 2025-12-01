# Aged Payable 2 - Customizations

**Module**: `aged_payable_2`  
**Type**: Custom (1)  
**Status**: ✅ In active use

## Overview
This module duplicates the Odoo Enterprise report "Aged Payable" and introduces a single behavioral change: aging is calculated based on the Account Move Date instead of the Due Date. This ensures the aging buckets reflect the actual posting date of payables rather than their maturity.

## What Changed
- **Original (Enterprise)**: Uses Due Date, falling back to Move Date
- **This Module**: Always uses Move Date

### Original behavior (Enterprise `account_reports`)
```sql
COALESCE(account_move_line.date_maturity, account_move_line.date) AS report_date,
```

### New behavior (`aged_payable_2`)
```sql
account_move_line.date AS report_date,
```

## Resulting Behavior
- All aging bucket computations (0–30, 31–60, etc.) now reference `account_move_line.date` as the source `report_date`
- No other logic or layout changes are introduced; the report is otherwise identical to Enterprise "Aged Payable"

## Technical Notes
- Based on Enterprise model: `account_reports/models/account_aged_partner_balance.py`
- The query building for report lines was altered to use `account_move_line.date` unconditionally for `report_date`
- No changes to filters, groupings, or column layout

## Requirements
- Odoo Enterprise Accounting Reports module must be available in the instance
- Appropriate access rights to run Accounting reports

## Purpose
- **Clarity for Finance**: Align aging with posting periods for analysis and accrual-based reporting
