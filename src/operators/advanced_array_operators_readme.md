# Array operators

When an attribute is an array, the management's different. We need to compare with each array element when doing querys. For this, we've the next operators:

1. ```$in:``` It matches all documents that include at least one. It's like includes js array method. It works with values and array

2.  ```$nin:``` It matches all documents that do not include any array element. It's completely different from $in.  It works with values and array

3. ```$all:``` For this operator, we begin with the next example:

We need to find all documents include the next tags

```js
db.collection.find({ tags: ["book", "fantasy"] })
```

but, if we do this query, we only get documents with book and fantasy, that quantity and that sorting.

In this cases, usually we would need $all operator, like the next example:

```js
db.collection.find({ tags: {
  $all:  ["book", "fantasy"] 
}})
```

In this case, we are able to find all documents with both tags.

This method only works for arrays attributes


4. ```$elemMatch:``` This operator allows us to do complex querys, with many conditions for an array

5. ```$size:``` This operator finds all documents with the array type attribute specified with the choosen length, without what they contain