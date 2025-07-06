# Delete

In mongodb, we have 3 ways to remove documents.

1. ```db.collection.deleteOne({...})```
2. ```db.collection.deleteMany({...})```
3. ```db.collection.drop()```

## db.collection.deleteOne({...})

This instruction removes only one document. It receives an object, usually with the next shape:

```js
db.collection.deleteOne({ _id: <ID> })
```

## db.collection.deleteMany({...})

This instruction deletes many documents. It's important to use it carefully.
It receives an object, like this:

```js
db.collection.deleteMany({ <attribute_1>: <Value>, <attribute_2>: <Value>, ...})
````

## db.collection.drop()

This instruction deletes all documents in the collection. It's very important to know, this instruction does affects all documents in the collection.