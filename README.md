# PostgreSQL Course - Free Code Camp

## 1. Clear PostgreSQL console

To clear the PostgreSQL console, you can use the command:

```bash
\! clear
```

## 2. Command to login to PostgreSQL

To log in, you can use the following command:

```bash
psql --username=freecodecamp --dbname=postgres
```

This will change the prompt, then you can use `\l` to see the available databases.

## 3. List available databases

To list the available databases, use the command:

```bash
\l
```

## 4. Create your own database

To create your own database, you can use the command:

```sql
CREATE DATABASE database_name;
```

It's important that the database name is in lowercase and that you end the statement with a semicolon `;`.

## 5. Connect to a database

To connect to a database, use the command:

```bash
\c database_name
```

This will change the prompt to the name of the database you connected to.

## 6. Show tables

To show the tables in the database, use the command:

```bash
\d
```

## 7. Create a table

You can create a table with the following command:

```sql
CREATE TABLE first_table();
```

## 8. View table details

To view table details, use the command:

```bash
\d table_name
```

## 9. Add a column to a table

You can add a column to an existing table with the command:

```sql
ALTER TABLE table_name ADD COLUMN column_name DATATYPE;
```

## 10. Drop a column from a table

To drop a column, use the following command:

```sql
ALTER TABLE table_name DROP COLUMN column_name;
```

## 11. Rename a column

To rename a column in a table, you can use the following command:

```sql
ALTER TABLE table_name RENAME COLUMN column_name_old TO new_name;
```

## 12. Insert data into a table

To insert data into a table, use the following command:

```sql
INSERT INTO table_name(column_1, column_2) VALUES(value1, value2);
```

If a column expects `VARCHAR` data, make sure to enclose the value in single quotes, for example: `'jair'`.

## 13. Query data from a table

To query data from a table, use the `SELECT` statement:

```sql
SELECT columns FROM table_name;
```

To select multiple columns, use:

```sql
SELECT id, name FROM characters;
```

## 14. Delete a row

To delete a row from a table, you can use the following command with a condition:

```sql
DELETE FROM table_name WHERE username='Luigi';
```

## 15. Drop a table

To drop a table, use the following command:

```sql
DROP TABLE table_name;
```

## 16. Rename a database

You can rename a database using the following command:

```sql
ALTER DATABASE database_name RENAME TO new_database_name;
```

## 17. Use of SERIAL type

The `SERIAL` type turns your column into an `INT` with a `NOT NULL` constraint, and it automatically increments when a new row is added.

## 18. Insert multiple rows

To insert multiple rows into a table, use the following command:

```sql
INSERT INTO characters(name, homeland, favorite_color)
VALUES
('Mario', 'Mushroom Kingdom', 'Red'),
('Luigi', 'Mushroom Kingdom', 'Green'),
('Peach', 'Mushroom Kingdom', 'Pink');
```

## 19. Update values in a table

If you make a mistake, you can change a value with the following command:

```sql
UPDATE table_name SET column_name=new_value WHERE condition;
```

## 20. Order query results

You can order query results with `ORDER BY`:

```sql
SELECT columns FROM table_name ORDER BY column_name;
```

## 21. Add a primary key

To add a `PRIMARY KEY`, use this command:

```sql
ALTER TABLE table_name ADD PRIMARY KEY(column_name);
```

## 22. Drop a constraint

To drop a constraint from a table, use the following command:

```sql
ALTER TABLE table_name DROP CONSTRAINT constraint_name;
```

## 23. NUMERIC data type

In PostgreSQL, `NUMERIC(4, 1)` is used to store numbers with specified precision and scale.

- 4: Precision, the total number of digits.
- 1: Scale, the number of digits to the right of the decimal point.

Examples of valid values:

- `999.9`
- `12.3`
- `0.1`

It cannot store values like `1000.0`, as it exceeds the 4 digits allowed.

## 24. Foreign key

To create a foreign key to relate two tables, you can use the following command:

```sql
ALTER TABLE table_name
ADD COLUMN column_name DATATYPE
REFERENCES referenced_table_name(referenced_column_name);
```

Example:

```sql
ALTER TABLE sounds ADD COLUMN character_id INT NOT NULL REFERENCES characters(character_id);
```

## 25. One-to-one relationship with UNIQUE constraint

You can enforce a one-to-one relationship using a `UNIQUE` constraint:

```sql
ALTER TABLE table_name ADD UNIQUE(column_name);
```

## 26. NOT NULL constraint

To ensure a column cannot have `NULL` values, use the following command:

```sql
ALTER TABLE table_name ALTER COLUMN column_name SET NOT NULL;
```

## 27. Select multiple columns

To select multiple columns, separate the column names with a comma:

```sql
SELECT character_id, name FROM characters;
```

## 28. Insert a row with specific data

Example of inserting a row with values:

```sql
INSERT INTO more_info(birthday, height, weight, character_id)
VALUES('1981-07-09', 155, 64.5, 1);
```

## 29. Query with condition

To query rows with a specific condition:

```sql
SELECT columns FROM table_name WHERE condition;
```

## 30. Order table by a column

To order a table by a specific column:

```sql
SELECT columns FROM table_name ORDER BY column;
```

## 31. Create a table with a primary key

Example of creating a table with a `SERIAL` primary key:

```sql
CREATE TABLE sounds(sound_id SERIAL PRIMARY KEY);
```

## 32. Many-to-many relationship with junction table

For a many-to-many relationship, create a junction table:

```sql
CREATE TABLE character_actions (
  character_id INT,
  action_id INT,
  PRIMARY KEY (character_id, action_id)
);
```

## 33. Add a foreign key to an existing column

To add a foreign key to an existing column:

```sql
ALTER TABLE character_actions ADD FOREIGN KEY (character_id) REFERENCES characters(character_id);
```

## 34. Composite primary key

To create a primary key using two columns (composite key):

```sql
ALTER TABLE table_name ADD PRIMARY KEY(column1, column2);
```

## 35. FULL JOIN command

To retrieve data from two tables using a `FULL JOIN`:

```sql
SELECT * FROM characters FULL JOIN sounds ON characters.character_id = sounds.character_id;
```
