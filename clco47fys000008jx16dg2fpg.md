# [JavaScript] Decimal Numbering Method : toFixed()

Monday morning, I received a request from a customer to show the sales price with the first decimal place in the Enterprise Programme.

I've googled and found one easy and simple method!

# toFixed(number)

```javascript
let num = 10.12345

num.toFixed(1) 
//result = 10.1

num.toFixed(2)
//result = 10.12

num.toFixed(3)
//result = 10.123
```

look how easy it is!

you just need to insert the number of decimal places you want.