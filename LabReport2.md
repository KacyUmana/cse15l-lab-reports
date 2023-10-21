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
