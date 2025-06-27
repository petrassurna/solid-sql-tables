# Solid SQL Tables

> Because product fields should be real SQL columns — not blobs, not JSONB, and definitely not WordPress-style postmeta.

**Solid SQL Tables** is a runtime schema engine for SQL Server that reads JSON definitions and creates actual, strongly-typed database tables and columns.  
It's designed for structured data systems — like eCommerce and content management — where performance, clarity, and integrity matter.

---

## ✨ Why Use This?

- ✅ Create SQL Server tables dynamically at runtime
- ✅ Every field is a **real column**, not a blob or EAV record
- ✅ Define schema in JSON — clean, declarative, and versionable
- ✅ Enforced types: `nvarchar`, `decimal`, `bit`, etc. Types that are common in CMS systems like WordPress custom fields or Umbraco document types
- ✅ Built with .NET + SQL SMO

---

## 🚀 Getting Started

### 1. Define your schema

Create a `Product.schema.json` file:

```json
{
  "entity": "Product",
  "schema": "dbo",
  "fields": [
    { "name": "Id", "type": "int", "isPrimaryKey": true, "isIdentity": true },
    { "name": "Name", "type": "nvarchar", "length": 200, "nullable": false },
    { "name": "Price", "type": "decimal", "precision": 18, "scale": 2 },
    { "name": "IsPublished", "type": "bit", "default": false }
  ]
}

SchemaLoader loader = new SchemaLoader(connectionString);
loader.Apply("Product.schema.json");

### 2. Or change your schema

{
  "entity": "Product",
  "previousEntityName": "Item" 
  "schema": "dbo",
  "fields": [
    { "name": "Id", "type": "int", "isPrimaryKey": true, "isIdentity": true },
    { "name": "ProductName", "type": "nvarchar", "length": 200, "nullable": false, "previousName": "Name" },
    { "name": "Price", "type": "decimal", "precision": 18, "scale": 2,  "previousName": "Current Price" },
    { "name": "SalePrice", "type": "decimal", "precision": 18, "scale": 2, "nullable": true, "delete" : true },
    { "name": "IsPublished", "type": "bit", "default": false }
  ]
}
