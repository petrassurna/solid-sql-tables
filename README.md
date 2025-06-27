# Solid SQL Tables

> Because product fields should be real SQL columns — not blobs, not JSONB, and definitely not WordPress/Umbraco style postmeta.

**Solid SQL Tables** is a runtime schema engine for SQL Server that reads JSON definitions and creates (and modifies) actual, strongly-typed database tables and columns.  
It's designed for structured data systems — like eCommerce and content management — where performance, clarity, and integrity matter.

---

## ✨ Why Use This?

- ✅ Create SQL Server tables dynamically at runtime
- ✅ Every field is a **real column**, not a blob or EAV (entity-attribute-value) record
- ✅ Querying should be intuitive and as fast as possible, as that's what the world needs
- ✅ Define schema in JSON — clean, declarative, and versionable
- ✅ Enforced types: `nvarchar`, `int`, `float`, `datetime`, `bit`, etc. Types that are common in CMS systems like WordPress custom fields or Umbraco document types
- ✅ Built with .NET + SQL SMO

---

## 🎯 Installation

Open the solution solid-sql-tables.sln in Visual Studio 2022 or later. Start by looking at solid-sql-tables.tests/README.md which will show you how to step through the tests. The tests start simply and build in complexity. They are the fastest way to understand the library.
