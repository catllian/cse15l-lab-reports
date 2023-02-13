# Lab Report 3

The command I chose was grep. The command searches within files to find matching patterns.

## First option: -c
For the first example, I searched the .txt files within the relative directory `written_2/non-fiction/OUP/Abernathy/` for a file that had the matching string "1940s". 
"1940s" is only present in one file, ch1.txt.
The command:
```
$ grep -c "1940s" written_2/non-fiction/OUP/Abernathy/*.txt
```
The output:
```
written_2/non-fiction/OUP/Abernathy/ch1.txt:1
written_2/non-fiction/OUP/Abernathy/ch14.txt:0
written_2/non-fiction/OUP/Abernathy/ch15.txt:0
written_2/non-fiction/OUP/Abernathy/ch2.txt:0
written_2/non-fiction/OUP/Abernathy/ch3.txt:0
written_2/non-fiction/OUP/Abernathy/ch6.txt:0
written_2/non-fiction/OUP/Abernathy/ch7.txt:0
written_2/non-fiction/OUP/Abernathy/ch8.txt:0
written_2/non-fiction/OUP/Abernathy/ch9.txt:0
```
The output displays the paths to all the .txt files and the number of lines in each with the matching string. Here, it shows that ch1.txt has 1 line that matches 
and that the rest have 0 lines that match. This option would be useful if the user only wants to see the number of lines with matches for each file. This can be 
used to make succinct comparisons between multiple files.

For the second example, I searched one .txt file with the path `written_2/travel_guides/berlitz1/HandRHawaii.txt` for lines that matched "the".
The command:
```
$ grep -c "the" written_2/travel_guides/berlitz1/HandRHawaii.txt
```
The output:
```
64
```
