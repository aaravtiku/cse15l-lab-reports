# CSE 15L Lab Report 5
## Different Terminal Commands

There are different commands that can be used in the terminal, some of which are as follows:

`find` - This command helps you find certain files by several ways, and not just exclusively by the 'file name'

`less` - This command helps one to see the certain file contents one at a time. Sometimes, when using commands like `ls`, it may so happen that too
many file names or outputs are returned back to the terminal, making it difficult to read. This command makes reading the file contents very easy, as it
is possible to navigate back and forth in an easier way and results in faster loading speeds.

`grep` - This command is primarily used to search for a particular string in a group of files.

Of the above commands, I explored the `find` command in Lab Report 3. I wish to explore the `grep` command in further detail in this lab report.

## grep Command Uses

### grep [file name] command

Checking whether a file with a specific name exists - With the help of the grep command, one can check whether a file containing certain characters exists.

<img width="550" alt="image" src="https://user-images.githubusercontent.com/89179888/224633416-a832793c-2e90-47f1-b716-f36f5c2fe352.png">

Taking the example of the command used in the Skill Demo 1, the command "grep -r -l "Lucayans"" recursively searches for the string "Lucayans" in all files and directories in the current directory, and its subdirectories.
The current directory in which I search for the string "Lucayans" is `/home/linux/ieng6/cs15lwi23/cs15lwi23amy/skill-demo1-server/skill-demo1-data`
It only prints the names of the files that contain the string "Lucayans", which in this case is Bahamas-History.txt

<img width="565" alt="image" src="https://user-images.githubusercontent.com/89179888/224636211-6738fb58-8f55-4264-9764-614b7e982508.png">
There is a slight difference between this command and the previous command as mentioned above, as it prints all lines that contain the word "Lucayans" in all files and subdirectories under the specified directory, while the first command will only print the names of files that contain the word "Lucayans".


1) In the above commands, `-r` stands for "recursive", meaning that the search will be performed in all subdirectories as well.
2) In the above commands, `-l` stands for "files with matches", meaning that only the names of the files containing the search string will be printed, not the actual matching lines.

### Search for lines that contain a pattern and output the results to a new file

With the help of `grep`, it is possible to check for a certain pattern and redirect the results to a completely new file.

<img width="567" alt="image" src="https://user-images.githubusercontent.com/89179888/224763777-1adc0536-81e9-4ed1-bda2-74f6cd194258.png">

The above use of the `grep` command is used in the Skill Demo 1. This command uses the `grep` command to search for lines in the file `find-results.txt` that contain the string `.txt`. The output of the grep command is redirected to a file called `grep-results.txt`. This means that instead of seeing the output on the terminal, it will be saved in a file called `grep-results.txt`.

<img width="574" alt="image" src="https://user-images.githubusercontent.com/89179888/224765847-bcd61feb-7090-436f-98e6-b9a19f859c2e.png">

While executing the above command, my current directory is `/home/linux/ieng6/cs15lwi23/cs15lwi23amy/skill-demo1-server/skill-demo1-data/written_2/travel_guides`. I initially use the find command to search for files and directories in `berlitz1`. The output of the find command is redirected to a file called `travel-guides.txt`. The results are saved in a file called `travel-guides.txt`. I then use the `grep` command to search for the keyword 'Mallorca', and the output is a file containing all files containing the word 'Mallorca', and is saved in `grep-results.txt`. I then use the command `wc` to check the frequency of the word 'Mallorca', and since there are 5 separate lines, it means that the word 'Mallorca' is present in 5 separate files.

### Counting the number of files in a directory

The `grep` command can also be used to count the number of files inside of a directory. This can be done in the following way:

Example 1:

<img width="524" alt="image" src="https://user-images.githubusercontent.com/89179888/224774661-c9ce2adf-7fd3-4b51-b664-004ee9ef824c.png">

Example 2:

<img width="502" alt="image" src="https://user-images.githubusercontent.com/89179888/224774746-29395e7c-2ec1-470b-a2b7-5147a1bf4f44.png">

In the above command, I check the number of files present inside of different directories. In the first image, my current working directory is `/home/linux/ieng6/cs15lwi23/cs15lwi23amy/skill-demo1-server/skill-demo1-data/written_2/travel_guides/berlitz1`, whereas in the second image, my current working directory is `/home/linux/ieng6/cs15lwi23/cs15lwi23amy/skill-demo1-server/skill-demo1-data/written_2/travel_guides/berlitz2`. According to the reponse to the commands typed, there are 101 files inside of `berlitz1`, whereas there are 78 files inside of `berlitz2`.

### Coloring a specific part of the text
It is possible to color a specific part of the text using the `grep` command when you mention the particular string that you want to be colored.

<img width="566" alt="image" src="https://user-images.githubusercontent.com/89179888/224779268-1c39378b-8a28-4032-af8c-540406fe7619.png">

In the above image, my current directory is `/home/linux/ieng6/cs15lwi23/cs15lwi23amy/skill-demo1-server/skill-demo1-data/written_2/travel_guides/berlitz2`. I execute the command, `grep --color "12 October 1492" Bahamas-History.txt`, which colors the part '12 October 1492' inside of `Bahamas-History.txt`. By default, the color appears to be red. If we want to change the color of the text, we can do it in the following way:

<img width="567" alt="image" src="https://user-images.githubusercontent.com/89179888/224780306-e46e4cb6-a82a-47ef-ad98-ae53747e3ded.png">

The command `export GREP_COLORS='ms=01;34` sets the default color to blue, so when you execute the same command as done in the first example, instead of red, the part of the text that you want to be colored will now be colored blue instead.

## Acknowledgements
I used three sources for writing the Week 5 Lab Report:

1)[Markdown Guide](https://www.markdownguide.org/cheat-sheet/)

2)[grep Commands in Linux](https://www.freecodecamp.org/news/grep-command-in-linux-usage-options-and-syntax-examples/#:~:text=Grep%20is%20a%20useful%20command,a%20powerful%20command%20to%20use.)

3)[ChatGPT](https://chat.openai.com/)








