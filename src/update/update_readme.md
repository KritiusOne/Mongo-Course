# Update instructions

## db.collection.updateOne({...})

The function updateOne allows us to modify only one document. It receives two params:
document will be updeted. For it, we may need to use a special function:

- ```ObjectId:``` Function to find a doc by _id/objId

***change***: It says to updateOne how it will be updated. For it, we need to use some operators (Go to operators section).


For example:

```js
db.products.updateOne(
  { _id: ObjectId('6869cc676302a28f68f40783')},
  { 
    $set: {
      name: "Product name changed 4"
    },
    $inc: {
      price: -20
    }
})
```
## db.collection.updateMany({...})

It receives the same parameters as db.collection.updateOne, but updateMany has a different behavior.

The function updateMany updates all matched documents.
For this, it's important to use it carefully. 

For example:
```js
db.zips.updateMany({
    city: "CLEVELAND"
  },
  {
    $set: {
      my_attr: "HI"
    }
})
```

## Operators

1. ```$set:``` It set a new value in anyone property.

2. ```$inc:``` It increase the property values. If we use negative values, it will subtract the value

3. ```$unset:``` It removes the indicated attribute

4. ```$rename:``` It changes the attribute's name indicates. It doesn't change the value, it only changes the name.

5. ```$push:``` It adds a new element to array attributes. It's like the push method in arrays. We can use $each to add many elements

6. ```$pull:``` It removes elements from array attributes. We can use $in to remove many elements