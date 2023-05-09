# **DVD_Rental_Store_MySQL_Project**
## **Introduction**
This MySQL project involves answering 8 questions that require joining data from multiple tables in a relational database. The database contains tables of data on customers, stores, inventory, staff, and films. This readme document provides a brief overview of the thought process behind each query and the resulting SQL code.

### **Question 1**
#### `Problem Statement`
My partner and I want to come by each of the stores in person and meet the managers. Please send over the managers’ names at each store, with the full address of each property (street address, district, city, and country please).

#### `Thought Process`
We need to select the full name of the manager from the staff table. Then, we need to select the address information from the address table. We can perform an inner join to join both tables for the result output.

#### `Query`
#### `select`
      staff.first_name,
      staff.last_name,
      address.address as street_address,
      address.district,
      address.city_id
#### `from` staff
`inner join` address
`on` address.address_id = staff.address_id;`

<img src="https://github.com/Symo-Stuart/DVD_Rental_Store_MySQL_Project/blob/main/Query%201.png">