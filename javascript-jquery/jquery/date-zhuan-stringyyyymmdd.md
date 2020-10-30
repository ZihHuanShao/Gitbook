# Date轉String\(yyyy-mm-dd\)

```javascript
var date = new Date("2020-10-01");

date.setDate(date.getDate() + 2);

date.toISOString()
// "2020-10-03T00:00:00.000Z"

date.toISOString().substr(0, 10)
// "2020-10-03"
```

## Ref.

{% embed url="https://stackoverflow.com/questions/9989382/how-can-i-add-1-day-to-current-date/9989458" %}



