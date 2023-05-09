# **DVD_Rental_Store_MySQL_Project**
## **Introduction**
This MySQL project involves answering 8 questions that require joining data from multiple tables in a relational database. The database contains tables of data on customers, stores, inventory, staff, and films. This readme document provides a brief overview of the thought process behind each query and the resulting SQL code.

### **Question 1**
#### `Problem Statement`
My partner and I want to come by each of the stores in person and meet the managers. Please send over the managers’ names at each store, with the full address of each property (street address, district, city, and country please).

#### `Thought Process`
- We need to select the full name of the manager from the staff table. Then, we need to select the address information from the address table. We can perform an inner join to join both tables for the result output.

#### `Query 1`
<img src="https://github.com/Symo-Stuart/DVD_Rental_Store_MySQL_Project/blob/main/Query%201.png">

### **Question 2**
#### `Problem Statement`
I would like to get a better understanding of all of the inventory that would come along with the business. Please pull together a list of each inventory item you have stocked, including the store_id number, the inventory_id, the name of the film, the film’s rating, its rental rate and replacement cost.

#### `Thought Process`
- We need all the film information from the film table.
- We need to know how many of each we have in our inventory and which store they are from the inventory table.
- We have to join the inventory table on the film table for our out put.

#### `Query 2`
<img src="https://github.com/Symo-Stuart/DVD_Rental_Store_MySQL_Project/blob/main/Query%202.png">

### **Question 3**
#### `Problem Statement`
From the same list of films you just pulled, please roll that data up and provide a summary level overview of your inventory. We would like to know how many inventory items you have with each rating at each store.

#### `Thought Process`
- From the list we just pulled up, all we need to do is add a count of the inventory_ids then group them by store_id and rating.

### `Query 3`
<img src="https://github.com/Symo-Stuart/DVD_Rental_Store_MySQL_Project/blob/main/Query%203.png">

### **Question 4**
#### `Problem Statement`
Similarly, we want to understand how diversified the inventory is in terms of replacement cost. We want to see how big of a hit it would be if a certain category of film became unpopular at a certain store. We would like to see the number of films, as well as the average replacement cost, and total replacement cost, sliced by store and film category.

#### `Thought Process`
- Our Query requires information from 2 tables that don't have a common key to join them. We know that the requirement of joining 2 tables is having a common field, so, how do we do this? We use what's called a bridge join. This is where we use a 3rd table in our join that cointains common fields with both the tables we primarily want to join. In this case the film_category table which joins on the film table through film_id and on the category table through category_id hence acting as a bridge.

#### `Query 4`
<img src="https://github.com/Symo-Stuart/DVD_Rental_Store_MySQL_Project/blob/main/Query%204.png">

### **Question 5**
#### `Problem Statement`
We want to make sure you folks have a good handle on who your customers are. Please provide a list of all customer names, which store they go to, whether or not they are currently active, and their full addresses – street address, city, and country.

#### `Thought Process`
- Same scenario as the query before. In this case the city table acts as the bridge between the address and the country tables.

#### `Query 5`
<img src="https://github.com/Symo-Stuart/DVD_Rental_Store_MySQL_Project/blob/main/Query%205.png">

### **Question 6**
#### `Problem Statement`
We would like to understand how much your customers are spending with you, and also to know who your most valuable customers are. Please pull together a list of customer names, their total lifetime rentals, and the sum of all payments you have collected from them. It would be great to see this ordered on total lifetime value, with the most valuable customers at the top of the list.

#### `Thought Process`
- The most important aspect to note here is the order of the out put. We are required to have the most valuable customers on top. Meaning we need our output to be ordered by the total amount a given customer has spent on our store Descending .

#### `Query 6`
<img src="https://github.com/Symo-Stuart/DVD_Rental_Store_MySQL_Project/blob/main/Query%206.png">

### **Question 7**
#### `Problem Statement`
My partner and I would like to get to know your board of advisors and any current investors. Could you please provide a list of advisor and investor names in one table? Could you please note whether they are an investor or an advisor, and for the investors, it would be good to include which company they work with.

#### `Thought Process`
- In this query we are required to do a union instead of a join. The top requirement for a union is that our tables have to have the same number of columnns with similar data types. In this case our advisor table has only 2 columnbs hence replacing the third column with a "null" in order for the union to execute.

#### `Query 7`
<img src="https://github.com/Symo-Stuart/DVD_Rental_Store_MySQL_Project/blob/main/Query%207.png">

### **Question 8**
#### `Problem Statement`
We're interested in how well you have covered the most-awarded actors. Of all the actors with three types of awards, for what % of them do we carry a film? And how about for actors with two types of awards? Same questions.  Finally, how about actors with just one award?

#### `Thought Process`
- For this query the "count" clause has it's limitations hence the "Case when". This clause helps us categorise our given records in a coulmn and aggregate them to a singular record in another column. For instance We have the clause looking through the awards coulmn and counting the number of awards for a singular actor, then out putting it as a percentage of actors with a given number of awards in our film inventory.

#### `Query 8`
<img src="https://github.com/Symo-Stuart/DVD_Rental_Store_MySQL_Project/blob/main/Query%208.png">