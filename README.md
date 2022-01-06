# SQL-Database-cheat-sheet
I'm learning SQL and taking the notes here
## Notes  
### Commands
```CREATE DATABASE database_name;```=> Create a new database // The capitalized words are keywords telling PostgreSQL what to do, name is in lower case and each command need a semi-colon at the end  
```\l``` => list command to see the databases presents  
REMARK: if there is no message after typing a command, it mean that the command is incomplet. If you forget a semi-colon, you can put it in the line after  
```\c database_name``` => connect to the database // To be sure that we are connected, there should be a message that tell us that we are connected and the prompt need to change for the database_name instead of postgre prompt  
```\d``` => inside a database to display the tables  
```CREATE TABLE table_name();```
```\d table_name``` => show more detail about a specified table  
```ALTER TABLE table_name ADD COLUMN column_name DATATYPE;``` => Add a column with a name and a datatype  ex: ```ALTER TABLE second_table ADD COLUMN first_column INT;``` //add a column to second_table named first_column with a INT type  
```ALTER TABLE table_name DROP COLUMN column_name;``` => remove the desired column  
```ALTER TABLE table_name RENAME COLUMN column_name TO new_name;``` => rename a column  
```INSERT INTO table_name(column_1, column_2) VALUES(value1, value2);``` => add row inside the colums with the data REMARK VARCHAR is made with single quote !!  
```INSERT INTO table_name(column_1, column_2) VALUES(value1, value2),(value1a, value2a);``` => add multiple row at once  
```SELECT columns FROM table_name;``` => view the data in a table  
```SELECT * FROM table_name;``` => view all the datas in a table  
```DELETE FROM table_name WHERE condition;``` => delete a row from a condition ex: DELETE FROM second_table WHERE username='Luigi';  
```DROP TABLE table_name;``` => delete a table;  
```DROPT DATABASE database_name;``` => Delete a database;  
```ALTER DATABASE database_name RENAME TO new_database_name;``` => rename a database  
```UPDATE table_name SET column_name=new_value WHERE condition;``` => Update a row  
```SELECT columns FROM table_name ORDER BY column_name;``` => Change the order ex:```SELECT * FROM characters ORDER BY character_id;```  
```ALTER TABLE table_name ADD PRIMARY KEY(column_name);```=> set a column that uniquely identifies each row in the table // Only one per table  
```ALTER TABLE table_name DROP CONSTRAINT constraint_name;``` => remove the constrait // used to remove the primary can if we set to the wrong column REMARK: the constraint may have an other name that the column name. Exemple: ```"characters_pkey" PRIMARY KEY, btree (character_id)``` here, the constraint name is ```characters_pkey```  
```ALTER TABLE table_name ADD COLUMN column_name DATATYPE REFERENCES referenced_table_name(referenced_column_name);``` => Used to connect database between them. It is to add a foreign key  
```ALTER TABLE table_name ADD UNIQUE(column_name);``` => add it to the foreign key to enforce the relation one-to-one. Normaly it's already but it's better to do it to make sure that one row in the table A is exactly one row in table B  
```ALTER TABLE table_name ALTER COLUMN column_name SET NOT NULL;``` => Set a colum not null. Used with relationnal database. If a table A is connected to a table B, it isn't possible to have a row A without a row B  
``````  
``````  


### Types  
```INT```  
```VARCHAR(30)``` => string type // Need to give a maximum length when using it, here it's 30 REMARK VARCHAR is made with single quote while writting data inside  
```SERIAL``` => The SERIAL type will make your column an INT with a NOT NULL constraint, and automatically increment the integer when a new row is added  
```NOT NULL``` => Add NOT NULL after the colum type to avoid null data ex: ALTER TABLE characters ADD COLUMN name VARCHAR(30) NOT NULL;  
```DATE```  => DATE  
```NUMERIC(4,1)``` => Data type for decimal up to 4 digit and 1 is to the right of the decimal  
