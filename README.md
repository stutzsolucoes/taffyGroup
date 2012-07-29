taffyGroup
==========

A "GROUP BY" clause extension for TaffyDB.

##How To Install

```html
<script src="taffy.js"></script>
<script src="taffy.extend.group.js"></script>
```

##How To Use

Just pass the column names that you want to group by.

```javascript
db().group('nation','state');
```

##Result Format

This extension method will return an array that contains group results.

Each group result have below properties:

- group : An array contains values of「GROUP BY」columns.
- result : An array contains records that match「group」property.
- count : The length of the array in「result」property.

Actually group result will looks like below:

```javascript
{"group":["USA","LA"],"result":[{"name":"New Orleans","state":"LA","nation":"USA","___id":"T000003R000011","___s":true}],"count":1}
```

##Example

If we have data likes below:

```javascript
var db = TAFFY([{name:"New York",state:"WA",nation:"USA"},
                {name:"Las Vegas",state:"NV",nation:"USA"},
                {name:"Boston",state:"WA",nation:"USA"},
                {name:"Denver",state:"CO",nation:"USA"},
                {name:"Phoenix",state:"AR",nation:"USA"},
                {name:"San Antonio",state:"TX",nation:"USA"},
                {name:"Dallas",state:"TX",nation:"USA"},
                {name:"Houston",state:"TX",nation:"USA"},
                {name:"Orlando",state:"FL",nation:"USA"},
                {name:"New Orleans",state:"LA",nation:"USA"},
                {name:"Seattle",state:"WA",nation:"USA"}]);
```