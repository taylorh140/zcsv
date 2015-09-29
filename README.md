# zcsv
idea for simpler spreadsheet format

## plan
There are many things that csv does that are in quite good. There are also things that people dont like about them. I see formats like the xlsx an xml based monstrosity and even the ods is quite beastly. Poking around for data without a corrisponding program can be difficult and using them as a template requires complex libraries that cost time and money to get learn to use. I am hoping to standarize a simple format that does slightly more that the csv but not too much more, and is easy to navigate and edit, just like csv :).

## specifications
The idea here is that I hope to specifiy this format to such a degree that there is no question of how it should be interperted, Obviously still a work in progress. 

## rough idea

The zcsv is a zipped group of csv files that describe the content of a spreadsheet.

 - filename.zcsv
  - Data.csv
  - formulas.csv
  - Formattings.csv
  - Formattings.json

### Data.csv 
typical csv with the data you have come to know and expect from a csv.
