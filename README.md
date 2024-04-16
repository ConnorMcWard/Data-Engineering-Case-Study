# ER Diagram Overview

![image](https://github.com/ConnorMcWard/Case-Study/assets/57818139/8bd0bcf6-f150-4362-80c8-9587800d3b1d)


This ERD diagram consists of four tables: **Property**, **Unit**, **Pricing**, and **Fee**. Below is a description of the relationships and fields within each table:

## 1. Property Table
- **Fields**: Property ID (PK), Property Name, Marketing Name, Full Address, Street Address, City, State Code, Postal Code, Country Code, Longitude, Latitude, Belonged City, Description, Neighborhood, Neighborhood Description, Currency Code.
- **Relationship**: Each property can have one or more associated units, establishing a one-to-many relationship with the **Unit** table.

## 2. Unit Table
- **Fields**: Unit ID (Primary Key), Property ID (Foreign Key), Room Number, Number of Bedrooms, Listing Square Footage, Unit Square Footage, Occupancy Type, Availability Date, Minimum Stay, Minimum Price, Maximum Price.
- **Relationships**:
  - **Fee**: A unit can have zero or more relationships with the **Fee** table, indicating that a unit may have none, one, or multiple fees associated.
  - **Pricing**: A unit can have one or more relationships with the **Pricing** table, meaning each unit can have one or multiple pricing entries.

## 3. Pricing Table
- **Fields**: Unit ID (Foreign Key), Name, Number of Months, Amount, Concession Description.
- **Description**: This table stores different pricing options for each unit, where each pricing entry can include potential concessions.

## 4. Fee Table
- **Fields**: Unit ID (Foreign Key), Fee Name, Description, Amount, Is Mandatory (boolean), Is Refundable (boolean).
- **Description**: The fee table records various fees associated with each unit, specifying whether each fee is mandatory and whether it is refundable.

## Deviation from 3NF
- **Explanation**: In this database design, I did not fully adhere to the third normal form. The the reason why there are individual tables for both Pricing and Fee is due to the fact that there are that there would be many redundancies in the Unit table if it was included with the Pricing and Fee table.


