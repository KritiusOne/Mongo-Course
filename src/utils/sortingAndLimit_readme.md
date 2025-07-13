# Sorting, Limit and Pagination

Sometimes, we may need data in a specific order, quantity or in small packages. For this, we can use the following utilities

## Sorting

Sort instruction has the following structure:

```js
db.collection.find({...}).sort( { <ATTRIBUTE>: <ORDER_TYPE> } )
```

Where:

- ***ATTRIBUTE*** is a field by which we will sort

- ***ORDER_TYPE*** is a value by which we decide how we will sort. That has 2 possible values, 1 and -1.
  - ***1***: small to big
  - ***-1***: big to small

## Limit

We might want a limited number of documents. For this, we can use the following structure:

```js
db.collection.find({...}
  .sort({...})
  .limit(<QUANTITY>)
)
```

Where:

- ***QUANTITY*** is the desired number of documents

## Pagination

When we put a limit in our queries, usually we want to get the limited documents later, and here it's very important the pagination.

Pagination is a technique for optimized query response, especially in apps like APIs. For this, Mongodb gives us skip utility function. It has the following structure:

```js
db.collection.find({...}
  .sort({...})
  .skip(<QUANTITY>)
  .limit(...)
)
```

Where:

- ***QUANTITY*** is the number of document to skip.

Then, if we take this:

```js
db.collection.find({...}
  .sort({...})
  .skip(0)
  .limit(2)
)
```

We will get the two first documents. If we wanted to get the next documents, We could do something like this:

```js
db.collection.find({...}
  .sort({...})
  .skip(2)
  .limit(2)
)
```
