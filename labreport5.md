# Lab Report 4

The command I chose to explore options for is find. The command searches through the paths of a directory and lists the files and directories within it. The "normal" format of the command is:
```
find <path>
```
The output will list the files and directories within the directory of the given path.

## First Option: - ls
The option -ls prints the corresponding statistics of the files and directories found.

For the first example, I find used the command `cd written_2` to get from the docsearch directory to the written_2 directory. I used the find command with the -ls option for the directory ./non-fiction/OUP/Berk.

Command:
```
$ find ./non-fiction/OUP/Berk -ls
```
Output:
```
28147497671137754      0 drwxr-xr-x   1 cathe    197609          0 Feb  2 16:22 ./non-fiction/OUP/Berk
33214047251929585     92 -rw-r--r--   1 cathe    197609      92576 Feb  2 16:22 ./non-fiction/OUP/Berk/ch1.txt
30117822508112372    104 -rw-r--r--   1 cathe    197609     103190 Feb  2 16:22 ./non-fiction/OUP/Berk/ch2.txt
37999121856010715    104 -rw-r--r--   1 cathe    197609     103804 Feb  2 16:22 ./non-fiction/OUP/Berk/CH4.txt
32932572275218938     68 -rw-r--r--   1 cathe    197609      67091 Feb  2 16:22 ./non-fiction/OUP/Berk/ch7.txt
```
The output shows all of the files within the Berk folder with the corresponding statistical information. This option is useful if the user wants to see information about particular files or directories and/or wants to compare information.

For the second example, I searched the directory ./travel_guides for files and directories.
Command:
```
$ find ./travel_guides -ls
```
Output:
```
11540474045209429      0 drwxr-xr-x   1 cathe    197609          0 Feb  2 16:22 ./travel_guides
 7036874417838948     40 drwxr-xr-x   1 cathe    197609          0 Feb  2 16:22 ./travel_guides/berlitz1
41939771529960314     20 -rw-r--r--   1 cathe    197609      16519 Feb  2 16:22 ./travel_guides/berlitz1/HandRHawaii.txt
24769797950610318      2 -rw-r--r--   1 cathe    197609       1222 Feb  2 16:22 ./travel_guides/berlitz1/HandRHongKong.txt
 7881299347970960      1 -rw-r--r--   1 cathe    197609        695 Feb  2 16:22 ./travel_guides/berlitz1/HandRIbiza.txt
33776997205351315     28 -rw-r--r--   1 cathe    197609      26084 Feb  2 16:22 ./travel_guides/berlitz1/HandRIsrael.txt
12947848928762779      1 -rw-r--r--   1 cathe    197609        955 Feb  2 16:22 ./travel_guides/berlitz1/HandRIstanbul.txt
29273397577980858     28 -rw-r--r--   1 cathe    197609      25813 Feb  2 16:22 ./travel_guides/berlitz1/HandRJamaica.txt
39125021762853823      2 -rw-r--r--   1 cathe    197609       1477 Feb  2 16:22 ./travel_guides/berlitz1/HandRJerusalem.txt
 7036874417839042      2 -rw-r--r--   1 cathe    197609       1562 Feb  2 16:22 ./travel_guides/berlitz1/HandRLakeDistrict.txt
 ...
```
Only the first 10 lines of output are shown because the actual output was to long to include. The output shows the directories and files within the ./travel-guides directories with the corresponding statistical information.

## Second Option: -name
The option -name is meant to search for and list only the files or directories with names that match the given name argument

For the first example, I searched the directory ./non-fiction/OUP/Kauffman for an existing file with the name ch10.txt.
Command:
```
$ find ./non-fiction/OUP/Kauffman -name ch10.txt
```
Output:
```
./non-fiction/OUP/Kauffman/ch10.txt
```
The output displays the path for the matching file. This command is useful if the user wants to find a file or directory with a specific name.

For the second example, I searched the directory ./travel_guides for an existing directory with the name berlitz1.
Command:
```
$ find ./travel_guides -name berlitz1
```
Output:
```
./travel_guides/berlitz1
```
The output displays the path of the matching directory.

## Third Option: -regex
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
travel_guides/berlitz2/CanaryIslands-WhatToDo.txt:48:Watch the birdie (and the dolphins). There are several animal/bird parks in the islands, Tenerife’s Loro Park, Gran Canaria’s Palmitos Park, or Lanzarote’s Guinate Tropical Park are all described in the Where To Go section of this guide. Others include the Parque Las Aguilas, Los Cristianos, Arona (Tenerife), which as the name implies, has an eagle show, all kinds of other birds and animals, and the new JungleRaid where kids of all ages can work their way through all kinds of obstacles.
travel_guides/berlitz2/CanaryIslands-WhatToDo.txt:50:Submarine Trips: see Where To Go for info on these excursions. Puerto Colón, Playa de Américas (Tenerife); Peurto de Mogán (Gran Canaria); and Puerto Calero (Lanzarote).
travel_guides/berlitz2/Paris-WhereToGo.txt:5:Where To Go
```
The output displays the paths to the files with the matching lines, the matching line numbers, and the lines themselves.

## Fourth Option: -type
The -v option looks for lines in files that don't match.

For the first example, I searched one .txt file with the path `non-fiction/OUP/Abernathy/ch1.txt` for lines without the string "the".
Command:
```
$ grep -v "the" non-fiction/OUP/Abernathy/ch1.txt
```
Output:
```
Five Decades of Change
A Dying Industry—or Not?
The Channel Perspective: Five Propositions
Proposition 1:  The retail, apparel, and textile sectors are increasingly linked as a channel through information and distribution relationships.
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
travel_guides/berlitz2/Algarve-History.txt:Kingdom’s End
travel_guides/berlitz2/Algarve-History.txt:
travel_guides/berlitz2/Algarve-History.txt:
...
```
I included only the first 10 lines of output because there were too many lines. The output displays the lines in the .txt files without the string "a", 
including empty lines.

## Reference
IBM Documentation: [https://www.ibm.com/docs/en/aix/7.2?topic=f-find-command](https://www.ibm.com/docs/en/aix/7.2?topic=f-find-command)
