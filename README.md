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

* Rule 1
  
-----------------------------------------------------------------------------------
1. Each record is located on a separate line, delimited by a line
   break (CRLF).  For example:

   aaa,bbb,ccc CRLF
   zzz,yyy,xxx CRLF
-----------------------------------------------------------------------------------

  (Windows, Mac or Unix) line breaks should be accepted when reading CSV files, 

* Rule 2

-----------------------------------------------------------------------------------
2. The last record in the file may or may not have an ending line
   break.  For example:

   aaa,bbb,ccc CRLF
   zzz,yyy,xxx
-----------------------------------------------------------------------------------

  
* Rule 3

-----------------------------------------------------------------------------------
3. There maybe an optional header line appearing as the first line
   of the file with the same format as normal record lines.  This
   header will contain names corresponding to the fields in the file
   and should contain the same number of fields as the records in
   the rest of the file (the presence or absence of the header line
   should be indicated via the optional "header" parameter of this
   MIME type).  For example:

   field_name,field_name,field_name CRLF
   aaa,bbb,ccc CRLF
   zzz,yyy,xxx CRLF
-----------------------------------------------------------------------------------

* Rule 4

-----------------------------------------------------------------------------------
4. Within the header and each record, there may be one or more
   fields, separated by commas.  Each line should contain the same
   number of fields throughout the file.  Spaces are considered part
   of a field and should not be ignored.  The last field in the
   record must not be followed by a comma.  For example:

   aaa,bbb,ccc
-----------------------------------------------------------------------------------

  The delimiter is a comma.

* Rule 5

-----------------------------------------------------------------------------------
5. Each field may or may not be enclosed in double quotes (however
   some programs, such as Microsoft Excel, do not use double quotes
   at all).  If fields are not enclosed with double quotes, then
   double quotes may not appear inside the fields.  For example:

   "aaa","bbb","ccc" CRLF
   zzz,yyy,xxx
-----------------------------------------------------------------------------------

* Rule 6

-----------------------------------------------------------------------------------
6. Fields containing line breaks (CRLF), double quotes, and commas
   should be enclosed in double-quotes.  For example:

   "aaa","b CRLF
   bb","ccc" CRLF
   zzz,yyy,xxx
-----------------------------------------------------------------------------------


* Rule 7

-----------------------------------------------------------------------------------
7. If double-quotes are used to enclose fields, then a double-quote
   appearing inside a field must be escaped by preceding it with
   another double quote.  For example:

   "aaa","b""bb","ccc"
-----------------------------------------------------------------------------------

* My Rule 8
-----------------------------------------------------------------------------------
8. If two commas are directly next to one another the data "cell" represented is null
   if a double quote is shown it is a empty string.
   For example:

   "",,"ccc"  => |empty string|null|ccc|
-----------------------------------------------------------------------------------
