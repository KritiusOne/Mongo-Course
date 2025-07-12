# Expressive operator

The expressive operator allows us to compare data in a complex, flexible and dynamic way. It has the following syntax:

```js
db.collection.find({
  $expr: {
    <COMPARISON>: [<A>, <B>]
  }
})
```

Where, we can make any comparison between ```A``` and ```B```. Here is the reason why ```$expr``` is very special:

```A``` and ```B``` could be, for example, document attributes. We take the following example:

```js
db.monthlyBudget.find({
  $expr: {
    $gt: ["$spent", "$budget"]
  }
});
```
Then, this query does the next:
in the collection ***monthlyBudget***, it compares the attributes ***spent*** and ***budget***. If ***spent*** value it's greater than ***budget*** value, it does match