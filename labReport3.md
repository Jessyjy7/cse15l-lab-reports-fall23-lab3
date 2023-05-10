# Lab Report 3
## There will be four command-line options for find demonstrated in this lab, and each command-line will be presented with two examples.

## Command-line 1: `find -type`
The `-type` option allows you to search for files based on their type. The different types of files include regular files `(f)`, directories `(d)`, symbolic links `(l)`, named pipes `(p)`, sockets `(s)`, character devices `(c)`, and block devices `(b)`. 

Exampele 1: `find -type d`
This example is showing that `-find -type d` command is searching all the directories in `/technical`, we can use it to find all the directory types of a folder. (I found this command by asking ChatGPT)

```
jessyjy7@Jiayings-MBP docsearch % cd technical 
jessyjy7@Jiayings-MBP technical % find * -type d
911report
biomed
government
government/About_LSC
government/Env_Prot_Agen
government/Alcohol_Problems
government/Gen_Account_Office
government/Post_Rate_Comm
```

Example 2: `find -type f`
This exmaple is showing that `-find -type f` command is searching all the files in /technical/government, we can use it to find all the files in a directory.(I found this command by asking ChatGPT)

```
jessyjy7@Jiayings-MBP technical % find ./government/Alcohol_Problems  -type f
./government/Alcohol_Problems/Session2-PDF.txt
./government/Alcohol_Problems/Session3-PDF.txt
./government/Alcohol_Problems/DraftRecom-PDF.txt
./government/Alcohol_Problems/Session4-PDF.txt
```

## Command-line 2: `find -size`
The -size option allows you to search for files based on their size. You can specify the size in bytes, kilobytes, megabytes, gigabytes, or terabytes.

Example 1: `find -size +100k`
This example is showing that `-size +100k` command s searching all the directories that is larger than 100kb in `/technical/911report`, this command can be used for filtering extremely large contents.(I found this command by asking ChatGPT)

```
jessyjy7@Jiayings-MBP technical % find ./911report -size +100k 
./911report/chapter-13.4.txt
./911report/chapter-13.5.txt
./911report/chapter-13.2.txt
./911report/chapter-13.3.txt
./911report/chapter-3.txt
./911report/chapter-1.txt
./911report/chapter-6.txt
./911report/chapter-7.txt
./911report/chapter-9.txt
./911report/chapter-12.txt
```
Example 2: `find -size -100k`
This example is showing that `-size +100k` command s searching all the directories that is smaller than 100kb in `/technical/911report`, this command can be used for filtering extremely small contents.(I found this command by asking ChatGPT)

```
jessyjy7@Jiayings-MBP technical % find ./911report -size -100k
./911report
./911report/chapter-13.1.txt
./911report/chapter-2.txt
./911report/chapter-5.txt
./911report/chapter-8.txt
./911report/preface.txt
./911report/chapter-10.txt
./911report/chapter-11.txt
```

## Command-line 3: `find -exec`
The -exec option allows you to execute a command on the files that are found by find. You can use {} as a placeholder for the filename(s) that are found.

Example 1: `find -exec wc -l {} +`
This example is showing that `-exec wc -l {} +` command is counting the number of lines of each `.txt` files in the `Alcohol_Problems` directory while finding these files using `find` command-line. This command allows us to execute both `find` and another command-line like `wc`.(I found this command by asking ChatGPT)

```
jessyjy7@Jiayings-MBP technical % find ./government/Alcohol_Problems/*.txt -exec wc -l {} +
     570 ./government/Alcohol_Problems/DraftRecom-PDF.txt
     637 ./government/Alcohol_Problems/Session2-PDF.txt
    1679 ./government/Alcohol_Problems/Session3-PDF.txt
    1375 ./government/Alcohol_Problems/Session4-PDF.txt
    4261 total
```

Example 2: `find -exec rm {} \;`
I first created a directory called uselessFolder under technical, and I also created three empty `.txt` files called `useless1.txt`, `useless2.txt`, `useless3.txt` under this directory(to make sure nothing important will be removed by the command.) Then `find ./uselessFolder -exec rm {} \;` command is finding the directory called uselessFolder then remove everything within this directory. This command can help us to delete multiple directories or files within one command.(I found this command by asking ChatGPT)

```
jessyjy7@Jiayings-MBP technical % find ./uselessFolder -exec rm {} \;                   
rm: ./uselessFolder: is a directory
jessyjy7@Jiayings-MBP technical % 
```

## Command-line 4: `find -mtime`
The -mtime option allows you to filter the results of find by the modification time of the file. You can specify the number of days since the file was last modified (e.g., -mtime 0 for files modified today). 

Example 1: `find -mtime +7`
This command-line can find the directories that are modified more than 7 days ago, in this example the command found all the `.txt` files under `technical/government/Alcohol_Problems` that are motified more than 7 days ago. This command can help us to filter the files and narrow down to our target file faster.(I found this command by asking ChatGPT)

```
jessyjy7@Jiayings-MBP technical % find ./government/Alcohol_Problems/*.txt -mtime +7
./government/Alcohol_Problems/DraftRecom-PDF.txt
./government/Alcohol_Problems/Session2-PDF.txt
./government/Alcohol_Problems/Session3-PDF.txt
./government/Alcohol_Problems/Session4-PDF.txt
```


Example 2:
This command-line can find the directories that are modified within 30 days, in this example the command found all the `.txt` files under `technical/government/Alcohol_Problems` that are motified within 30 day. This command can help us to filter the files and narrow down to our target file faster.(I found this command by asking ChatGPT)

```
jessyjy7@Jiayings-MBP technical % find ./government/Alcohol_Problems/*.txt -mtime -30
./government/Alcohol_Problems/DraftRecom-PDF.txt
./government/Alcohol_Problems/Session2-PDF.txt
./government/Alcohol_Problems/Session3-PDF.txt
./government/Alcohol_Problems/Session4-PDF.txt
```
