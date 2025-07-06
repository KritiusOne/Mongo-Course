# Comparison query operators

The comparison query operators are an operator group that allows us to do complex query through the mix of them.

The comparison query operators are the next: 

1. ```$eq:``` This operator exists implicit when we do something like
```js
db.collection.find({ price: 20 })
```
Because, $eq matches all documents that have an equal value in the attribute. In the explicit way, it would see like this:
```js
db.collection.find({ price: { $eq: 20 }})
````
2. ```$ne:``` This operator matches all documents with different value. This is so because ***$ne*** is a contraction of ***NOT EQUALS***

3. ```$gt:``` It matches all documents greater than the specified value. It's the same that the > operator

4. ```$gte:``` It matches all documents greater or equals that the specifies value. It's the same that the >= operator

5. ```$lt:``` It matches all documents less than specified value. It's the same that the < operator

6. ```$lte:``` It matches all documents less or equals that specified value. It's the same that the <= operator

7. ```$in:``` It matches any value include in array

8. ```$nin:``` It matches no value included in array.