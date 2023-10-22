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

The main method in the StringServerMain class would be called because you're starting the server from the command line with the provided port number.

Inside the main method, the following code would execute:
```
int port = Integer.parseInt(args[0]);
Server.start(port, new StringServer());
```
the following methods would be called:

- StringServerMain.main: To start the server.
- StringServer.handleRequest: To handle the incoming HTTP request and add the message "Hello" to the messageStringBuilder.
- This code parses the provided port number from the command line arguments and starts the server with the StringServer to handle incoming requests.

Once the server is started, the StringServer instance will handle incoming requests. When you access the URL "localhost:4001/add-message?s=Hello," the handleRequest method of the StringServer class will be called with the URI object representing this URL as its argument.

Within the handleRequest method, the code will check if the request path is "/add-message," and it will proceed to parse the query parameters. In this case, it will split the query parameter by '=' and check if the parameter name is "s" and if the length of the parameters array is 2.

If these conditions are met, the code will append the message "Hello" to the messageStringBuilder, increment the num variable, and return the updated message list.
