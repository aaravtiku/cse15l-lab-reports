# CSE15L Lab Report 2
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
The code for Server.java is as follows:
```java
// A simple web server using Java's built-in HttpServer

// Examples from https://dzone.com/articles/simple-http-server-in-java were useful references

import java.io.IOException;
import java.io.OutputStream;
import java.net.InetSocketAddress;
import java.net.URI;

import com.sun.net.httpserver.HttpExchange;
import com.sun.net.httpserver.HttpHandler;
import com.sun.net.httpserver.HttpServer;

interface URLHandler {
    String handleRequest(URI url);
}

class ServerHttpHandler implements HttpHandler {
    URLHandler handler;
    ServerHttpHandler(URLHandler handler) {
      this.handler = handler;
    }
    public void handle(final HttpExchange exchange) throws IOException {
        // form return body after being handled by program
        try {
            String ret = handler.handleRequest(exchange.getRequestURI());
            // form the return string and write it on the browser
            exchange.sendResponseHeaders(200, ret.getBytes().length);
            OutputStream os = exchange.getResponseBody();
            os.write(ret.getBytes());
            os.close();
        } catch(Exception e) {
            String response = e.toString();
            exchange.sendResponseHeaders(500, response.getBytes().length);
            OutputStream os = exchange.getResponseBody();
            os.write(response.getBytes());
            os.close();
        }
    }
}

public class Server {
    public static void start(int port, URLHandler handler) throws IOException {
        HttpServer server = HttpServer.create(new InetSocketAddress(port), 0);

        //create request entrypoint
        server.createContext("/", new ServerHttpHandler(handler));

        //start the server
        server.start();
        System.out.println("Server Started! Visit http://localhost:" + port + " to visit.");
    }
}
```
### Starting the Server

1) I first compiled the `Server.java` and `StringServer.java` files.

2) I hosted the server locally on my laptop using the following code:

```
javac Server.java StringServer.java

java StringServer 4000
```
3) The local port in which the server is hosted is 2023.

4) The given string is parsed into an int type and is stored in `port`

5) The above is passed as an argument to `Server.start`

6) The server is started and a link to visit the server is generated. This can be seen below:

<img width="597" alt="image" src="https://user-images.githubusercontent.com/89179888/218656359-d67d3492-eb93-41a0-a500-a3e24da8e1e0.png">

### Adding Messages

<img width="544" alt="image" src="https://user-images.githubusercontent.com/89179888/218659383-413c94c7-f851-456e-b4db-d26d87b0f3c5.png">


1) When the server is being hosted, you can just make a change to the URL to modify the page.

2) Adding `Hi!` to the webpage by changing the URL - `http://localhost:2023/add-message?s=Hi!`

3) The above URL is used as the argument in `handleRequest`

4) The `url.getQuery().split("=")` splits the request into two different parameters.

5) `parameters[0]` contains 's' and `parameters[1]` contains 'Hi!'

6) 'Hi!' is added to `stringgiven` and that value is returned, and it gets displayed on the webpage.


### Adding a Second Message

<img width="633" alt="image" src="https://user-images.githubusercontent.com/89179888/218659321-711fd534-5585-4097-97a2-70c47f343b43.png">

1) Previously, I already added the message `Hi!` by making minor changes to the URL.

2) I made a minor change to the URL by adding `http://localhost:2023/add-message?s=Aarav`

3) The above URL is used as the argument in `handleRequest`

4) The `url.getQuery().split("=")` splits the request into two different parameters.

5) `parameters[0]` contains 's' and `parameters[1]` contains 'Aarav'

6) 'Aarav' is added to `stringgiven` and that value is returned, and it gets displayed on the webpage.

7) Since 'Aarav' is the second value being added to 'stringgiven', the `\n` separates 'Hi!' and 'Aarav' into two different lines.

## Part 2

### JUnit Tests and Symptoms

The failure inducing JUnit test is as follows:

```java
@Test
public void testReverseInPlace(){
    int [] sampleArray = {3,7,8,9};
    ArrayExamples.reverseInPlace(sampleArray);
    assertArrayEquals(new int[]{9,8,7,3}, sampleArray);
}
```
The JUnit test that doesn't cause a failure is as follows:

```java
@Test
public void testReverseInPlace(){
    int [] input = {5};
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(new int[]{5}, input);
}
```

The symptoms are as follows:

<img width="617" alt="image" src="https://user-images.githubusercontent.com/89179888/218661886-821e9ad7-27d8-4daf-beb6-94abd56da2f6.png">

The reverseInPlace method before the fix:

```java
static void reverseInPlace(int[] arr){
    for(int i = 0; i < arr.length; i += 1){
        arr[i] = arr[arr.length - i - 1];
    }
}
```

The reverseInPlace method after the fix:

```java
static void reverseInPlace(int[] arr){
    int tmp;
    for(int i = 0; i < arr.length/2; i += 1){
        tmp = arr[i];
        arr[i] = arr[arr.length - i - 1];
        arr[arr.length - i - 1] = tmp;
    }
}
```

When initially testing `reverseInPlace`, the output was incorrect as `reverseInPlace` was incorrectly reversing the array. In the given code, the problem was that the array was replacing the values of the array using edited values.

To fix this issue, I created a `tmp` variable which stores that value of each index, and then equated `arr[i]` to `arr[arr.length - 1 - i]`(the corresponding opposite side) and equate that to the `tmp` variable. By doing so, I was able to update the values and made the for loop iterate for half the original number of values.






## Part 3
In the second Lab Session, I re-hosted a local server on my laptop. This was not the first time I did this,
as I have previously hosted a website that I built on my laptop. However, it was the first time I connected using an SSH
key to a server hosted by one of the computers in UCSD(201/202/203) and host my server there. I have never had an issue before with
hosting a server due to overcrowding(people using the same port on the local server), so this was a learning experience as I had to change the port
number. Also, it was fun to experiment with the code running on my friend's laptop on my own laptop just by changing the port number.
