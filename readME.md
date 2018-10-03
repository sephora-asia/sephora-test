# Data Warehouse Architect Position at Sephora

You can write your code in the language of your choice. But we have preferences for the language of our stack:

- Go (Highly recommended)
- Python
- NodeJS

Please organise, document and write some tests.
Also precise if a specific setup is required to make your code run.

## Context
At Sephora SEA, we are building business schemas on top of the ecommerce databases.
For instance, we have a products table which is the consolidation of 30 different tables from the databases and contains the information for each product. This clean schema is created from a bunch of dependent SQL scripts and is used accross the company.

- We are pulling tables from the ecommerce databases and are pushing the exact copy to a raw dataset. (raw folder)
- We are cleaning and consolidating the data on top of the raw tables using SQL scripts stored in the tmp folder. The result of the tmp.inventory_items.sql script will be stored in the tmp.inventory_items table.
- The products tables in the (from the final.products.sql script) is the final clean table created.

## Data structure

1. Write a clean structure (from scratch, no external library!) that show the dependencies between all the scripts.
2. How would you run the scripts in order? Code it and test it.

*Going further, we would like to parallelize the execution of few of these scripts. If you think of the dependencies as a tree: scripts from different nodes can work simultaneously, but, still, must not be executed before its children's tasks are done.*

3. If you had to parallelize these tasks' executions, how would you do that?
4. Apply on your structure, and test it

*Sample of task function (in js):

```js
function tmp_inventory_items (callback){
    // This is execution time of the tmp.inventory_items script
    setTimeout(callback, parseInt(1000 * Math.random()));
}
```