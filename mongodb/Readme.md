###### MongoDB

<div align="center">
    <h1>Welcome to MongoDB Practice</h1>
</div>

<details>
    <summary>Table of Contains</summary>
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
                    </ul>
               </li>
               <li>
                    <a href="#insert-documents-by-importing-files">Insert Documents by Importing Files</a>
                    <ul>
                        <li><a href="#advanced-practice">Advanced Practice</a></li>
                    </ul>
               </li>
               <li>
                    <a href="#query-documents">Query Documents</a>
                    <ul>
                        <li><a href="#practice-query">Practice Query</a></li>
                    </ul>
               </li>
            </ul>         
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

## Insert Documents by Importing Files

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
`--version` : Returns the `mongoimport` release number. </br>
`--help` : Prints all the available options and use of `mongoimport` </br>

<div>
    <b><a href="https://www.mongodb.com/docs/database-tools/mongoimport">[ Read More... ]</a></b>
</div>

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

### Advanced Practice

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

> **`<query>:`** (optional). The query parameter filters the documents of a collection using query operators. </br> 
> **`<projection>:`** (optional). The projection parameter determines which fields are returned in the matching documents. It is a process of representation of showing results. </br>  
> **`<options>:`** (optional). These options modify query behavior and how results are returned. Variables can be applied for query through options.

> **`returns:`** `.find()` returns a `cursor`, the result set of a query. Clients can iterate through a cursor to retrieve results. By default, cursors cannot be opened within a session automatically timeout after 10 minutes of inactivity.

> **`cursorMethods():`** Common cursor methods are `.limit()`, `.sort()`, `.forEach()`, `.skip()`, `.next()` etc. </br>  [All available cursor methods...](https://www.mongodb.com/docs/manual/reference/method/db.collection.find/#available-mongosh-cursor-methods)

> > **`Query Operators:`** [All the available query operators](https://www.mongodb.com/docs/manual/reference/operator/query/#query-selectors) </br> 
> > **`Projection Operators:`** [All the available projection operators](https://www.mongodb.com/docs/manual/reference/operator/query/#projection-operators)

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>

### Practice Query

Before we proceed to practice query, we need an excellent database from where we can implement and understand how query works in mongoDB. A [json file](./sample%20data/society.json) is already created. Now import this file by using `mongoimport` command line [[Guide Me]](#insert-documents-by-importing-files), and create a database named `society` and a collection named `people`.

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>
