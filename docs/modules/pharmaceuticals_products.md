# Pharmaceuticals Products - Customizations

**Module**: `pharmaceuticals_products`  
**Type**: Custom (1)  
**Status**: ✅ In active use  

## Overview
The Pharmaceuticals Products module automatically creates journal entries for consignment products based on percentages set for each vendor. The module triggers when invoices/credit notes are validated or cancelled and contain consignment products, creating appropriate journal entries automatically.

**Note**: To eliminate confusion, the technical name "pharmaceuticals" or "deals" refers to "Consignment Product"

## Workflow Documentation

### Step 1: Configuration
In the configuration, we set the debit/credit accounts and the journal type for automatic journal creation.

![Pharmaceuticals Products Configuration](../screenshots/pharmaceuticals_products_config.png)

*Screenshot showing the configuration settings for accounts and journal types*

### Step 2: Product Setup
In the product view for the consignment product, it must be marked as "Deals Products".

![Pharmaceuticals Products Product View](../screenshots/pharmaceuticals_products_product_view.png)

*Screenshot showing the product view with "Deals Products" checkbox*

### Step 3: Contact/Vendor Setup
In the contact, a section called "Deals Products" is added where the product is selected and the percentage is specified.

![Pharmaceuticals Products Contact](../screenshots/pharmaceuticals_products_contact.png)

*Screenshot showing the contact view with deals products section and percentage settings*

### Step 4: Journal Creation
**Trigger**: When an invoice/credit note is validated or cancelled and contains deals products, journal entries are automatically created.

**Multiple Products**: If the invoice or credit note contains multiple deals products, multiple journals will be created accordingly.

![Pharmaceuticals Products Journal Entry](../screenshots/pharmaceuticals_products_journal_entry.png)

*Screenshot showing the generated journal entry for consignment products*

## Journal Triggers (Also included in the journal entry ref field)

### 1. Invoice
- **Action**: Credits the payables account and debits the expense account
- **Trigger**: When invoice is validated

### 2. Invoice Cancel
- **Action**: Reverses the Invoice journal
- **Trigger**: When invoice is cancelled

### 3. Credit Note
- **Action**: Debits the payables account and credits the expense account
- **Trigger**: When credit note is validated

### 4. Credit Note Cancel
- **Action**: Reverses the credit note journal
- **Trigger**: When credit note is cancelled

## Purpose
The Pharmaceuticals Products module provides:
- **Automatic Journal Creation**: Eliminates manual journal entry creation for consignment products
- **Percentage-Based Calculations**: Uses vendor-specific percentages for accurate accounting
- **Invoice Integration**: Seamlessly integrates with invoice/credit note validation process
- **Consignment Management**: Handles complex consignment product accounting automatically

## Enhancement required
### 1. Smart Button Integration
- **Description**: Add a smart button to invoices/credit notes that links to generated journal entries
- **Purpose**: Provide easy access to view related consignment journal entries
- **Benefit**: Improves traceability and audit capabilities

## Technical Implementation
- **Automatic Triggers**: Invoice/credit note validation and cancellation events
- **Percentage Calculations**: Vendor-specific percentage application
- **Journal Entry Creation**: Automatic generation based on transaction type
- **Multi-Product Support**: Handles multiple consignment products in single transaction
