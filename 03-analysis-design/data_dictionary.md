# Data Dictionary
## Laser Print Template Layout Management System

**Project:** Laser Print Template Layout Management System
**Version:** 1.0
**Date:** 2025-12-18

---

## Purpose

This data dictionary defines all data elements used in the laser print layout management system, including database tables, fields, and their attributes.

---

## Database Tables

### Table: customer_layout_config

**Purpose:** Stores customer-specific layout configurations

| Column Name | Data Type | Length | Null | PK | FK | Default | Description |
|-------------|-----------|--------|------|----|----|---------| ------------|
| config_id | INT | - | No | Yes | - | AUTO | Unique configuration ID |
| customer_id | VARCHAR | 50 | No | - | Yes (Customers.customer_id) | - | Customer identifier from Kubal |
| customer_name | VARCHAR | 200 | No | - | - | - | Customer name (denormalized for performance) |
| template_type | VARCHAR | 50 | No | - | - | 'STANDARD' | Layout template type (STANDARD, MINIMAL, DETAILED, CUSTOM) |
| is_active | BOOLEAN | - | No | - | - | TRUE | Active status (TRUE/FALSE) |
| created_by | VARCHAR | 100 | No | - | - | - | User ID who created config |
| created_date | DATETIME | - | No | - | - | CURRENT_TIMESTAMP | Creation timestamp |
| modified_by | VARCHAR | 100 | Yes | - | - | NULL | User ID who last modified |
| modified_date | DATETIME | - | Yes | - | - | NULL | Last modification timestamp |
| version | INT | - | No | - | - | 1 | Configuration version number |
| notes | TEXT | - | Yes | - | - | NULL | Optional notes/comments |

**Indexes:**
- PRIMARY KEY (config_id)
- INDEX idx_customer_id (customer_id)
- INDEX idx_active (is_active)
- UNIQUE INDEX idx_customer_active (customer_id, is_active) WHERE is_active=TRUE

**Constraints:**
- Only one active configuration per customer
- template_type must be in ('STANDARD', 'MINIMAL', 'DETAILED', 'CUSTOM')

---

### Table: layout_field_mapping

**Purpose:** Stores which data fields are included in each layout configuration

| Column Name | Data Type | Length | Null | PK | FK | Description |
|-------------|-----------|--------|------|----|----|-------------|
| mapping_id | INT | - | No | Yes | - | Unique mapping ID |
| config_id | INT | - | No | - | Yes (customer_layout_config.config_id) | Configuration this mapping belongs to |
| field_code | VARCHAR | 50 | No | - | Yes (available_data_fields.field_code) | Data field code |
| is_required | BOOLEAN | - | No | - | - | Whether field is required (mandatory) |
| field_order | INT | - | Yes | - | - | Display order (if applicable) |
| formatting_rules | VARCHAR | 200 | Yes | - | - | Optional formatting rules (JSON) |

**Indexes:**
- PRIMARY KEY (mapping_id)
- INDEX idx_config_id (config_id)
- UNIQUE INDEX idx_config_field (config_id, field_code)

---

### Table: available_data_fields

**Purpose:** Master list of all data fields that can be included in layouts

| Column Name | Data Type | Length | Null | PK | Description |
|-------------|-----------|--------|------|----|-------------|
| field_code | VARCHAR | 50 | No | Yes | Unique field code (e.g., LOGO, COMPANY_NAME) |
| field_name | VARCHAR | 100 | No | - | Human-readable field name |
| field_description | VARCHAR | 500 | Yes | - | Description of what this field contains |
| data_type | VARCHAR | 20 | No | - | Data type (TEXT, NUMERIC, DATE, IMAGE, QRCODE) |
| source_table | VARCHAR | 100 | Yes | - | Kubal table where data is sourced |
| source_column | VARCHAR | 100 | Yes | - | Kubal column name |
| max_length | INT | - | Yes | - | Maximum character length (for Hertwich constraints) |
| is_always_required | BOOLEAN | - | No | - | TRUE if field must be in every layout (e.g., QR_CODE) |
| is_active | BOOLEAN | - | No | - | Whether field is currently available |

**Indexes:**
- PRIMARY KEY (field_code)

**Sample Data:**

| field_code | field_name | data_type | source_table | source_column | max_length | is_always_required |
|------------|------------|-----------|--------------|---------------|------------|-------------------|
| LOGO | Company Logo | IMAGE | - | - | - | FALSE |
| COMPANY_NAME | Company Name | TEXT | Customers | company_name | 100 | FALSE |
| CHARGE_NUM | Charge Number | TEXT | Production_Orders | charge_number | 20 | FALSE |
| ALLOY_NUM | Alloy Number | TEXT | Products | alloy_number | 20 | FALSE |
| HOMOGEN_STATUS | Homogenization Status | TEXT | Production_Process | homogenization_status | 50 | FALSE |
| HOMOGEN_MACHINE | Homogenization Machine | TEXT | Equipment | machine_name | 50 | FALSE |
| INGOT_ID | Unique Ingot ID | TEXT | Inventory | ingot_id | 30 | FALSE |
| LENGTH | Length | NUMERIC | Production_Orders | length | 10 | FALSE |
| DIMENSION | Dimension | TEXT | Products | dimension | 20 | FALSE |
| PROD_DATE | Production Date | DATE | Production_Orders | production_date | 10 | FALSE |
| QR_CODE | QR Code | QRCODE | - | - | - | TRUE |

---

### Table: batch_layout_log

**Purpose:** Audit trail linking production batches to layouts used

| Column Name | Data Type | Length | Null | PK | Description |
|-------------|-----------|--------|------|----|-------------|
| log_id | INT | - | No | Yes | Unique log entry ID |
| batch_number | VARCHAR | 50 | No | - | Production batch/charge number |
| config_id | INT | - | No | Yes (customer_layout_config.config_id) | Configuration used |
| customer_id | VARCHAR | 50 | No | - | Customer ID (denormalized) |
| transmission_timestamp | DATETIME | - | No | - | When data was sent to Hertwich |
| transmission_status | VARCHAR | 20 | No | - | SUCCESS, FAILED, RETRIED |
| data_snapshot | TEXT | - | Yes | - | JSON snapshot of data sent |
| override_used | BOOLEAN | - | No | - | TRUE if manual override was used |
| override_reason | TEXT | - | Yes | - | Reason for override (if applicable) |
| processed_by | VARCHAR | 100 | No | - | User ID who processed |

**Indexes:**
- PRIMARY KEY (log_id)
- INDEX idx_batch_number (batch_number)
- INDEX idx_transmission_date (transmission_timestamp)
- INDEX idx_customer_id (customer_id)

---

### Table: configuration_audit_log

**Purpose:** Audit trail of all configuration changes

| Column Name | Data Type | Length | Null | PK | Description |
|-------------|-----------|--------|------|----|-------------|
| audit_id | INT | - | No | Yes | Unique audit entry ID |
| config_id | INT | - | No | - | Configuration that was changed |
| action_type | VARCHAR | 20 | No | - | CREATE, UPDATE, DEACTIVATE, REACTIVATE |
| changed_by | VARCHAR | 100 | No | - | User ID who made change |
| changed_date | DATETIME | - | No | - | Timestamp of change |
| old_value | TEXT | - | Yes | - | JSON of previous configuration state |
| new_value | TEXT | - | Yes | - | JSON of new configuration state |
| change_reason | VARCHAR | 500 | Yes | - | Optional reason for change |

**Indexes:**
- PRIMARY KEY (audit_id)
- INDEX idx_config_id (config_id)
- INDEX idx_changed_date (changed_date)

---

### Table: layout_templates

**Purpose:** Predefined layout templates

| Column Name | Data Type | Length | Null | PK | Description |
|-------------|-----------|--------|------|----|-------------|
| template_code | VARCHAR | 50 | No | Yes | Template code (STANDARD, MINIMAL, DETAILED, CUSTOM) |
| template_name | VARCHAR | 100 | No | - | Template display name |
| template_description | VARCHAR | 500 | Yes | - | Description of template |
| default_fields | TEXT | - | No | - | JSON array of default field codes |
| is_active | BOOLEAN | - | No | - | Whether template is currently available |

**Sample Data:**

| template_code | template_name | default_fields (JSON) |
|---------------|---------------|----------------------|
| STANDARD | Standard Layout | ["LOGO","COMPANY_NAME","CHARGE_NUM","ALLOY_NUM","HOMOGEN_STATUS","HOMOGEN_MACHINE","QR_CODE"] |
| MINIMAL | Minimal Layout | ["ALLOY_NUM","CHARGE_NUM","QR_CODE"] |
| DETAILED | Detailed Layout | ["LOGO","COMPANY_NAME","CHARGE_NUM","ALLOY_NUM","HOMOGEN_STATUS","HOMOGEN_MACHINE","INGOT_ID","LENGTH","DIMENSION","QR_CODE"] |
| CUSTOM | Custom Layout | ["QR_CODE"] |

---

## Data Element Definitions

### Core Business Entities

**Customer:**
- **Definition:** A client who purchases aluminum billets
- **Source:** Kubal Customers table
- **Key Attribute:** customer_id (VARCHAR 50)
- **Related Tables:** customer_layout_config

**Production Order / Batch:**
- **Definition:** A production run for a specific quantity of billets
- **Source:** Kubal Production_Orders table
- **Key Attribute:** charge_number / batch_number (VARCHAR 50)
- **Related Tables:** batch_layout_log

**Layout Configuration:**
- **Definition:** Set of data fields and formatting rules for a customer's laser print
- **Source:** customer_layout_config table
- **Key Attribute:** config_id (INT)

**Data Field:**
- **Definition:** Individual piece of information that can be laser-printed
- **Source:** available_data_fields table
- **Key Attribute:** field_code (VARCHAR 50)
- **Examples:** ALLOY_NUM, CHARGE_NUM, QR_CODE

---

## Data Validation Rules

| Field Type | Validation Rule | Example |
|------------|-----------------|---------|
| CHARGE_NUM | Alphanumeric, max 20 chars | "CH-123456" |
| ALLOY_NUM | Alphanumeric, max 20 chars | "6061", "AL-7075" |
| COMPANY_NAME | Text, max 100 chars | "ABC Aluminum Corp" |
| LENGTH | Numeric, max 10 digits, unit in mm | "6000" (mm) |
| DIMENSION | Text, max 20 chars | "150mm x 300mm" |
| QR_CODE | Generated, contains comma-separated values | "CH-12345,CUST001,6061,150x300,6000,COMPLETE" |
| INGOT_ID | Alphanumeric, max 30 chars | "ING-20251218-001" |
| HOMOGEN_STATUS | Text from predefined list | "COMPLETE", "PENDING", "NOT_REQUIRED" |

---

## Data Flow

```
Kubal Database → Available Data Fields → Layout Configuration → Production Order →
Field Mapping → Data Extraction → Validation → Hertwich Transmission → Batch Log
```

---

**END OF DOCUMENT**
