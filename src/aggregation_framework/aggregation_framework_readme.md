# Aggregation framework

## What is it?

The aggregation framework is a powerful tool for deep data analysis.
It can go further than the Mongo query language, especially when we work large datasets.

## How does it work?

The aggregation framework works through aggregate() command using a pipeline system in different stages.

Take the following example:

```js
use("sample_airbnb")
db.listingsAndReviews.find(
  {
    amenities: {
      $in: ["Wifi"]
    }
  },
  {
    price: 1,
    amenities: 1
  }
)
```

Here, we use the Mongo query language to do a query in the famous database sample_airbnb. In this case, we get 5303 documents with the following structure:

```js
{
    "_id": "10006546", //example
    "amenities": [
      ...
    ],
    "price": {
      "$numberDecimal": "80.00"
    }
  }
```

***But, if we would want to do it with aggregate framework***, How would we do it? It would be like:

```js
use("sample_airbnb")
db.listingsAndReviews.aggregate([
  {
    $match: {
      amenities: {
        $in: ["Wifi"]
      }
    }
  },
  {
    $project: {
      price: 1, amenities: 1
    }
  },
])
```

## What is the difference?

1. Aggregations are better than the Mongo query language when we have a dataset that is too large

2. Aggregations are more flexible than the Mongo query language, we can create many things like joins, math operations, powerful optimizations

3. Aggregations make it easier data transformation due to operators like ***$project***, ***$addFields***, ***$unwind***

4. We can handle nested data with operators like ***$unwind*** and ***$group***
