# CSE15L Week 3 Lab Report
## Part 1
The first step of the Lab Activity is to modify the NumberServer code and fix it so that it takes in a string and perform operations with it instead of number as in the NumberServer code, and rename it StringServer.
After making a few minor changes to my code, I renamed the code StringServer. The revised code is as follows:

```java
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    int num = 0;
    String stringgiven = "";
    public String handleRequest(URI url) {
        if (url.getPath().equals("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if(parameters[0].equals("s")){
                stringgiven += "\n" + parameters[1];
                return stringgiven;
            }
        }
        return "Please use it in the format /add-message";
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```
You need to enter a few commands in the terminal. They are as follows:

`/add-message?s=Hello` - Adds 'Hello' to the localhost website

`/add-message?s=How are you` - Adds 'How are you' to the localhost website


I experimented this code and opened a LocalHost server in my laptop and added the comments 'Hei' and 'Guten Tag'.

<img width="1339" alt="image" src="https://user-images.githubusercontent.com/89179888/215678024-6a3f312e-d463-4b73-b0bf-75da30ae3258.png">
<img width="1338" alt="image" src="https://user-images.githubusercontent.com/89179888/215678115-9d84edfe-a3e9-4b52-9423-227495abdd1b.png">

## Part 2
<img width="703" alt="image" src="https://user-images.githubusercontent.com/89179888/215677298-10fe522e-ae59-4b0a-a45a-f1c675929ffd.png">

<img width="709" alt="image" src="https://user-images.githubusercontent.com/89179888/215677803-a3f32347-bde2-4aa2-8a66-3e7d15eb0681.png">


## Part 3
In the second Lab Session, I re-hosted a local server on my laptop. This was not the first time I did this,
as I have previously hosted a website that I built on my laptop. However, it was the first time I connected using an SSH
key to a server hosted by one of the computers in UCSD(201/202/203) and host my server there. I have never had an issue before with
hosting a server due to overcrowding(people using the same port on the local server), so this was a learning experience as I had to change the port
number. Also, it was fun to experiment with the code running on my friend's laptop on my own laptop just by changing the port number.
