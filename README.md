# kw
Keyword based Note Database using bash and sqlite3

Requires a sqlite3 database file to be identified by the default variable:
sqlpath=~/bin/kwdata.sqlite

The database contains one table in the form of:
CREATE TABLE data(id integer primary key, note text not null, keywords text not null, modified text default current_timestamp not null);

If you dont want to make your own database file in sqlite3, the included kwdata.sqlite file is already in the correct format with a couple test entries.

Usage can be found with:
kw -h
or 
kw -?

Usage is as follows:
kw - Keyword driven note database
Usage:
kw [-a] [-n] [-l limit] [-o offset] [-s offset] [-h] [-?] keyword [keyword..n]
kw -c          : Create new note
kw -u <index>  : Update note with the id <index>
kw -d <index>  : Delete note with the id <index>
kw -i <index>  : View note with the id <index>
 
-a             : Show all note fields in results, id, note, keywords, modified datetime
-l <limit>     : Show <limit> number of results : default = 10
-o <offset>    : Skip <offset> number of results : default = 0
-s <offset>    : Skip <offset> number of results : default = 0
-n             : Search note field for given keywords instead of keywords field
-h             : Show help
-?             : Show help
 
keyword        : Any number of space separated keywords searched with logical AND


Default is to enter notes with your $EDITOR setting. If no $EDITOR is found, it will default to /usr/bin/vim.

