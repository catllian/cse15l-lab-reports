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
The option -name searches for and lists the files or directories with names that match the given name argument.

For the first example, I searched the directory ./non-fiction/OUP for two existing files with the name ch10.txt.
Command:
```
$ find ./non-fiction/OUP -name ch10.txt
```
Output:
```
./non-fiction/OUP/Fletcher/ch10.txt
./non-fiction/OUP/Kauffman/ch10.txt
```
The output displays the paths for the matching files. This command is useful if the user wants to find a file or directory with a specific name.

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
The option -regex searches for and lists the files or directories with the given pathname.

For the first example, I searched the current directory, the written_2 folder, for a file with the path ./non-fiction/OUP/Abernathy/ch1.txt.
Command:
```
$ find ./ -regex ./non-fiction/OUP/Abernathy/ch1.txt
```
Output:
```
./non-fiction/OUP/Abernathy/ch1.txt
```
The output displays the matching file path. This option is useful if the user wants to see if a certain path exists.

For the second example, I searched the current directory, the written_2 folder, for a directory with the path ./travel_guides/berlitz2.
Command:
```
$ find ./ -regex ./travel_guides/berlitz2
```
Output:
```
./travel_guides/berlitz2
```
The output displays the matching directory path.

## Fourth Option: -type
The -type option searches for directories or files that match given type argument.

For the first example, I searched the directory ./non-fiction/OUP/Castro for files of type `f` (`f` argument means plain file type). The Castro folder has 14 .txt files, and .txt files are plain files.
Command:
```
$ find ./non-fiction/OUP/Castro -type f
```
Output:
```
./non-fiction/OUP/Castro/chA.txt
./non-fiction/OUP/Castro/chB.txt
./non-fiction/OUP/Castro/chC.txt
./non-fiction/OUP/Castro/chL.txt
./non-fiction/OUP/Castro/chM.txt
./non-fiction/OUP/Castro/chN.txt
./non-fiction/OUP/Castro/chO.txt
./non-fiction/OUP/Castro/chP.txt
./non-fiction/OUP/Castro/chQ.txt
./non-fiction/OUP/Castro/chR.txt
./non-fiction/OUP/Castro/chV.txt
./non-fiction/OUP/Castro/chW.txt
./non-fiction/OUP/Castro/chY.txt
./non-fiction/OUP/Castro/chZ.txt
```
The output displays the paths for all 14 files within the directory, since they match the plain file type. This option would be useful if the user wants to find directories or files within a directory of a specific type.

For the second example, I searched the current directory, the written_2 folder, for all directories within it (`d` argument means directory). 
Command:
```
$ find ./ -type d
```
Output:
```
./
./non-fiction
./non-fiction/OUP
./non-fiction/OUP/Abernathy
./non-fiction/OUP/Berk
./non-fiction/OUP/Castro
./non-fiction/OUP/Fletcher
./non-fiction/OUP/Kauffman
./non-fiction/OUP/Rybczynski
./travel_guides
./travel_guides/berlitz1
./travel_guides/berlitz2
...
```
The output displays the paths of all the directories within the current directory.

## Reference
IBM Documentation: [https://www.ibm.com/docs/en/aix/7.2?topic=f-find-command](https://www.ibm.com/docs/en/aix/7.2?topic=f-find-command)
