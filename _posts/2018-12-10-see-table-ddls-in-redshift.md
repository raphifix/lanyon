---
published: false
---
Sometimes it's useful or necessary to see how a particular table was created. Some SQL IDEs have a feature to see DDLs (data definition language) for individual tables, but what if you want to see DDLs for multiple tables? In redshift, it's easy:

`SELECT * FROM admin.v_generate_tbl_ddl;`