# 2.1.-BaseDades_N1_Ex1
This project defines the database structure for managing an optics business. The database includes tables for clients, employees, glasses, referrals, sales, suppliers, and sale details. It is designed to handle key operations such as recording client information, tracking sales, and managing inventory.

## Database Structure
### 1. `clients` Table
Stores information about the clients of the optics business.

- **Columns**:
  - `id_client` (Primary Key): Unique identifier for the client.
  - `name`: Name of the client.
  - `address`: Address of the client.
  - `phone`: Contact phone number of the client.
  - `email`: Email address of the client (optional).
  - `register_date`: Date the client was registered.
  - `id_referral` (Foreign Key): Reference to the referral source from the `referral` table.
  - `id_employee` (Foreign Key): Reference to the employee managing this client from the `employee` table.
  
### 2. `employee` Table
Stores details of employees working in the business.

- **Columns**:
  - `id_employee` (Primary Key): Unique identifier for the employee.
  - `name`: Name of the employee.

### 3. `glasses` Table: 
Tracks inventory for glasses.

- **Columns**:
  - `id_glasses` (Primary Key): Unique identifier for glasses.
  - `brand`: Brand of the glasses.
  - `left_eye_measurement` & `right_eye_measurement`: Measurements for the left and right lenses (optional).
  - `frame_type`: Type of frame (e.g., Flotant, Pasta, Metàl·lica).
  - `frame_colour`: Color of the frame (optional).
  - `lefteye_glass_colour` & `righteye_glass_colour`: Colors of the lenses for each eye (optional).
  - `price`: Price of the glasses.
  - `id_supplier` (Foreign Key): Reference to the supplier in the `supplier` table.
  - `id_brand` (Foreign Key): Reference to the brands in the `brands` table.

### 4. `referral` Table
Tracks referral sources for new clients.

- **Columns**:
  - `id_referral` (Primary Key): Unique identifier for the referral source.
  - `name`: Name of the referral source.


### 5. `sales` Table
Tracks sales transactions.

- **Columns**:
  - `id_sale` (Primary Key): Unique identifier for the sale.
  - `id_client` (Foreign Key): Reference to the client who made the purchase.
  - `id_employee` (Foreign Key): Reference to the employee who handled the sale.
  - `id_glasses` (Foreign Key): Reference to the glasses sold.
  - `sale_date`: Date of the sale.


### 6. `sale_detail` Table
Tracks detailed information about items sold in each sale.

- **Columns**:
  - `id_detail` (Primary Key): Unique identifier for the sale detail.
  - `id_sale` (Foreign Key): Reference to the `sales` table.
  - `quantity`: Quantity of items sold.
  - `price`: Price of the items sold.


### 7. `supplier` Table
Stores supplier details.

- **Columns**:
  - `id_supplier` (Primary Key): Unique identifier for the supplier.
  - `name`: Name of the supplier.
  - `address`, `city`, `postal_code`, `country`: Location details of the supplier.
  - `phone` & `fax`: Contact information for the supplier (optional).
  - `TIN`: Tax identification number (unique).
 

### 8. `brands` Table
Tracks referral sources for the brands that the optitian works with.

- **Columns**:
  - `id_brand` (Primary Key): Unique identifier for the brands source.
  - `name`: Name of the brand.
  - `id_supplier` (Foreign Key): Reference to the supplier in the `supplier` table.



## Setup

1. Create the database schema by executing the provided SQL script.
2. Insert the data into the respective tables.
3. Ensure all foreign key relationships and constraints are maintained.

