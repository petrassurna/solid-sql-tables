# Solid SQL Tables – Philosophy & Design

This library creates and modifies SQL Server databases by dynamically adding tables and columns based on 
JSON definitions.


---

## 🎯 Purpose

The philosophy behind this library is to support the kind of strongly typed SQL schemas that content systems like WordPress/Umbraco *should* use — without relying on blobs, postmeta tables, or EAV patterns.


---

## 🔍 Design Principles

This library is opinionated by design:

- ✅ **Every table has an `Id` column automatically.**  
  You don’t need to define it in your JSON — it’s always there.

- ✅ **All columns are required by default.**  
  We discourage the use of nullable columns. Make data intentional.

- ✅ **A focused set of SQL types is supported.**  
  Most CMS/eCommerce systems only need a handful: `int`, `nvarchar`, `bit`, `datetime`, etc.  
  You’re welcome to contribute additional types if needed — just open a pull request!

---

💡 This approach favors **clarity**, **performance**, and **easy querying** — a sharp contrast to systems like WordPress or Umbraco that rely on `postmeta` tables and dynamic key-value blobs.

## Sample Json


For a full working example of table creation, see:  
📁 `solid-sql-tables.tests/json/all-fields.json` (incomplete)
