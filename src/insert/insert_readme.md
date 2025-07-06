# Insert instructions

## collection().insertOne({...})

This instruction creates only one document. 
If collection doesn't exist yet, it will be created first.

MongoDb manages Id creation by default, but we can implement custom ID management

By default, MongoDB generates Ids like follow:

1. **MongoCompas**: 
    ```json
    "_id": ObjectId("6865e101a4c20afddda241b9")
    ```
2. **Vs Code plugin**:
    ```json
    "_id": {
      "$oid": "6865e12e8ae6c5f020f7a0be"
    }
    ```

## collection().insertMany([{...}])

This intruction creates many documents at once. It receives an array of documents, like this:

```js
db.collection.insertMany(
   [ <document 1> , <document 2>, ... ],
   {
      writeConcern: <document>,
      ordered: <boolean>
   }
)
```

Mongo manage Ids generation the same way as insertOne.

The optional settings are ```writeConcern``` and ```ordered```. Ordered allows inserting all documents even if there is an _id collision.