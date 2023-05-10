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

