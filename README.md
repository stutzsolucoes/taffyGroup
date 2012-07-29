taffyGroup
==========

A "GROUP BY" clause extension for TaffyDB.

##How To Install

`<script src="taffy.js"></script>`   
`<script src="taffy.extend.group.js"></script>`

##How To Use

Just pass the column names that you want to group by.

`db().group('nation','state');`

##Result Format

This extension method will return an array that contains group results.

Each group result have properties below:

- group : An array contains values of「GROUP BY」columns.
- result : An array contains records that match「group」property.
- count : The length of the array in「result」property.

Actually group result will looks like below:

`{"group":["USA","LA"],"result":[{"name":"New Orleans","state":"LA","nation":"USA","___id":"T000003R000011","___s":true}],"count":1}`