# Database Fundamentals with Pandas

A practical Jupyter Notebook covering fundamental relational database concepts and their equivalent operations in **Pandas**.

The goal of this repository is to build a practical understanding of how common **SQL and relational database concepts** translate into Python/Pandas workflows used in data analysis and data preparation.

## Topics Covered

* **Database Fundamentals**

  * Types of databases
  * Tables and records
  * Relational database concepts
  * Database query execution

* **Keys & Relationships**

  * Primary Keys
  * Foreign Keys
  * One-to-Many relationships
  * Relationships between tables

* **SQL → Pandas**

  * `SELECT`
  * Selecting specific columns
  * Filtering with `WHERE`
  * Sorting
  * Aggregation
  * Grouping
  * Counting records
  * Joining tables

* **Pandas Operations**

  * DataFrame creation
  * Column selection
  * Boolean filtering
  * `value_counts()`
  * `groupby()`
  * `merge()`
  * Working with multiple related DataFrames

## Practical Focus

The notebook uses small database-like DataFrames such as **customers** and **orders** to demonstrate how relational data can be represented and manipulated in Pandas.

For example:

```text
customers
    │
    │ customer_id
    ▼
orders
```

This allows SQL concepts such as:

```sql
SELECT *
FROM orders
WHERE quantity > 1;
```

to be understood alongside their Pandas equivalents.

## SQL and Pandas Mapping

| SQL / Database Concept | Pandas Equivalent         |
| ---------------------- | ------------------------- |
| Table                  | `DataFrame`               |
| Column                 | `Series`                  |
| `SELECT *`             | `df`                      |
| `SELECT column`        | `df['column']`            |
| `SELECT col1, col2`    | `df[['col1', 'col2']]`    |
| `WHERE`                | Boolean filtering         |
| `GROUP BY`             | `groupby()`               |
| `COUNT()`              | `count()` / `size()`      |
| `ORDER BY`             | `sort_values()`           |
| `JOIN`                 | `pd.merge()`              |
| Primary Key            | Unique identifier column  |
| Foreign Key            | Related identifier column |

## Example

A simple relational structure is represented using Pandas:

```python
customers = pd.DataFrame({
    'customer_id': [1, 2, 3, 4],
    'name': ['John Doe', 'Jane Smith', 'Bob Johnson', 'Alice Brown'],
    'email': [
        'john@example.com',
        'jane@example.com',
        'bob@example.com',
        'alice@example.com'
    ]
})

orders = pd.DataFrame({
    'order_id': [101, 102, 103, 104, 105],
    'customer_id': [1, 2, 1, 3, 4],
    'product': ['Widget A', 'Widget B', 'Widget C', 'Widget A', 'Widget B'],
    'quantity': [2, 1, 3, 1, 2]
})
```

The relationship between the two tables is established through `customer_id`, demonstrating the practical relationship between a primary key and a foreign key.

## Repository Purpose

This repository is part of my ongoing preparation for **Data Science and Machine Learning**.

Understanding SQL and relational databases alongside Pandas is important for working with real-world datasets, where data is often distributed across multiple related tables.

The exercises focus on building practical intuition for:

* Working with structured data
* Understanding relational data
* Translating SQL logic into Pandas
* Combining data from multiple tables
* Preparing data for analysis and Machine Learning workflows

## Tools

* Python
* Pandas
* Jupyter Notebook
* SQL concepts
* Relational databases

## Notebook

[Data_Base_Fundamental.ipynb](./Data_Base_Fundamental.ipynb)

**Status:** Work in Progress
