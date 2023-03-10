# CSE15L Lab Report 4

## Challenge Tasks
In this lab report, I will discuss the steps involved for the Lab Challenge that took place on 22/02.

Before starting the challenge, it is important to generate SSH keys for both ieng6 and Github first. It can be done as follows:

### Generating SSH keys for ieng6

1) Login to the ieng6 computer through the terminal, as shown below in the picture:

<img width="578" alt="image" src="https://user-images.githubusercontent.com/89179888/221725151-9bb5217f-a8c8-4c67-a64c-1311edd944c9.png">

2) Run the command `ssh-keygen` in the command terminal, so that it generates a randomart image in the local computer:

<img width="581" alt="image" src="https://user-images.githubusercontent.com/89179888/221729324-ee5e7970-83dd-48bf-81e7-5e1206cdd8f1.png">

3) On the local computer, run the command - scp `<path to the public SSH key>` `cs15lwi23__@ieng6.ucsd.edu:~/.ssh/authorized_keys`. After running this
command, the command terminal will ask for your ieng6 password and it should appear like this:

<img width="555" alt="image" src="https://user-images.githubusercontent.com/89179888/221729673-c9f3817b-73e0-48fb-a742-8b4f916c8861.png">

### Generating SSH keys for GitHub

1) Login to the ieng6 computer through the terminal, as shown below in the picture:

<img width="578" alt="image" src="https://user-images.githubusercontent.com/89179888/221725151-9bb5217f-a8c8-4c67-a64c-1311edd944c9.png">

2) Run the command `ssh-keygen` in the command terminal, so that it generates a randomart image. The difference between this step 2 and the step 2
in the previous task is that this time, you are running the command inside ieng6, whereas last time, you were doing the same task in your local computer.

<img width="581" alt="image" src="https://user-images.githubusercontent.com/89179888/221729324-ee5e7970-83dd-48bf-81e7-5e1206cdd8f1.png">

3) Enter the following command in the terminal - `cat <path of your ssh key .pub file>`

4) Go to GitHub and save the SSH key details as seen below. Once this has been done, you can additionally go back to the command terminal and check
whether the ssh key was successfully added or not:
![image](https://user-images.githubusercontent.com/89179888/221731062-62b578a4-c838-43f0-bc1c-896e78c28b6a.png)

<img width="658" alt="image" src="https://user-images.githubusercontent.com/89179888/221740914-360a199a-ae20-4099-85a8-e6f97ffb499e.png">

Now, we can work on the challenge tasks(4-9):

### The Challenge 

Task 4) Logging in to the ieng6 account. As demonstrated above, we can login to the ieng6 account by typing the command `ssh cs15lwi23amy@ieng6.ucsd.edu` and then press the `<enter>` key as demonstrated below:

<img width="570" alt="image" src="https://user-images.githubusercontent.com/89179888/224908603-620ece5b-020c-4d40-9e17-976bd8868879.png">

Task 5) Cloning the fork of the repository from Github:

<img width="353" alt="image" src="https://user-images.githubusercontent.com/89179888/224796247-73c5220c-3cae-43fc-a634-623484b36a7a.png">

This indicates that I have successfully forked the repository from my GitHub account. 

<img width="434" alt="image" src="https://user-images.githubusercontent.com/89179888/224796736-a57524ea-8541-4836-860c-686f276d9483.png">

From my GitHub account, I get the above link which I use to clone the fork of the repository from my GitHub account in the terminal and use the command `git clone git@github.com:aaravtiku/lab7.git` and then press `<enter>`. This is demonstrated below:

<img width="851" alt="image" src="https://user-images.githubusercontent.com/89179888/221741147-b61e2a97-de66-43da-858e-6e0354373783.png">

Task 6) Running the JUnit tests

As completed during Week 3, we need to first compile and then run the JUnit tests. This can be done by running the
following commands:
  
  1) `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` `<enter>`
  
  2) `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples` `<enter>`

The result that we get when running these commands is as follows:

<img width="569" alt="image" src="https://user-images.githubusercontent.com/89179888/224799732-4589936a-b492-43be-b359-b4ddfd1956f7.png">

Task 7) As there are some errors, as the code is not passing all the test cases, we need to edit the code so as to ensure that the code passes
all the test cases.

To make changes to the code within the terminal itself, I used the command `nano ListExamples.java`, and navigated using the following commands:

`<down(until I reached line 43)><right(12 times)><backspace><2>`
  
 By completing the commands mentioned above, I fixed the error in the code.
 
<img width="337" alt="image" src="https://user-images.githubusercontent.com/89179888/221742640-4c423d16-e52d-43b2-a9ec-41aa24c837eb.png">

Once done, I pressed the following keys to save my changes and exit the terminal text-based editor:

`<Control O><enter>` (to save the changes that I made in my code)
`<Control X>` (to exit the terminal text-based editor)

Now, the code has been edited and one can test it out.

Task 8) Now, we can test out the code using the JUnit tests to assess whether everything works seamlessly. 

To do this, I pressed the following keys:

`<up><up><enter>` (compilation of the JUnit tests)

`<up><up><enter>` (Running the JUnit tests, the command is the same as the above command because now the 2nd command is two commands above)

  I completed the above steps rather than just copy-pasting the commands because they were present in my command terminal history. 
Now, I get the following message on the JUnit terminal:

<img width="924" alt="image" src="https://user-images.githubusercontent.com/89179888/221743861-6026aa14-0efa-4465-8ed6-e8ca967b37e3.png">

This indicates that the JUnit tests have been successful and we don't need to do anything further to the code.

Task 9) The final task is to commit and push the changes to the Github account. This can be by typing the following commands in the terminal:

  1)`git add .` - adds all the changes in the current working directory and its subdirectories to the staging area. The staging area is one prepares changes to be committed to the Git repository. After writing this command, I pressed the `<enter>` key.

  2)`git commit -m "changes reflected"` - commits the change in the working directory with the message "changes reflected". After writing this command, I pressed the `<enter>` key.
  
  It should appear like this in the terminal once the changes have been committed:
  
  <img width="568" alt="image" src="https://user-images.githubusercontent.com/89179888/224816003-65e70798-3139-4578-9b7b-6c8170f7210e.png">

  3)`git push` - pushes the new changes to GitHub. After writing this command, I pressed the `<enter>` key.

Upon completing the above steps in the terminal, you should get the following response:

<img width="642" alt="image" src="https://user-images.githubusercontent.com/89179888/221744443-18d9be8a-e673-459b-ba63-d8d526e5dad6.png">

The completion of this step means that you have completed the competition successfully.













