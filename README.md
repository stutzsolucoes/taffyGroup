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

- group : An array contains values of "GROUP BY" columns.
- result : An array contains records that match "group" property.
- count : The length of the array in "result" property.

Actually group result will looks like below:

```javascript
{"group":["USA","LA"],"result":[{"name":"New Orleans","state":"LA","nation":"USA","___id":"T000003R000011","___s":true}],"count":1}
```

##Example

If we have records likes below:

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

We want to group these records by "nation" and "state" columns:

```javascript
var result = db().group("nation","state");
```

Then we will get result likes this:

```javascript
[{"group":["USA","WA"],"result":[{"name":"New York","state":"WA","nation":"USA","___id":"T000003R000002","___s":true},{"name":"Boston","state":"WA","nation":"USA","___id":"T000003R000004","___s":true},{"name":"Seattle","state":"WA","nation":"USA","___id":"T000003R000012","___s":true}],"count":3},
{"group":["USA","NV"],"result":[{"name":"Las Vegas","state":"NV","nation":"USA","___id":"T000003R000003","___s":true}],"count":1},
{"group":["USA","CO"],"result":[{"name":"Denver","state":"CO","nation":"USA","___id":"T000003R000005","___s":true}],"count":1},
{"group":["USA","AR"],"result":[{"name":"Phoenix","state":"AR","nation":"USA","___id":"T000003R000006","___s":true}],"count":1},
{"group":["USA","TX"],"result":[{"name":"San Antonio","state":"TX","nation":"USA","___id":"T000003R000007","___s":true},{"name":"Dallas","state":"TX","nation":"USA","___id":"T000003R000008","___s":true},{"name":"Houston","state":"TX","nation":"USA","___id":"T000003R000009","___s":true}],"count":3},
{"group":["USA","FL"],"result":[{"name":"Orlando","state":"FL","nation":"USA","___id":"T000003R000010","___s":true}],"count":1},
{"group":["USA","LA"],"result":[{"name":"New Orleans","state":"LA","nation":"USA","___id":"T000003R000011","___s":true}],"count":1}]
```

##My Blog

If you have any question or suggestion, welcome to my blog: http://aio1108.pixnet.net/blog 