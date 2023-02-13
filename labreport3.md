# Week 3 Lab Report
## Different Terminal Commands

There are different commands that can be used in the terminal, some of which are as follows:

`find` - This command helps you find certain files by several ways, and not just exclusively by the 'file name'

`less` - This command helps one to see the certain file contents one at a time. Sometimes, when using commands like `ls`, it may so happen that too
many file names or outputs are returned back to the terminal, making it difficult to read. This command makes reading the file contents very easy, as it
is possible to navigate back and forth in an easier way and results in faster loading speeds.

`grep` - This command is primarily used to search for a particular string in a group of files.

Of the above commands, I wish to explore the `find` command in greater detail:

1)Checking whether a file with a specific name exists - There are two main ways in which this can be done.
One of the ways of doing this is by checking files from the root directory and performing a search on a large
number of files using the command `$ find / -name "WhereToIndia.txt"` . Depending on whether you have file permissions
to access all files, it may work or not work. For example, when using this command in the `ieng6` server, it did not
work. Another variation to this command is the `$ find . -name "WhereToIndia.txt"`, which checks only for files
within a particular directory, and is a better option in case you know where the file should exist.

An example of using this command is as follows:
<img width="527" alt="image" src="https://user-images.githubusercontent.com/89179888/218334085-71ae898f-3aac-4f18-8ebf-b540d9c27735.png">

Another example of using this command is as follows:
<img width="523" alt="image" src="https://user-images.githubusercontent.com/89179888/218334127-7283972c-a612-432b-9c6c-ee4dcd25388b.png">

In the first example, we just checked for the existence of a file containing 'WhereToIndia', whereas in the second command,
we checked for all the files of the form "txt".

2)Converting the files present in a particular directory into a '.txt' form - As demonstrated in task 5 of the skill demo,
it is possible to convert a list of files present in a particular directory into a .txt file. This is useful for computing the
number of files present in a given directory, the number of words or characters present in a given 
directory. 

`find written_2/ > find-results.txt` - This command converts the content present in `written_2` into a file named `find-results.txt`.
The below image illustrates how it is possible to find details about the content contained inside `written_2`

<img width="572" alt="image" src="https://user-images.githubusercontent.com/89179888/218352439-a0fd78d8-85fd-479a-96bc-a46506fa0c08.png">
Therefore, there are 224 files, 224 words and 11245 characters.

Similarly, I used this command to find the number of travel guides inside the 'berlitz1' subdirectory as follows:
<img width="548" alt="image" src="https://user-images.githubusercontent.com/89179888/218353603-f503f40d-bfcd-4684-9e25-a507ba377be0.png">

Hence, there are 101 travel guides in the berlitz1 subdirectory.

3) Finding a file based on the creation time - It is possible to find files absed on when they were created using the `-mtime` command. An example of this can be seen below:
4) <img width="570" alt="image" src="https://user-images.githubusercontent.com/89179888/218355170-e7802ef8-af86-4ef2-9571-4233bff40386.png">

In the above command, I checked the list of files that were created in a period of time greater than 7 days back.





