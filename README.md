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

- group:
- result:
- count: