# Lab Report 3

The command I chose was grep. The command searches within files to find matching patterns. The "normal" format of the command is:
```
grep <pattern> <path>
```
The output will print all the lines in the files (within the path) that match the given pattern.

## First Option: -c
The option -c is meant to only display the number of matching lines for each file.

For the first example, I searched the .txt files within the directory `non-fiction/OUP/Abernathy/` for a file that had the matching string "1940s". 
"1940s" is only present in one file, ch1.txt.
Command:
```
$ grep -c "1940s" non-fiction/OUP/Abernathy/*.txt
```
Output:
```
non-fiction/OUP/Abernathy/ch1.txt:1
non-fiction/OUP/Abernathy/ch14.txt:0
non-fiction/OUP/Abernathy/ch15.txt:0
non-fiction/OUP/Abernathy/ch2.txt:0
non-fiction/OUP/Abernathy/ch3.txt:0
non-fiction/OUP/Abernathy/ch6.txt:0
non-fiction/OUP/Abernathy/ch7.txt:0
non-fiction/OUP/Abernathy/ch8.txt:0
non-fiction/OUP/Abernathy/ch9.txt:0
```
The output displays the paths to all the .txt files and the number of matching lines in each file. Here, it shows that ch1.txt has 1 line that matches 
and that the rest have 0 lines that match. This option would be useful if the user only needs to see the number of lines with matches for each file. This can be 
used to make succinct comparisons between multiple files.

For the second example, I searched one .txt file with the path `travel_guides/berlitz1/HandRHawaii.txt` for the number of lines that matched "the".
Command:
```
$ grep -c "the" travel_guides/berlitz1/HandRHawaii.txt
```
Output:
```
64
```
The output displays the number of lines with the matching string. HandRHawaii.txt has 64 lines that contain "the". For this example, I was just curious as to how the 
output would be displayed if the given path was just one .txt file.

## Second Option: -l
The option -l is meant to only display the files that have matching lines. 

For the first example, I searched the .txt files within the directory `non-fiction/OUP/Abernathy/` for a file that had the matching string "1940s". 
"1940s" is only present in one file, ch1.txt.
Command:
```
$ grep -l "1940s" non-fiction/OUP/Abernathy/*.txt
```
Output:
```
non-fiction/OUP/Abernathy/ch1.txt
```
The output displays the path to the .txt file with matching lines. Here, it shows that only ch1.txt has a matching line. This would be useful if the user only needs to 
know whether there are any matching strings in any files.

For the second example, I searched the .txt files within the directory `travel_guides/berlitz1/*.txt` for the string "???". The string is present in 
multiple .txt files in this directory.
Command:
```
$ grep -l "???" travel_guides/berlitz1/*.txt
```
Output:
```
travel_guides/berlitz1/HandRIsrael.txt
travel_guides/berlitz1/HandRIstanbul.txt
travel_guides/berlitz1/HandRJamaica.txt
travel_guides/berlitz1/HandRJerusalem.txt
travel_guides/berlitz1/HandRLakeDistrict.txt
travel_guides/berlitz1/HandRLosAngeles.txt
```
The output displays the paths to the .txt files with the matching lines.

## Third Option: -n
The option -n displays the line number with the matching lines.

For the first example, I searched one .txt file with the path `non-fiction/OUP/Abernathy/ch1.txt` for the line with the string "1940s". 
Command:
```
$ grep -n "1940s" non-fiction/OUP/Abernathy/ch1.txt
```
Output:
```
5:In the late 1940s, Bond Stores, the largest men???s clothing chain at the time, created a sensation in New York City by offering a wide selection of suits with two pairs of pants instead of one, reintroducing a level of product choice not seen since before the war.1 When the line of hopeful buyers at its Times Square store stretched around the block, Bond had to impose a limit of two suits per customer. During World War II, the apparel and textile industries had been converted to supply field jackets, overcoats, and uniforms to the U.S. and Allied Forces. But in the years immediately following the war, returning soldiers, the end of rationing, and pent-up customer demand meant apparel was in short supply.
```
The output displays the matching line number followed by the line itself. This option would be useful if the user wanted to find where exactly in the file the matches are.

For the second example, I searched the .txt files within the directory `travel_guides/berlitz2/` for files with lines that matched "Where To Go". There are multiple 
files in this directory with matching lines.
Command:
```
$ grep -n "Where To Go" travel_guides/berlitz2/*.txt
```
Output:
```
travel_guides/berlitz2/Beijing-WhereToGo.txt:5:Where To Go
travel_guides/berlitz2/CanaryIslands-WhatToDo.txt:48:Watch the birdie (and the dolphins). There are several animal/bird parks in the islands, Tenerife???s Loro Park, Gran Canaria???s Palmitos Park, or Lanzarote???s Guinate Tropical Park are all described in the Where To Go section of this guide. Others include the Parque Las Aguilas, Los Cristianos, Arona (Tenerife), which as the name implies, has an eagle show, all kinds of other birds and animals, and the new JungleRaid where kids of all ages can work their way through all kinds of obstacles.
travel_guides/berlitz2/CanaryIslands-WhatToDo.txt:50:Submarine Trips: see Where To Go for info on these excursions. Puerto Col??n, Playa de Am??ricas (Tenerife); Peurto de Mog??n (Gran Canaria); and Puerto Calero (Lanzarote).
travel_guides/berlitz2/Paris-WhereToGo.txt:5:Where To Go
```
The output displays the paths to the files with the matching lines, the matching line numbers, and the lines themselves.

## Fourth Option: -v
The -v option looks for lines in files that don't match.

For the first example, I searched one .txt file with the path `non-fiction/OUP/Abernathy/ch1.txt` for lines without the string "the".
Command:
```
$ grep -v "the" non-fiction/OUP/Abernathy/ch1.txt
```
Output:
```
Five Decades of Change
A Dying Industry???or Not?
The Channel Perspective: Five Propositions
Proposition 1:??????The retail, apparel, and textile sectors are increasingly linked as a channel through information and distribution relationships.
Similar dynamics are cropping up in nonclothing areas as well. Grocery stores now stock a profusion of toothbrushes, Home Depot has shelves and shelves of different light bulbs, and Dell offers custom-configured personal computers. The growing presence of fashion-basic elements in myriad consumer products means that all retailers and suppliers may find new competitive opportunities using replenishment.
How This Book Is Organized
```
The output displays the lines in the .txt file without the string "the". This option might be useful if the user wants to find files that don't discuss a certain subject.

For the second example, I searched the .txt files in the `travel_guides/berlitz2/` for files without lines that matched the string "a".
Command:
```
$ grep -v "a" travel_guides/berlitz2/*.txt
```
Output:
```
travel_guides/berlitz2/Algarve-History.txt:
travel_guides/berlitz2/Algarve-History.txt:
travel_guides/berlitz2/Algarve-History.txt:
travel_guides/berlitz2/Algarve-History.txt:
travel_guides/berlitz2/Algarve-History.txt:A Brief History
travel_guides/berlitz2/Algarve-History.txt:Under Moorish Rule
travel_guides/berlitz2/Algarve-History.txt:Foreign Intrigues
travel_guides/berlitz2/Algarve-History.txt:Kingdom???s End
travel_guides/berlitz2/Algarve-History.txt:
travel_guides/berlitz2/Algarve-History.txt:
...
```
I included only the first 10 lines of output because there were too many lines. The output displays the lines in the .txt files without the string "a", 
including empty lines.

## Reference
IBM Documentation: [https://www.ibm.com/docs/en/zvm/7.1?topic=commands-grep-search-file-specified-pattern](https://www.ibm.com/docs/en/zvm/7.1?topic=commands-grep-search-file-specified-pattern)
