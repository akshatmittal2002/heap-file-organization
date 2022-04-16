# Heap-File-Organization

Implementation of `Heap File` in C++.<br>
It tree will have a parameters: `page_size`<br>
- Each page will have a fixed size.
- Each page is divided into two parts: `Data Area` and `Book Keeping Area`.<br>The data area grows from beginning of the page to the end of the page.<br>The book keeping area grows in the reverse direction.<br>A new blank page has `four` integers stored at the end of page:
    - Address of previous page
    - Address of next page
    - Count of the number of records in the page
    - Start address of free space within the page<br>

```
NOTE: Assume that each integer requires 4 bytes of storage.
```
To store a record into the page, you need to create a directory entry in the book keeping area.<br>This entry will store pointer to the beginning of the record in the page.<br> Assume that this pointer is an integer value.<br>To store a record of size `R Bytes`, the space occupied in the page is `R+4 Bytes`.

### Input:
`Line 1` contains the value of `page_size`<br>
`Line 2 onwards` descibes various operation to be performed<br>
&emsp;`1` : Insert new value<br>
&emsp;&emsp;&emsp;Parameter: Record_size and Value<br>
&emsp;`2` : Display The Status<br>
&emsp;`3` : Search for a value<br>
&emsp;&emsp;&emsp;Parameter: Value<br>
&emsp;`4` : Exit<br>

### Output:
For operation `2`, output will be one line containing `number of pages` and `number of records in each page` separated by `space` and terminated by `\n`.<br>
For operation `3`, output will be one line containing `page id` and `slot id` if the value is found and `-1 -1` if the value is not found.<br>