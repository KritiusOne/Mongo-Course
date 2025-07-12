# Regex operator

A regular expresion, usually naming regex, is a common way to make querys on text attributes. In mongodb, we have a operator to do querys through regex

1. ```$regex:``` Through this operator, we can do regex. Something like this:

```js
db.collection.findMany({ <Attribute_name>: {$regex /<ourRegex>/}})
```
This topic is very large. We can find more information in: <a href="https://www.mongodb.com/docs/atlas/atlas-search/regex/">Mongo documentation</a>