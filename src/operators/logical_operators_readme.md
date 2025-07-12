# Logical operators

The logical operators are fundamental to build complex queries. In mongodb, we can use the following operators for this goal:

1. ```$and:``` This operator matches all documents that satisfy every specified condition. It has the following structure:

```js
db.collection.find({
  $and: [
    {
      <ATTRIBUTE>: <CONDITION>
    },
    {
      <ATTRIBUTE_1>: <CONDITION_1>
    },
    ...
  ]
})
```

2. ```$or:``` This operator matches all documents that satisfy at least one specified condition. It has the following structure:

```js
db.collection.find({
  $or: [
    {
      <ATTRIBUTE>: <CONDITION>
    },
    {
      <ATTRIBUTE_1>: <CONDITION_1>
    },
    ...
  ]
})
```

3. ```$not:``` This operator is a negation, for this, it matches all documents don't satisfy the condition. It has the following structure:

```js
db.collection.find({
  <ATTRIBUTE> : {
    $not: <QUERY>
  }
})
```

4. ```$nor:``` This operator doesn't match all documents that satisfy every specified condition. It has the following structure:

```js
db.collection.find({
  $nor: [
    {
      <ATTRIBUTE>: <CONDITION>
    },
    {
      <ATTRIBUTE_1>: <CONDITION_1>
    },
    ...
  ]
})
```