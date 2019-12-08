# BPlus-Tree-Implementation

In this project, we have implemented the insert and delete functions for B+ tree. The insert function implemented is capable of dealing with overflows by splitting. The delete function on the other hand, is naïve delete and does not deal with merging i.e. it simply deletes the record from the tree. Thus, we have implemented the methods insert(), _insert() and NaiveDelete().

## Getting Started

These instructions will get you a version of the project up and running on your local machine for development and testing purposes. See the following, for notes on how to deploy the project on a live system.

### Prerequisites

1) Java SE Development Kit 8
2) Java Minibase (included in the directory)
3) Putty (Command line terminal for remote access) or use any functional terminal.

### Operations

Insert Method
The insert() method takes the parameters <key,RID>. The B+ tree will initially be empty and the header will point to INVALID_PAGE. When the first record is inserted, a new leaf page is created and the header is made to point to this new page.

All other insertion operations will happen via the _insert() method that takes parameters <key, RID, currentPageID>. This function checks if the entry is a leaf or index page and in case of leaf page, it checks if there’s space. If the there is no space then it splits the data into a new leaf page and creates an index that maps to the newly created leaf. It is found that
in this project, the page splits when the 63rd record is entered. The existing page takes the first 31 records and the newly created page takes the remaining 31 records. 

Delete Method
In this project, with the NaiveDelete() method, we deleted the record directly from the tree without balancing the tree i.e. it won’t take into account for merging or redistribution of records after deletion. The NaiveDelete() function will take the parameters <key, RID>. We will use the key to traverse the tree and compare the key value. Once we find the match, we delete that record. 

## Running the tests

1) Open putty,
2) Put Authentication details,
3) Access the "BplusTree" folder,
4) go to src>tests> & enter make command to compile the file with makefile.
5) After this run the file using "make bttest" command. 
6) Insert & delete records.
7) Exit the program using 6.

## Built With

* [Java Minibase](https://research.cs.wisc.edu/coral/minibase/minibase.html) - The Library used.
* [Putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/) - Command line terminal for remote access to server.
* [JDK](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) - Java SE Development Kit 8 

