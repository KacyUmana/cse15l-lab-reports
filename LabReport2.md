# Lab Report 2
## Part 1: `StringServer`

```
# code for StringServer
import java.io.IOException;
import java.net.URI;

class StringServer implements URLHandler {
    int num = 1;
    StringBuilder messageStringBuilder = new StringBuilder();
    
    public String handleRequest(URI url) {     
        if (url.getPath().equals("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s") && parameters.length == 2) {
                String message = parameters[1];
                messageStringBuilder.append(num).append(". ").append(message).append("\n");
                num++;
                return messageStringBuilder.toString();
            }
            return "Add message!";
        }

        else {
            return "Invalid input! Try again.";
        }
    }
}

class StringServerMain {
    public static void main(String[] args) throws IOException {
        if(args.length == 0) {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new StringServer());
    }
}
```
![Image](StringServerSS1.png)
the following methods would be called:

- StringServerMain.main: To start the server.
- StringServer.handleRequest: To handle the incoming HTTP request and add the message "Hello" to the messageStringBuilder.
- This code parses the provided port number from the command line arguments and starts the server with the StringServer to handle incoming requests.

The main method in the StringServerMain class would be called because you're starting the server from the command line with the provided port number.

Inside the main method, this code would execute:
```
int port = Integer.parseInt(args[0]);
Server.start(port, new StringServer());
```
Once the server is started, the StringServer instance will handle incoming requests. When accessing the URL "localhost:4001/add-message?s=Hello," the handleRequest method of the StringServer class will be called with the URI object representing this URL as its argument. Within the handleRequest method, the code will check if the request path is "/add-message," and it will proceed to parse the query parameters. In this case, it will split the query parameter by '=' and check if the parameter name is "s" and if the length of the parameters array is 2. If these conditions are met, the code will append the message "Hello" and all other following messages to the messageStringBuilder, increment the num variable, and return the updated message list.

StringServerMain.main(String[] args):

Arguments: args is an array of command-line arguments.
Relevant Values:
args[0]: The first element of the args array contains the port number provided as a command-line argument.

StringServer.handleRequest(URI url):

Argument: url is a URI object representing the incoming HTTP request URL.
Relevant Values:
url.getPath(): This method retrieves the path component of the URL. In this case, it will be "/add-message".
url.getQuery(): This method retrieves the query component of the URL. In this case, it will be "s=Hello".

StringServer Fields:

int num: An integer field used to keep track of the message number.
StringBuilder messageStringBuilder: A StringBuilder used to store and construct the response message

int num: The num field is used to keep track of the message number. In this specific request, since a new message is being added, the num field would be incremented by 1. If the initial value of num was 1, after processing this request, num would become 2.

StringBuilder messageStringBuilder: This StringBuilder is used to store and construct the response message. When you add a new message to it, it appends the message and increments the message number. In this specific request, the message "Hello" would be appended, and the response message would look something like "1. Hello\n" (assuming it's the first message added).
