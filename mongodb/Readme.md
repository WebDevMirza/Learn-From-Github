###### MongoDB 

<div align="center">
    <img src="./assets/logo.svg" alt="MONGODB" width="150" height="auto"/>
    <h1>Welcome to MongoDB Practice</h1>
</div>

<details open>
    <summary><h2>Table of Contains</h2></summary>
    <ol>
        <li>
            <a href="#about-mongodb">About MongoDB</a>
            <ul>
                <li><a href="#common-operations-of-mongodb">Common Operations of MongoDB</a></li>
                <li><a href="#common-backend-technologies-and-their-frameworks">Common Backend Technologies and Their Frameworks</a></li>
            </ul>
        </li>
        <li>
            <a href="#getting-started">Getting Started</a>
            <ul>
                <li><a href="#downloading-and-installing">Downloading and Installing</a></li>
                <li><a href="#terminology">Terminology</a></li>
                <li><a href="#basic-commands">Basic Commands</a></li>
            </ul>
        </li>
        <li>
            <a href="#mongodb-crud-operations">MongoDB CRUD Operations</a>
            <ul>
               <li>
                    <a href="#insert-documents">Insert Documents</a>
                    <ul>
                        <li><a href="#practice-insert">Practice Insert</a></li>
                        <ul>
                            <li><a href="#step-1-general-import">Step-1: General Import</a></li>
                            <li><a href="#step-2-insert-documents-by-importing-files">Step-2: Insert Documents by Importing Files</a></li>
                        </ul>
                    </ul>
               </li>
               <li>
                    <a href="#query-documents">Query Documents</a>
                    <ul>
                        <li><a href="#practice-query">Practice Query</a></li>
                        <ul>
                            <li><a href="#step-1-to-import-json-file">Step-1: To import json file</a></li>
                            <li><a href="#step-2-basic-query-selections">Step-2: Basic query selections</a></li>
                            <li><a href="#step-3-comparison-query-selections">Step-3: Comparison query selections</a></li>
                            <li><a href="#step-4-logical-query-selections">Step-4: Logical query selections</a></li>
                            <li><a href="#step-5-element-query-selections">Step-5: Element query selections</a></li>
                            <li><a href="#step-6-regex-query-selections">Step-6: Regex query selections</a></li>
                            <li><a href="#step-7-query-selections-for-object">Step-7: Query selections for object</a></li>
                            <li><a href="#step-8-query-selections-for-array">Step-8: Query selections for array</a></li>
                        </ul>
                    </ul>
               </li>
               <li>
                    <a href="#update-documents">Update Documents</a>
                    <ul>
                        <li><a href="#practice-update">Practice Update</a></li>
                        <ul>
                            <li><a href="#step-1-using-updateone---">Step-1: Using .updateOne({ }, { })</a></li>
                            <li><a href="#step-2-using-updatemany---">Step-2: Using .updateMany({ }, { })</a></li>
                            <li><a href="#step-3-using-updateone-----">Step-3: Using .updateOne({ }, { }, { })</a></li>
                            <li><a href="#step-4-using-replaceone---">Step-4: Using .replaceOne({ }, { })</a></li>
                        </ul>
                    </ul>
               </li>
               <li>
                    <a href="#delete-documents">Delete Documents</a>
                    <ul>
                        <li><a href="#practice-delete">Practice Delete</a></li>
                        <ul>
                            <li><a href="#step-1-using-deleteone-">Step-1: Using .deleteOne()</a></li>
                            <li><a href="#step-2-using-deletemany-">Step-2: Using .deleteMany()</a></li>
                        </ul>
                    </ul>
               </li>
            </ul>
            <li><a href="#conclusion">Conclusion</a></li>
            <li><a href="#author">Author</a></li>
            <li><a href="#contributions">Contributions</a></li>
        </li>
    </ol>

</details>

<!-- ABOUT Mongodb -->

# About MongoDB

MongoDB is a popular open-source **document-oriented database** system that uses a flexible, JSON-like format to store data in collections of documents. It is designed to be scalable, high-performance, and easy to use, making it a popular choice for developers building modern web and mobile applications.

MongoDB is a **backend technology**, specifically a database management system, that is used to store and manage data for web and mobile applications. It is typically accessed and manipulated using a backend programming language such as Node.js, Express.js, PHP, or Python etc. Its primary role is to handle the storage and retrieval of data on the server-side, making it a backend technology.

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

## Common Operations of MongoDB

- Storing Data
- Retrieving Data
- Updating Data
- Deleting Data

Overall, **CRUD (Create, Read, Update, Delete)** operations are fundamental to working with databases, including MongoDB. These operations allow you to create, read, update, and delete data as needed, providing a basic set of tools for managing data stored in MongoDB collections.

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

## Common Backend Technologies and Their Frameworks

Several common backend technologies and their associated frameworks for MongoDB are listed below:
| Backend Technology | Frameworks |
|--------------------|---------------|
| Node.js | Express.js |
| Python | Flask, Django |
| PHP | Laravel |

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

# Getting Started

In this article, I use `MongoDB Community Server v6.0.5`, `MongoDB Shell v1.8.0` and `MongoDB Command Line Database Tools v100.7.0`

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

## Downloading and Installing

- **MongoDB Community Edition**
  - [MongoDB Community Server](https://www.mongodb.com/try/download/community)
- **Tools**
  - [MongoDB Shell](https://www.mongodb.com/try/download/shell)
  - [MongoDB Command Line Database Tools](https://www.mongodb.com/try/download/database-tools)

After installing, add MongoDB binaries to the System PATH `C:\Program Files\MongoDB\Server\6.0\bin`. Now open terminal and type `mongosh`. If everything is okay, you should see a version number. Now you are ready to go.

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

## Terminology

There are four main basic terminologies exists that need to know before move ahead: `database`, `collections`, `documents`, and `fields`.

- `Database`: Holds `collections`. MongoDB database server can store multiple databases.
- `Collections`: Holds `documents` set. It is like a table in relational database.
- `Documents`: Holds `fields` and their associate `value`.
- `Fields`: Fields carry a value in the form of `string`, `number`, `boolean`, `array`, or even an `object`.

> Several key-value pairs constitute a document familiar as a unit of mongoDB database.

<img src="https://www.mongodb.com/docs/manual/images/crud-annotated-document.bakedsvg.svg" alt="document and field example"/>

Some important terminologies can be learnt if you wish: `_id`

- `_id`: The unique field of the mongoDB database system that carries an auto generated id if it is not given while creating a document. It is like a primary key.

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

## Basic Commands

<details>
      <summary>1. What should you write in the terminal to enter mongosh shell?</summary>

```js
mongosh;
```

</details>

<details>
      <summary>2. Show all the databases.</summary>

```js
show dbs
```

> Newly created empty collection database will not show.

</details>

<details>
      <summary>3. Create or Access a database named <code>studentdb</code>.</summary>

```js
use studentdb
```

> if `studentdb` exists, you will get accessed otherwise it will create a new one and give access.

</details>

<details>
      <summary>4. Get the current database name.</summary>

```js
db;
```

</details>

<details>
      <summary>5. Clear terminal.</summary>

```js
cls;
```

</details>

<details>
      <summary>6. Show all the collections in <code>studentdb</code> database.</summary>

```js
show collections
```

> If any collection exists, it will show, otherwise it shows a blank line.

</details>

<details>
      <summary>7. Insert some data: <code>students</code> as a collection, and the following table data.</summary>
      
| name | age | class | group   |
|------|-----|-------|---------|
| John | 12  | V     | General |
      
```js
db.students.insertOne({name: "John", age: 12, class: "V", group: "General"})
```

> Now we can notice a collection named `students` by running `show collections` as we just created a new document with four fields.

</details>

<details>
      <summary>8. Show the newly added fields and their value.</summary>

```js
db.students.find();
```

</details>

<details>
      <summary>9. How can you count total number of available documents in this collection?</summary>

```js
db.students.countDocuments();
```

</details>

<details>
      <summary>10. Let's say, we do not want this database. Thus, can you delete the entire database you've just created?</summary>

```js
db.dropDatabase();
```

</details>

<details>
      <summary>11. Exit the mongosh shell.</summary>

```js
exit;
```

</details>

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

# MongoDB CRUD Operations

CRUD stands for Create, Read, Update, and Delete, which are the four basic operations performed on data in a database like mongoDB. By performing these operations, you can create, retrieve, modify, and delete data in a structured way, making it easier to build robust and scalable applications.

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

## Insert Documents

We can manually insert data into a MongoDB collection using the `insertOne()` or `insertMany()` methods in the MongoDB shell or through a MongoDB driver in our application code. In both cases, if there is no collection exists before, it will create a new collection.

- `insertOne()`: This can create only one document at a time with one or several key-value pairs.

- `insertMany()`: This can take more than one documents in the form of an array.

> If no `ID` is provided, it creates automatically in both cases.

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

### Practice Insert

##### **Step-1: General Import:**

<details>
      <summary>1. Insert the following table data in <code>students</code> collection. Add the first two documents by using <code>insertOne()</code> method, and then using <code>insertMany()</code> method for the rest.</summary>
      
| name      | age | class | group   |
|-----------|-----|-------|---------|
| John      | 12  | V     | general |
| Olivia    | 11  | IV    | general |
| Noah      | 12  | V     | general |
| Charlotte | 15  | VIII  | general |
| Amelia    | 16  | IX    | science |

```js
db.students.insertOne({name: "John", age: 12, class: "V", group: "general"})

db.students.insertOne({name: "Olivia", age: 11, class: "IV" group: "general"})

db.students.insertMany([
      {name: "Noah", age: 12, class: "V", group: "general"},
      {name: "Charlotte", age:15, class: "VII", group: "general"},
      {name: "Amelia", age: 16, class: "IX", group: "science"}])

```

</details>

<details>
      <summary>2. Insert some data by using the following json object.</summary>

```json
{
  "name": "John Smith",
  "age": 35,
  "email": "john.smith@example.com",
  "address": {
    "street": "123 Main St",
    "city": "Anytown",
    "state": "CA",
    "zip": "12345"
  },
  "hobbies": ["reading", "traveling", "sports"],
  "isActive": true
}
```

```js
db.students.insertOne({
  name: "John Smith",
  age: 18,
  email: "sample@example.com",
  address: { street: "123 Main St", city: "Anytown", state: "CA", zip: 12345 },
  hobbies: ["reading", "traveling", "sports"],
  isActive: true,
});
```

> We can populate data into a collection in the form of `string`, `number`, `boolean`, `array`, `object` etc.

</details>

<details>
      <summary>3. Insert the following table data in <code>students</code> collection.</summary>
      
| name      | age | class | group   | hobbies                      | Active | Address                                                            |
|-----------|-----|-------|---------|------------------------------|--------|--------------------------------------------------------------------|
| Charlotte | 15  | VIII  | general |                              |        |                                                                    |
| Charlotte | 17  | X     | science | studying, playing, gardening |        |                                                                    |
| Benjamin  | 14  | IX    | arts    |                              | true   |                                                                    |
| Rowan     | 10  | III   | general |                              |        | street: 2416 Roosevelt,</br>city: San Francisco,</br>zipcode: 94108 |

> Here we see, two charlottes in a school, and several blank fields in each document as well. In relational database system, the entry of such type of data is hard, while it is very simple and easy to entry this kind of data in mongoDB.

```js
db.students.insertMany([
  { name: "Charlotte", age: 15, class: "VII", group: "general" },
  { name: "Charlotte", age: 17, class: "X", group: "science", hobbies: ["studying", "playing", "gardening"] },
  { name: "Benjamin", age: 14, class: "IX", group: "arts", isActive: true },
  {
    name: "Rowan",
    age: 10,
    class: "III",
    group: "general",
    address: { street: "2416 Roosevelt", city: "San Francisco", zipcode: 94108 },
  },
]);
```

</details>

<details>
      <summary>4. In the following table, there is an empty space in the field name <code>previous exam</code> and <code>next exam</code>. How can you deal with it when you entry it into a collection?</summary>
      
| name | class | previous exam | next exam    |
|------|-------|---------------|--------------|
| Bob  | XII   | passed        | no exam      |
| Lee  | XII   | failed        | 2 days later |

> **Hints:** Put the field name between two `"` marks.

```js
db.students.insertMany([
  { name: "Bob", class: "XII", "previous exam": "passed", "next exam": "no exam" },
  { name: "Lee", class: "XII", "previous exam": "failed", "next exam": "2 days later" },
]);
```

</details>

<details>
      <summary>5. We can use of dot notation in mongoDB for inserting values. Use that dot notation system to insert the following table.</summary>

| name | class | address                                    |
| ---- | ----- | ------------------------------------------ |
| Bob  | XII   | street: 123 Main Street,<br>city: New York |

```js
db.students.insertOne({ name: "Bob", class: "XII", "address.street": "123 Main Street", "address.city": "New York" });
```

> I dislike this method. I am very comfortable in the following way:

```js
db.students.insertOne({ name: "Bob", class: "XII", address: { street: "123 Main Street", city: "New York" } });
```

</details>

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

##### **Step-2: Insert Documents by Importing Files:**

One of the famous processes that can populate documents inside a collection of a database is to implement `mongoimport`. `mongoimport` must be run from the system command line, not from `mongosh` shell. `Extended JSON`, `CSV`, or `TSV` files can be imported by using `mongoimport` process.

> However, if you do not have installed [`MongoDB Command Line Database Tools`](https://www.mongodb.com/try/download/database-tools "Download from mongodb official page") on your pc, you cannot use `mongoimport` command line since you are using mongodb above v4.2. To check whether it is properly install, type `mongoimport --version` in the system command line. If you get a version info, that means you are ready to use it.

#### Syntax

```js
mongoimport <options> <connection-string> <file>
```

##### common `options`:

`--db=<database>, -d=<database>` : Specifies the name of the database on which to run the `mongoimport`. </br>
`--collection=<collection>, -c=<collection>` : Specifies where the collection to import. If you do not specify it `mongoimport` takes imput filename as the collection name, omitting the file's extension if it has one. </br>
`--type=<json|csv|tsv>`: Specifies the file type to import. Default is `json`. </br>
`--headerline`: Only for `csv` and `tsv`, not for `json`. Takes first line as field names. </br>
`--ignoreBlanks`: Only for `csv` and `tsv`, not for `json`. Ignores empty fields in `csv` and `tsv` exports. If not specified, `mongoimport` creates fields without values in imported documents. </br>
`--fields=<field1[,field2]>, -f=<field1[,field2]>`: Only for `csv` and `tsv` files, not for `json`. `json` has its own key which can be used as a field name. Without any headerline in `csv` and `tsv` files can be provided fields by this option. </br>
`--drop`: Modifies the import process so that the target instance drops the collection before importing the data from the input. </br>
`--mode=<insert|upsert|merge|delete>` :

<ul>
    <li>insert: Default is `insert`.</li>
    <li>upsert: Replace existing documents in the database with matching documents from the import file.</li>
    <li>merge: Merge existing documents that match a document in the import file with the new document. `mongoimport` will insert all other documents.</li>
    <li>delete: Delete existing documents in the database that match a document in the import file. `mongoimport` takes no action on non-matching documents.</li>
</ul>

`--file=<filename>`: Specifies the location and name of a file containing the data to import. Must be specified at the last of the syntax.</br>
`--jsonArray`: Add this if you get `Failed: cannot decode array into a primitive` problem while importing json file. </br>
`--version` : Returns the `mongoimport` release number. </br>
`--help` : Prints all the available options and use of `mongoimport` </br>

<div>
    <b><a href="https://www.mongodb.com/docs/database-tools/mongoimport">[ Read More... ]</a></b>
</div>

</br>

<details>
    <summary>1. Import <code>./mongodb/sample data/query/flights.csv</code> file containing nearly 7698 documents. Specify <code>airlines</code> as database, <code>flights</code> as collection. A headerline has already been included.</summary>

```js
mongoimport --db="airlines" --collection="flights" --type="csv" --headerline  --file="./mongodb/sample data/query/flights.csv"
```

</details>

<details>
    <summary>2. How can you inspect this newly created database <code>airlines</code>?</summary>

```js
mongosh
show dbs
```

</details>

<details>
    <summary>3. How can you enter this database and inspect the collection<code>flights</code>?</summary>

```js
use airlines
show collections
```

</details>

<details>
    <summary>4. How can you know the total number of documents in this collection?</summary>

```css
db.flights.countDocuments()
```

</details>

<details>
    <summary>5. How can you know the total number of documents in this collection that have country <code>Canada</code> ?</summary>

```css
db.flights.countDocuments({country: "Canada"})
```

This gives the exact number of documents in this collection that have country named `Canada`.

</details>

</br>

> More advanced practices such as auth, merge, delete, fields, ignore blanks during importation are coming soon.

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

## Query Documents

MongoDB queries are used to search and retrieve data from a collection of documents in a database. In mongoDB, you can find your expected results through filtering, and represent those results in a flexible way through projection. Query always returns a cursor.

#### Syntax

```js
db.myCollections.find(<query>, <projection>, <options>).cursorMethods()
```

> **`.find`** can take upto three parameters, but all are optional. If you pass no parameter, it retrieves all the documents in a collection.

<!-- prettier-ignore -->
> **`<query>:`** (optional). The query parameter filters the documents of a collection using query operators. </br> 
> **`<projection>:`** (optional). The projection parameter determines which fields are returned in the matching documents. It is a process of representation of showing results.</br>
> **`<options>:`** (optional). These options modify query behavior and how results are returned. Variables can be applied for query through options.

> **`returns:`** `.find()` returns a `cursor`, the result set of a query. Clients can iterate through a cursor to retrieve results. By default, cursors cannot be opened within a session automatically timeout after 10 minutes of inactivity.

> **`cursorMethods():`** Common cursor methods are `.count()`, `.limit()`, `.sort()`, `.forEach()`, `.skip()`, `.next()` etc. </br> [All available cursor methods...](https://www.mongodb.com/docs/manual/reference/method/db.collection.find/#available-mongosh-cursor-methods)

<!-- prettier-ignore -->
> > **`Query Operators:`** [All the available query operators](https://www.mongodb.com/docs/manual/reference/operator/query/#query-selectors) </br> 
> > **`Projection Operators:`** [All the available projection operators](https://www.mongodb.com/docs/manual/reference/operator/query/#projection-operators)

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

### Practice Query

Before we proceed to practice query, we need an excellent database from where we can implement and understand how query works in mongoDB. A [json file](./sample%20data/society.json) is already created. Now import this file by using `mongoimport` command line [[Guide Me]](#insert-documents-by-importing-files), and create a database named `society` and a collection named `people`.

##### **Step-1: To import json file:**

```js
mongoimport -d="society" -c="people" --file="./mongodb/sample data/society.json" --jsonArray
```

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

##### **Step-2: Basic query selections:**

<details>
    <summary>1. Get all the documents in <code>people</code> collection. After receiving the results, apply <code>count()</code> cursor method to get the amount of documents of this query.</summary>
    
```js
db.people.find()
db.people.find().count()
```
    
</details>

<details>
    <summary>2. Get all the documents that have <code>gender: female</code>. After that, apply <code>count()</code> method.</summary>
    
```js
db.people.find({gender: "female"})
db.people.find({gender: "female"}).count()
```
    
</details>

<details>
    <summary>3. Get documents that have <code>hasAuthority: false</code>. Count and then limit to first three results.</summary>
    
```js
db.people.find({hasAuthority: false})
db.people.find({hasAuthority: false}).count()
db.people.find({hasAuthority: false}).limit(3)
```
    
</details>

<details>
    <summary>4. Get documents that have <code>hasAuthority: true</code>, but this time you need a projection query. Let you want to present <code>firstName: &lt;value&gt;</code> each of the document. How can you do that? After doing that, count and limit to first two results.</summary>
    
```js
db.people.find({hasAuthority: true}, {firstName: 1})   // `1` means to show while `0` means not to show fields.
db.people.find({hasAuthority: true}, {firstName: 1}).count()
db.people.find({hasAuthority: true}, {firstName: 1}).limit(2)
```
    
</details>

<details>
    <summary>5. Later, you wish to get the results in alphabetically order. How can you do it?</summary>
    
```js
db.people.find({hasAuthority: true}, {firstName: 1}).sort({firstName: 1})
```
    
</details>
    
<details>
    <summary>6. MongoDB gives an auto generated unique id. But I want to repersent my result without it, and I also want firstName, lastName, and their age those who have <code>hasAuthority: true</code>. And of course, firstName must be in alphabetically order. Can you do it for me, please? After that, count total results.</summary>
    
```js
db.people.find({hasAuthority: true}, {_id: 0, firstName: 1, lastName: 1, age: 1}).sort({firstName: 1})
db.people.find({hasAuthority: true}, {_id: 0, firstName: 1, lastName: 1, age: 1}).sort({firstName: 1}).count()
```
    
</details>

<details>
    <summary>7. Now get all the documents and present only firstName, age, and language fields. After that, sort their age in ascending order. Then descending order. Then limit to first five results in ascending order.</summary>
    
```js
db.people.find({}, {_id: 0, firstName: 1, age: 1, language: 1}) 
db.people.find({}, {_id: 0, firstName: 1, age: 1, language: 1}).sort({age: 1})    \\ ascending order.
db.people.find({}, {_id: 0, firstName: 1, age: 1, language: 1}).sort({age: -1})     \\ descending order.
db.people.find({}, {_id: 0, firstName: 1, age: 1, language: 1}).sort({age: 1}).limit(5)   \\ ascending order and first five results.
```
    
</details>

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

##### **Step-3: Comparison query selections:**

| Name |          Description           |
| :--: | :----------------------------: |
| $eq  |            equal to            |
| $ne  |          not equal to          |
| $gt  |          greater than          |
| $gte |     greater than or equal      |
| $lt  |           less than            |
| $lte |       less than or equal       |
| $in  | any of the values in an array  |
| $nin | none of the values in an array |

#### Syntax:

```js
{ <field>: { $<comparisionName>: <value> } }        \\ not for $in and $nin
{ <field>: { $in: [<value1>, <value2>, ..., <valueN> ] } }      \\ only for $in
{ <field>: { $nin: [<value1>, <value2>, ..., <valueN> ] } }      \\ only for $nin
```

<details>
    <summary>8. Get a result of people who are above 30 years, and only show their firstName with age. Sort age in a ascending manner.</summary>
    
```js
db.people.find({age: {$gt:30}}, {_id: 0, firstName: 1, age: 1}).sort({age: 1})
```

</details>

<details>
    <summary>9. Get a result of people who are 25 years or less, and only show their firstName, age, and hasAuthority fields. Sort age in a ascending manner and then sort firstName is descending alphabetically order. Now present only first two documents.</summary>
    
```js
db.people.find({age: {$lte: 25}}, {_id: 0, firstName: 1, age: 1, hasAuthority: 1})
db.people.find({age: {$lte: 25}}, {_id: 0, firstName: 1, age: 1, hasAuthority: 1}).sort({age: 1, firstName: -1})
db.people.find({age: {$lte: 25}}, {_id: 0, firstName: 1, age: 1, hasAuthority: 1}).sort({age: 1, firstName: -1}).limit(2)
```

</details>

<details>
    <summary>10. Get a result of people who are female, and present the result only firstName with their age field.</summary>
    
```js
db.people.find({gender: {$eq:"female"}}, {_id: 0, firstName: 1, age: 1})
```

**Equivalent to:**

```js
db.people.find({ gender: "female" }, { _id: 0, firstName: 1, age: 1 });
```

</details>

<details>
    <summary>11. Get a result of people who are not 55 years old, and present result with only lastName and their gender. Then count.</summary>
    
```js
db.people.find({age: {$ne: 55}}, {_id: 0, lastName: 1, gender: 1})
db.people.find({age: {$ne: 55}}, {_id: 0, lastName: 1, gender: 1}).count()
```

</details>

###### Handling Arrays (12-17)

<details>
    <summary>12. Get a presented firstName and role result of people who have exactly one <code>patient</code> role. Then count.</summary>
    
```js
db.people.find({role: ["patient"] }, {_id: 0, firstName: 1, role: 1})
db.people.find({role: ["patient"] }, {_id: 0, firstName: 1, role: 1}).count()
```

> Gives result which has first `patient` element in the `role` array.

</details>

<details>
    <summary>13. Get a presented firstName and role result of people who have exactly <code>patient</code> and then <code>lawyer</code> role in order. Then count.</summary>
    
```js
db.people.find({role: ["patient", "lawyer"] }, {_id: 0, firstName: 1, role: 1})
db.people.find({role: ["patient", "lawyer"] }, {_id: 0, firstName: 1, role: 1}).count()
```

> Gives result which `role` array has `patient` as a first element and `lawyer` as a second element.

</details>

<details>
    <summary>14. Try to get exactly <code>lawyer</code> role in first order. Then count.</summary>
    
```js
db.people.find({role: ["lawyer"] }, {_id: 0, firstName: 1, role: 1})
db.people.find({role: ["lawyer"] }, {_id: 0, firstName: 1, role: 1}).count()
```
> If `lawyer` is the first element of the role array, it will show result otherwise show empty. Because we use `{role: ["lawyer"]}` meaning the very first element of the array.

</details>

<details>
    <summary>15. Get a presented firstName and role result of people who have atleast <code>patient</code>. Then count.</summary>
    
```js
db.people.find({role: {$in: ["patient"]}}, {_id: 0, firstName: 1, role: 1})
db.people.find({role: {$in: ["patient"]}}, {_id: 0, firstName: 1, role: 1}).count()
```

> If `role` array has a `patient` element, no matter what its position in the array, it will give some result. This `role` might has more element rather than only one `patient` element.

</details>

<details>
    <summary>16. Get a presented firstName and role result of people who have either <code>patient</code> or <code>doctor</code> or both role.</summary>
    
```js
db.people.find({role: {$in: ["patient", "doctor"]}}, {_id: 0, firstName: 1, role: 1})
```

> Hmm, `role` array might has several additional elements. But this array must has atleast `patient` or `doctor` element. They may contain both elements as well. Element order is not important here.

</details>

<details>
    <summary>17. Get a presented firstName and role result of people who does not have <code>patient</code> role.</summary>
    
```js
db.people.find({role:{$nin: ["patient"]}}, {_id: 0, firstName: 1, role: 1})
```

> `role` array does not contain `patient` element.

</details>

**Note: Equivalent code**

```css
db.people.find({ role: "lawyer" }, { _id: 0, firstName: 1, role: 1 })
```

is equivalent to

```css
db.people.find({ role: { $in: ["lawyer"] } }, { _id: 0, firstName: 1, role: 1 })
```

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

##### **Step-4: Logical query selections:**

| Name |                                  Description                                  |
| :--: | :---------------------------------------------------------------------------: |
| $and | combines multiple conditions together; if all true, returns non-empty result. |
| $or  | combines multiple conditions together; if any true, returns non-empty result. |
| $nor |                                 inverts `$or`                                 |
| $not |                              inverts conditions                               |

#### Syntax:

```js
{ $and: [ { <expression1> }, { <expression2> } , ... , { <expressionN> } ] }
{ $or: [ { <expression1> }, { <expression2> }, ... , { <expressionN> } ] }
{ $nor: [ { <expression1> }, { <expression2> }, ...  { <expressionN> } ] }
{ field: { $not: { <operator-expression> } } }
```

<details>
    <summary>18. Get a list of firstName, gender, and age of people who are above 30 years old and female. Now, Sort their age in ascending order.</summary>
    
```js
db.people.find({$and: [{age: {$gt: 30}}, {gender: {$eq: "female"}}]}, {_id: 0, firstName: 1, age: 1, gender: 1})
db.people.find({$and: [{age: {$gt: 30}}, {gender: {$eq: "female"}}]}, {_id: 0, firstName: 1, age: 1, gender: 1}).sort({age: 1})
```

</details>

<details>
    <summary>19. Get a list of firstName, and role of people who are either doctor or lawyer or both. Now, Sort their name in ascending order.</summary>
    
```js
db.people.find({$or: [{role: {$in: ["doctor"]}}, {role: {$in: ["lawyer"]}}]}, {_id: 0, firstName: 1, role: 1})
db.people.find({$or: [{role: {$in: ["doctor"]}}, {role: {$in: ["lawyer"]}}]}, {_id: 0, firstName: 1, role: 1}).sort({firstName: 1})
```

</details>

##### **Step-5: Element query selections:**

|  Name   |                   Description                    |
| :-----: | :----------------------------------------------: |
| $exists |     inspects the target field exists or not.     |
|  $type  | whether the target field is specific type or not |

#### Syntax:

```js
{ field: { $exists: <boolean> } }
{ field: { $type: <BSON type> } }
```

> [See available types](https://www.mongodb.com/docs/manual/reference/operator/query/type/#available-types)

<details>
    <summary>20. Inspect `isChairman` field is there or not.</summary>
    
```js
db.people.find({isChairman: {$exists: true}}, {_id: 0, firstName: 1, isChairman: 1, age: 1})
```

</details>

<details>
    <summary>21. Count `address` field if it is an object.</summary>
    
```js
db.people.find({address: {$type: "object"}}).count()
```

</details>

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

##### **Step-6: Regex query selections:**

Provides regular expression capabilities for pattern matching strings in queries. MongoDB uses Perl compatible regular expressions (i.e. "PCRE" ) version 8.42 with UTF-8 support.

#### Syntax:

```js
{ <field>: { $regex: /pattern/, $options: '<options>' } }
{ <field>: { $regex: 'pattern', $options: '<options>' } }
{ <field>: { $regex: /pattern/<options> } }
```

> [See available options](https://www.mongodb.com/docs/manual/reference/operator/query/regex/#mongodb-query-op.-options)

<details>
    <summary>22. Get the firstName list of people whose name starts with `M`.</summary>
    
```js
db.people.find({firstName: {$regex: /^M/ }}, {_id: 0, firstName: 1})
```

</details>

<!-- prettier-ignore -->
> > [Help of selecting regex](https://regexr.com/) </br>
> > [See All the operators](https://www.mongodb.com/docs/manual/reference/operator/query/)

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

##### **Step-7: Query selections for object:**

<details>
    <summary>23. Search the person who has street: "3333 Oak St", city: "Anycity", state: "CA", zipcode: 90001, and country: "USA".</summary>
    
```js
db.people.find({address: {street: "3333 Oak St", city: "Anycity", state: "CA", zipcode: 90001, country: "USA"}})
```

> Needs all the fields and exactly in the same order to perform a correct result; Otherwise, use dot notation for individual key.

</details>

<details>
    <summary>24. Get a list having firstName and city of person who are from `Anycity` city.</summary>
    
```js
db.people.find({"address.city": "Anycity"}, {_id: 0, firstName: 1, "address.city": 1})
```

</details>

> **Note:** When querying using dot notation, the field and nested field must be inside quotation marks.

<details>
    <summary>25. Get a list having firstName and address zipcode of person whose zipcode is between 60000 and 70000.</summary>
    
```js
db.people.find({$and: [{"address.zipcode": {$gt: 60000}}, {"address.zipcode": {$lt: 70000}}]}, {_id: 0, firstName: 1, "address.zipcode": 1})
```

</details>

<details>
    <summary>26. Get a list having firstName and address zipcode of person who is female and whose zipcode is between 60000 and 70000.</summary>
    
```js
db.people.find({$and: [{"address.zipcode": {$gt: 60000}}, {"address.zipcode": {$lt: 70000}}, {gender: "female"}]}, {_id: 0, firstName: 1, "address.zipcode": 1})
```

</details>

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

##### **Step-8: Query selections for array:**

> **Note:** [See Handling Arrays (12-17)](<#handling-arrays-(12-17)>)

<details>
    <summary>27. Search the person who has street: "3333 Oak St", city: "Anycity", state: "CA", zipcode: 90001, and country: "USA".</summary>
    
```js
db.people.find({role: {$all: ["lawyer", "patient"]}}).count()
```

> If you use `$all`, it finds all the target values whatever their position inside an array. It does not follow order.

</details>

<details>
    <summary>28. Search a doctor, but person may have multiple roles.</summary>
    
```js
db.people.find({role: "doctor"}, {role: 1})
```

> Here, role contains the string "doctor" as one of its elements.

</details>

<details>
    <summary>29. List of firsName and their role of people who has `lawyer` and `patient` role.</summary>
    
```js
db.people.find({role: {$eq: "lawyer", $eq:"patient"}}, {role: 1, _id: 0, firstName: 1})
```

> Here, role contains either lawyer or patient, or even both.

</details>

> > [Take a look of $elemMatch](https://www.mongodb.com/docs/manual/reference/operator/query/elemMatch/#-elemmatch--query-). The `$elemMatch` operator matches documents that contain an array field with at least one element that matches all the specified query criteria. However, if your `$elemMatch` expression contains the $not or $ne operators then omitting the `$elemMatch` expression changes the documents returned.

**Array Index; Use of `<array>.<index>: <value>`**

<details>
    <summary>31. Query an array by its length.</summary>
    
```js
db.people.find({"language.1": "spanish"}).count()       // here `1` is the index of language array.
```

</details>

**Array Length; Use of `$size: <number>`**

<details>
    <summary>32. Count how many people talks in only one language.</summary>
    
```js
db.people.find({language: {$size: 1}}).count()          
// how many people have only one language, meaning `language` array got only one element.
```

</details>

**Project Specific Array Elements Use of `$slice: <number>`**

<details>
    <summary>33. Present people's last role. People must be above 30 years old.</summary>
    
```js
db.people.find({age: {$gt: 30}}, {_id: 0, firstName: 1, role: {$slice: -1}})   
// `$slice: 1` means first one value, `$slice: 2` means first two values, `$slice: 3` means first three values,
// `$slice: -1` means last value.
```

</details>

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

## Update Documents

Here, the three ways to update an existing document:

#### Syntax

```js
db.myCollection.updateOne(<filter>, <update>, <options>)
// only updates the first matched result.
```

```js
db.myCollection.updateMany(<filter>, <update>, <options>)
// updates all the matched results.
```

```js
db.myCollection.replaceOne(<filter>, <update>, <options>)
// replaces all the fields that matches. (Danger!!)
```

<!-- prettier-ignore -->
> **`<filter>:`** exactly the same process that we do in query section. </br>
> **`<update>:`** uses some sort of update expression. [See all update operators](https://www.mongodb.com/docs/manual/reference/operator/update/#fields) </br>
> **`<options>:`** (optional). `upsert` -> When `true`, it creates a new document if no document matches the filter. [See Details](https://www.mongodb.com/docs/manual/reference/method/db.collection.updateOne/#syntax)

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

### Practice Update

<!-- go -->

##### **Step-1: Using .updateOne({ }, { }):**

<details>
    <summary>1. Find `isChairman: "Yes"` and update its `age` to 50.</summary>

```js
db.people.updateOne({ isChairman: "Yes" }, { $set: { age: 50 } });
```

</details>

<details>
    <summary>2. Push new role `banker` to `firstName: "Marjorie".</summary>

```js
db.people.updateOne({ firstName: "Marjorie" }, { $push: { role: "banker" } });
// `$push` Adds an item to an array. [See all](https://www.mongodb.com/docs/manual/reference/operator/update/#array)
```

</details>

##### **Step-2: Using .updateMany({ }, { }):**

<details>
    <summary>3. Filter people who are 25 years or less, and then add `status: "Young"` field.</summary>

```js
db.people.updateMany({ age: { $lte: 25 } }, { $set: { status: "Young" } });
```

</details>

##### **Step-3: Using .updateOne({ }, { }, { }):**

<details>
    <summary>4. Filter `role: "teacher"` and then add `firstName: "Anis", role: "teacher"`. Use `upsert: true` as we have no document before.</summary>

```js
db.people.updateOne({ role: ["teacher"] }, { $set: { firstName: "Anis", role: ["teacher"] } }, { upsert: true });
// `upsert` creates new document if there is no document existed before.
```

</details>

##### **Step-4: Using .replaceOne({ }, { }):**

<details>
    <summary>5. Filter `firstName: "Anis"` and replace with `firstName: "Adam". You will notice no role field that we have befor. That's why replaceOne is dangerous. It only updates what you pass in the second parameter, remaining or existing fields will get deleted.</summary>

```js
db.people.replaceOne({ firstName: "Anis" }, { firstName: "Adam" });
```

</details>

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

## Delete Documents

Here, the ways to delete an existing document:

#### Syntax

```css
db.collection.deleteOne()
// When no parameter, deletes first document even though multiple documents may exist.
// When `<filter>` parameter, deletes first matched document.
```

```css
db.collection.deleteMany()
// When no parameter, deletes all  documents.
// When `<filter>` parameter, deletes all the matched documents.
```

```css
db.collection.remove(<query>, <justOne-boolean>)
// if optional justOne boolean is passed, it removes only one document.
```

[Read more...](https://www.mongodb.com/docs/manual/reference/delete-methods/#delete-methods)

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

### Practice Delete

<!-- go -->

##### **Step-1: Using .deleteOne({ }):**

<details>
    <summary>1. Find `firstName: "Adam"` and delete.</summary>

```js
db.people.deleteOne({ firstName: "Adam" });
```

</details>

##### **Step-2: Using .deleteMany({ }):**

<details>
    <summary>2. Delete all at once people who are exactly 22 years.</summary>

```js
db.people.deleteMany({ age: { $eq: 22 } });
```

</details>

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

# Conclusion
Here in this article, all the basics including most advanced topics are covered. At this point, anyone can understanding mongoDB database system and able to implement the power of this database to build server side website. If you want to learn more, you can browse the official docs. [Official Docs](https://www.mongodb.com/docs/launch-manage/)

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

# Author
- Mirza Monirul Alam (Ethen)
- Full Stack Developer.

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

# Contributions
Any contribution will be appreciated. **THANK YOU**

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>
