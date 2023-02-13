# Lab Report 3

The command I chose was grep. The command searches within files to find matching patterns.

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
The output displays the paths to all the .txt files and the number of lines in each with the matching string. Here, it shows that ch1.txt has 1 line that matches 
and that the rest have 0 lines that match. This option would be useful if the user only needs to see the number of lines with matches for each file. This can be 
used to make succinct comparisons between multiple files.

For the second example, I searched one .txt file with the path `travel_guides/berlitz1/HandRHawaii.txt` for lines that matched "the".
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

For the first example, I searched the .txt files within the relative directory `non-fiction/OUP/Abernathy/` for a file that had the matching string "1940s". 
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

For the second example, I searched the .txt files within the directory `travel_guides/berlitz1/*.txt` for the string "❁". The string is present in 
multiple .txt files in this directory.
Command:
```
$ grep -l "❁" travel_guides/berlitz1/*.txt
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
5:In the late 1940s, Bond Stores, the largest men’s clothing chain at the time, created a sensation in New York City by offering a wide selection of suits with two pairs of pants instead of one, reintroducing a level of product choice not seen since before the war.1 When the line of hopeful buyers at its Times Square store stretched around the block, Bond had to impose a limit of two suits per customer. During World War II, the apparel and textile industries had been converted to supply field jackets, overcoats, and uniforms to the U.S. and Allied Forces. But in the years immediately following the war, returning soldiers, the end of rationing, and pent-up customer demand meant apparel was in short supply.
```
The output displays the number of the matching line followed by the line itself. This would be useful if the user wanted to find where in the file the matching string was.

For the second example, I searched the .txt files within the directory `travel_guides/berlitz2/` for files with lines that matched "Where To Go". There are multiple 
files in this directory with matching lines.
Command:
```
$ grep -n "Where To Go" travel_guides/berlitz2/*.txt
```
Output:
```
travel_guides/berlitz2/Beijing-WhereToGo.txt:5:Where To Go
travel_guides/berlitz2/CanaryIslands-WhatToDo.txt:48:Watch the birdie (and the dolphins). There are several animal/bird parks in the islands, Tenerife’s Loro Park, Gran Canaria’s Palmitos Park, or Lanzarote’s Guinate Tropical Park are all described in the Where To Go section of this guide. Others include the Parque Las Aguilas, Los Cristianos, Arona (Tenerife), which as the name implies, has an eagle show, all kinds of other birds and animals, and the new JungleRaid where kids of all ages can work their way through all kinds of obstacles.
travel_guides/berlitz2/CanaryIslands-WhatToDo.txt:50:Submarine Trips: see Where To Go for info on these excursions. Puerto Colón, Playa de Américas (Tenerife); Peurto de Mogán (Gran Canaria); and Puerto Calero (Lanzarote).
travel_guides/berlitz2/Paris-WhereToGo.txt:5:Where To Go
```
The output displays the paths to the files with the matching lines, the numbers of the matching lines, and the lines themselves.
