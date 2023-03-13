# CSE 15L Lab Report 5
## Different Terminal Commands

There are different commands that can be used in the terminal, some of which are as follows:

`find` - This command helps you find certain files by several ways, and not just exclusively by the 'file name'

`less` - This command helps one to see the certain file contents one at a time. Sometimes, when using commands like `ls`, it may so happen that too
many file names or outputs are returned back to the terminal, making it difficult to read. This command makes reading the file contents very easy, as it
is possible to navigate back and forth in an easier way and results in faster loading speeds.

`grep` - This command is primarily used to search for a particular string in a group of files.

Of the above commands, I explored the 'find' command in Lab Report 3. I wish to explore the `grep` command in further detail in this lab report.

## grep Command Uses

### grep [file name] command
Checking whether a file with a specific name exists - With the help of the grep command, one can check whether a file containing certain characters exists.

<img width="550" alt="image" src="https://user-images.githubusercontent.com/89179888/224633416-a832793c-2e90-47f1-b716-f36f5c2fe352.png">

Taking the example of the command used in the Skill Demo 1, the command "grep -r -l "Lucayans"" recursively searches for the string "Lucayans" in all files and directories in the current directory, and its subdirectories.
The current directory in which I search for the string "Lucayans" is `/home/linux/ieng6/cs15lwi23/cs15lwi23amy/skill-demo1-server/skill-demo1-data`
It only prints the names of the files that contain the string "Lucayans".

<img width="565" alt="image" src="https://user-images.githubusercontent.com/89179888/224636211-6738fb58-8f55-4264-9764-614b7e982508.png">
There is a slight difference between this command and the previous command as mentioned above.


1) In the above command, "-r" stands for "recursive", meaning that the search will be performed in all subdirectories as well.
2) In the above command, "-l" stands for "files with matches", meaning that only the names of the files containing the search string will be printed, not the actual matching lines.

18 54
