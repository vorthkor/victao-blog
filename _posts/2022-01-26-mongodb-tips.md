---
layout: post
title: "MongoDB tips to MacOS"
date: 2022-01-26
categories: learn
---

How to start and test MongoDB service on macOS.

***

## Table of Contents
  - [Install MongoDB](#Install-MongoDB)
  - [Running](#Running)
  - [MongoDB Shell](#MongoDB-Shell)
  - [Verify if MongoDB is running](#Verify-if-MongoDB-is-running)
  - [Tips](#Tips)

***

Here some easy ways to procceed with MongoDB and MacOS on the node intermediate course from GitHub Labs.

## Install MongoDB

[As followed by here](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/), 

- Install xcode-select
- Install homebrew

Then:

```
brew tap mongodb/brew

brew install mongodb-community@5.0
```



***

## Running


```
brew services start mongodb-community@5.0

```


***
## MongoDB Shell

 Install and after run

```
brew install mongosh

mongosh

```

***

## Shutdown via mongosh

Run mongosh and then:

```
db.adminCommand({
  shutdown: 1
})
```

***

## Verify if MongoDB is running 



```
brew services list
```

***

## Tips

```

    Open a new console and type in the mongosh command.
    Select our database: use userData
    Insert a new user into a users collection:db.users.insertOne({name:"octocat",email:"octo@cat.com",password:"password"})
    Find all users: db.users.find()
    Delete all users: db.users.drop()

```

***