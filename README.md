MongoDB is a NoSQL database{key-value database} that stores data in JSON-like documents instead of traditional relational tables. It is widely used for its scalability, flexibility, and high performance.
**Features:**
Schema-less – No predefined schema like SQL databases.
Document-Oriented – Stores data as BSON (Binary JSON) documents.
Scalability – Easily handles large amounts of data using sharding.
High Performance – Fast read and write operations.
Indexing – Supports indexing for faster queries.
Replication – Uses replica sets for high availability.
Aggregation Framework – Allows complex queries and analytics.

**Document Orineted Database:**
provides API's or a query/update language that exposes the ability to query or update based on the internal structure in the document.
Mongodb documents are composed of filed and value pairs 
{
   field1:value1,
   field2:value2
}

commands:
show databases -  list all databases in MongoDB
use <database-name>  - select the database workspace as current working DB
If not it will create but it will not display till we add some collection or data inside it
db -  show you the database you are currently working in
find() //Return all the documents
findOne // returns only 1t document


Languages supported by Mongodb:
PHP
Node JS
Python
Java
C#
C++
Database:Collection of data{Physical container for collections}
Mongodb server can hosts multiple databases 
1 or more collections together become a database
Collections:Group of MongoDB Documents[No JOINS Concept]
Instead of joins we use aggregations in MongoDB
do NOT enforce any schema
Document: Set of "key-value" pairs
Every document in MongoDB has a unique value via Key "_id"
Have dynamic schema-they can be same or different
MongoDB will add a key automatically for each document -_id
User defined schema in MongoDB document and they are NOT static or fixed

**Creating AND Dropping Databases:**
Creating Database *use <database-name>
Remove database -db.dropDatabase()
Creating and Dropping Collecions:
*Creating Collections: db.createCollection(name,options)
*Dropping Collections: db.collection.drop()
**Datatypes in MongoDB:**
BSON
JSON
Integer
Boolean
Double
Arrays
Object
Null 
Date
Timestamp
Object Id
Code

**Inserting Documents into Collections **
used for creating new documents inside the collections
To insert any document into Collection
* Db.<collection-name>.insert({"name":"Hemalatha"})
To insert many documents at once into collection
*  Db.<collection-name>.insertMany(
   {"name":"Hemalatha"}
   {"name":"Latha"}
   )  
Every document that we insert will have a unique key "_id"
- the value for this is always unique and 24 character
- _id is a Primary Key in your collection

Updating Documents into Collections:
*Update
*updateOne
*updateMany
Db.<collection-name>.update(
{"name":"HEMALATHA"},
{
   $set:{
       "key":"value"
       }
})

**Read Data From Collection*** 
multiple ways to read data from collection
find() - finds all documents in collection
db.collection.find()
findOne()-find first document in collection
find({"key1":"value","key2":"value2"}) - by setting query conditions
findOneAndReplace({"key1":"value","key2":"value2"}, <replacement>)
findOneAndDelete({"key1":"value", "key2": "value2"})
**Delete documents from Collections**
Multiple ways to Delete data from collection
deleteOne() //delete only one document
deleteMany({}) //delete many documents at once
when passed with empty curly brace - it will delete all documents in collections

**CRUD OPERATIONS**
-Create/Insert Documents into Collections
-Read documents from Collections
-Update documents from Collections
-Delete documents from Collection

**Conditions in Find Method:**
Using multiple operations inside the find method
Using operations we add more search power to Find method
Various conditions that can be used are:
* Equality
* Less Than
* Less than equal
* Greater than
* Greater than Equal
* Not Equal
**Operations inside Find Method**
  All conditions "MUST" be satisfied in order to return the document
  $and - AND Operation
  Match all conditions mentioned in the Find method
  $or - OR operation
  Match any condition in the find method
**Queries**
  using find method of MongoDB with operators
  -Eq
  -lt - less than
  -lte - less than equal
  -gt - greater than
  -gte - greater than equal
  
 **Selecting Fields**
 db.leads.find() - all documents are returned
 
 **Projections in MongoDB**
 By default it will bring up all keys/values from all documents in collections
 Another name for selecting fields for showing or hiding
 specify the field as "1" or "0"
 
 **Aggregation:**
 Similar to find command, where you can provide the criteria for your query in the form of JSON documents
 pipeline-key element in aggregation
 helps in performing operations like min,max,sum etc.
 db.leads.aggregate(pipeline,options)
 Pipeline - sequence of data aggregation operations or stages
 pipeline is an array

 Valid aggregation stages:
 * $count
 * $group
 * $limit
 * $lookup
 * $match
 * $merge
 * $sort
 * $project
 * $unwind
 * $unset
pipeline = [
{...},
{...},
{...},
];
db.leads.aggregate(pipeline);

**Limit and Skip in MongoDB**
we may not always want all documents all the time
db.collection.find().limit(4)
we may want to skip some documents we don't need  (skip will skip sequentially not random)
db.collection.find().skip(3);

 **Sorting in MongoDB**
 sort the record set before passing it to next logical operation
 db.collection.find().sort({"leadName":1})
 1:ascending
 -1:descending
 
**Index:**
fastest way to find information

**Back Up & Restore**
Steps to create back up of MongoDB Data:
create a folder where you want to save your data
run the command "mongodump.exe"
verify the data dump and folder dumped correctly

Steps to create Restore of MongoDB Data:
got the backup of the data dump from MongoDB
run the command "mongorestore.exe"
verify the data dump and folder dumped correctly
