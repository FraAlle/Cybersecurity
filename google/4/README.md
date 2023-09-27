## Linux FHS(File Hierarchy Standard)

*   /home: Each user in the system gets their own home directory.

*   /bin: This directory stands for “binary” and contains binary files and other executables.

*   /etc: This directory stores the system’s configuration files.

*   /tmp: This directory stores many temporary files.

*   /mnt: This directory stands for “mount” and stores media, such as USB drives and hard drives.

## SQL

Foreign key: primary key in another table.
While filtering sql querrys, the % means for any number of others charcters, the _ means only 1 other character(__ means 2, ___ means 3 etc).
Query example: `select * from X where Y='A' and Z like 'Something%' or W like 'Some%'`
INNER JOIN: returns rows matching on a specified columns that exist in more than 1 table.
`SELECT * FROM employees INNER JOIN machines ON employees.device_id = machines.device_id;`
OUTER JOIN: each type of outer join returns all rows from either one table or both tables.
*   LEFT JOIN: returns all of the records of the first table, but return only rows of the second table that match on a specific column.
`SELECT * FROM employees LEFT JOIN machines ON employees.device_id = machines.device_id;`
*   RIGHT JOIN: returns all of the records of the second table but only returns rows of the first table that match on a specified column.
`SELECT * FROM employees RIGHT JOIN machines ON employees.device_id = machines.device_id;`
*   FULL OUTER JOIN: returns all records from both tables.
`SELECT * FROM employees FULL OUTER JOIN machines ON employees.device_id = machines.device_id;`
`COUNT` output the number of rows from a query.`SELECT COUNT(name)....`
`AVG` returns a single number that represents the average of the numerical data in a column.
`SUM` returns a single number that represents the sum of the numerical data in a column.