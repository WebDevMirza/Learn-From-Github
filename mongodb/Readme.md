Welcome to MongoDB Practice

###### MongoDB

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
    </ol>

</details>

<!-- ABOUT Mongodb -->

# About MongoDB

MongoDB is a popular open-source **document-oriented database** system that uses a flexible, JSON-like format to store data in collections of documents. It is designed to be scalable, high-performance, and easy to use, making it a popular choice for developers building modern web and mobile applications.

MongoDB is a **backend technology**, specifically a database management system, that is used to store and manage data for web and mobile applications. It is typically accessed and manipulated using a backend programming language such as Node.js, Express.js, PHP, or Python etc. Its primary role is to handle the storage and retrieval of data on the server-side, making it a backend technology.

<p align="right">(<a href="#mongodb">back to top</a>)</p>

## Common Operations of MongoDB

- Storing Data
- Retrieving Data
- Updating Data
- Deleting Data

Overall, **CRUD (Create, Read, Update, Delete)** operations are fundamental to working with databases, including MongoDB. These operations allow you to create, read, update, and delete data as needed, providing a basic set of tools for managing data stored in MongoDB collections.

<p align="right">(<a href="#mongodb">back to top</a>)</p>

## Common Backend Technologies and Their Frameworks

Several common backend technologies and their associated frameworks for MongoDB are listed below:
| Backend Technology | Frameworks |
|--------------------|---------------|
| Node.js | Express.js |
| Python | Flask, Django |
| PHP | Laravel |

<p align="right">(<a href="#mongodb">back to top</a>)</p>

# Getting Started

In this article, I use `MongoDB Community Server v6.0.5`, `MongoDB Shell v1.8.0` and `MongoDB Command Line Database Tools v100.7.0`

<p align="right">(<a href="#mongodb">back to top</a>)</p>

## Downloading and Installing

- **MongoDB Community Edition**
  - [MongoDB Community Server](https://www.mongodb.com/try/download/community)
- **Tools**
  - [MongoDB Shell](https://www.mongodb.com/try/download/shell)
  - [MongoDB Command Line Database Tools](https://www.mongodb.com/try/download/database-tools)

After installing, add MongoDB binaries to the System PATH `C:\Program Files\MongoDB\Server\6.0\bin`. Now open terminal and type `mongosh`. If everything is okay, you should see a version number. Now you are ready to go.

<p align="right">(<a href="#mongodb">back to top</a>)</p>

## Terminology

There are four main basic terminology exists that need to know before move ahead: `database`, `collections`, `documents`, and `fields`.

- `Database`: holds `collections`.
- `Collections`: holds `documents`. It is like a table in relational database.
- `Documents`: holds `fields` and their associate `value`.
- `Fields`: Each key-value pair represents a field in the document.

<img src="https://www.mongodb.com/docs/manual/images/crud-annotated-document.bakedsvg.svg" alt="document and field example"/>
<p align="right">(<a href="#mongodb">back to top</a>)</p>

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
