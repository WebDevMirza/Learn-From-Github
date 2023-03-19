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
               <li><a href="#insert-documents">Insert Documents</a></li>
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
      <summary>9. Let's say, we do not want this database. Thus, can you delete the entire database you've just created?</summary>

```js
db.dropDatabase();
```

</details>

<details>
      <summary>10. Exit the mongosh shell.</summary>

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

### Practice

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

<div align="right">
    <b><a href="#mongodb">↥ back to top</a></b>
</div>
