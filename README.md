---
title: CassandraDB Delete Activity
---

# CassandraDB Delete Activity
This activity allows you to delete a record from particular table from the CassandraDB server

## Installation
### Flogo CLI
```bash
flogo install github.com/dhire05/cassandradeleterecord
```

## Schema
Inputs and Outputs:

```json
{   
  "inputs":[
    {
      "name": "ClusterIP",
      "type": "string",
	  "required": true      
    },
	{
      "name": "Keyspace",
      "type": "string",
      "required": true
    },
	{
      "name": "TableName",
      "type": "string",
      "required": true
    },
	{
      "name": "Where",
      "type": "string",
      "required": true
    }
  ],
  "outputs": [
    {
      "name": "result",
      "type": "any"
    }
  ]
 }
```
## Settings
| Setting        | Required | Description |
|:---------------|:---------|:------------|
| ClusterIP      | True     | The CassandraDB cluster instance |         
| Keyspace       | True     | The name of the Keyspace
| TableName      | True     | The name of table to delete record
| Where          | True     | The where clause or condition |

## Example
The below example is to delete record from CassandraDB

```json
{
  "id": "CassandraDB_1",
  "name": "CassandraDB connector",
  "description": "Delete record from CassandraDB",
  "activity": {
    "ref": "github.com/dhire05/cassandradeleterecord",
    "input": {
      "ClusterIP": "127.0.0.1",
      "Keyspace": "sample",
      "TableName": "employee",
      "Where": "empid = 101"      
    }
  }
}
```