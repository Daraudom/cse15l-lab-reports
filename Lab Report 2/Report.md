# Lab Report 2
## Report Contents
[Part 1: StringServer.java](#StringServer)

[Part 2: Debugging](#Debugging)

[Part 3: Reflection](#reflection)

## StringServer 

StringServer handles requests by supporting the path `/add-message` and taking a string query. The expected output should display each added string in a new line.
The following is the code used to launch the StringServer! We use an arraylist to store all of the input strings from the `add-message` request. To show the input strings
line by line, we use the `join` string method with `\n` as the delimiter.

```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler{
    // Initialize a new array list to store the list of strings
    ArrayList<String> listofStrings = new ArrayList<>();

    public String handleRequest(URI url) {
        String urlPath = url.getPath();
        String urlQuery = url.getQuery();
        // Home Page
        if (urlPath.equals("/")) {
            return ("Welcome to Dom's String Server.\nBegin by adding a list of strings!");

        } else {
            System.out.println("Path: " + urlPath);// /add?s=
            // Adding Method
            if (urlPath.contains("/add-message") && urlQuery.contains("=")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s" )) {
                    listofStrings.add(parameters[1]);
                    return String.format(String.join("\n", listofStrings));
                } else {
                    return ("Invalid Query! Please type it as /add-message?s=<A String>!");
                }
            // Reseting the List
            } else if (urlPath.contains("/reset")){
                ArrayList<String> newListofStrings = new ArrayList<>();
                listofStrings = newListofStrings;
                return "Database Reset. Waiting for new inputs...";
            }
            return "404 Not Found!";
        }
    }
}

public class StringServer {
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
**First Screenshot Using `add-message`**

<img src="images/add1.png" height = "400" width = "800" />

1. The method `handleRequest` is called when we hit enter after typing out the URL.  Inside `handleRequest`, 
we use two the built-in methods from the class URl: `getPath` and `getQuery` to manipulate the passed URL argument.
2. When launching the server for the first time, `handleRequest` is called
which passes, "" as the URL argument in the method's parameter. The first if statement takes `/` as the default path, leading to displayed message of the home page! In the screnshot above, the argument passed was the URL.
Its path and query is retrieved and is stored in the variables as followed: `urlPath` and `urlQuery`. 
`urlPath` stores `/add-message` while `urlQuery` stores `s=This is the first screenshot!`. 
3. Since `urlPath` contains `/add-message`, it enters the else's scope into the next if statement. Here `urlQuery` gets checked if it contains `=` which it does,
so the query string gets split with `=` as the delimiter. This manipulate the query string to be legible for our next move.
This generates a string array which is stored in the temporary `String [] parameters` variable which should only contains 2 elements: `{s, This is the first screenshot!}`.
It then goes through another block of conditional statement where it checks for the valid query, `?s=<String>`. If it does, it stores the 2nd element to the arraylist
and prints it out.

**Second Screenshot Using `/add-message`**

<img src="images/add2.png" height = "400" width = "800" />

1. The method `handleRequest` is called when we hit enter after typing out the URL.  Inside `handleRequest`, 
we use two the built-in methods from the class URl: `getPath` and `getQuery` to manipulate the passed URL argument.
2. When launching the server for the first time, `handleRequest` is called
which passes, "" as the URL argument in the method's parameter. The first if statement takes `/` as the default path, leading to displayed message of the home page! In the screnshot above, the argument passed was the URL.
Its path and query is retrieved and is stored in the variables as followed: `urlPath` and `urlQuery`. 
`urlPath` stores `/add-message` while `urlQuery` stores `s=This is the second screenshot!`. 
3. Since `urlPath` contains `/add-message`, it enters the else's scope into the next if statement. Here `urlQuery` gets checked if it contains `=` which it does,
so the query string gets split with `=` as the delimiter. This manipulate the query string to be legible for our next move.
This generates a string array which is stored in the temporary `String [] parameters` variable which should only contains 2 elements: `{s, This is the second screenshot!}`.
It then goes through another block of conditional statement where it checks for the valid query, `?s=<String>`. If it does, it stores the 2nd element to the arraylist
and prints it out. Notice that the way it is being displayed is made possible using the `join` string method since we use `\n` as the delimiter.

## Debugging

Bug: 


## Reflection
