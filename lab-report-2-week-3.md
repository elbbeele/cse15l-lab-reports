# Week 3 Lab Report 2
## Part 1: Simple Search Engine

### *Code* ###
```
import java.io.IOException;
import java.net.URI;
import java.util.*;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    
    ArrayList<String> l = new ArrayList<>();
    
    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return createString(l);
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    l.add(parameters[1]);
                    return "String " + parameters[1] + " was added!";
                }
            }
            else if(url.getPath().contains("/search")){
                String[] parameters = url.getQuery().split("=");
                ArrayList<String> con = new ArrayList<>();
                
                if (parameters[0].equals("s")) {
                    for(String s: l){
                        if(s.contains(parameters[1])){
                            con.add(s);
                        }
                    }
                    return createString(con);
                }
            }
            return "404 Not Found!";
        }
    }
    public String createString(ArrayList<String> str){
        StringBuilder sb = new StringBuilder();
        if(str.size()>0){
            for(String s: str){
                sb.append(s);
                sb.append(" ");
            }
        }
        else{
            sb.append("Your list is empty! Please add some strings!");
        }
        return sb.toString();
    }
}

class SearchEngine {
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

### *Adding Pineapple* ###

![Image](https://elbbeele.github.io/cse15l-lab-reports/addPine.png)

This photo shows the process of adding “pineapple” into the list. It uses the methods called “handleRequest,” “createString,” and “main”. This method first takes in the path of the website and checks that it contains “/add”. Then it splits the query using “=”, and adds the string to the list after “=.”

### *Adding Apple* ###

![Image](https://elbbeele.github.io/cse15l-lab-reports/addApple.png)

This photo shows the process of adding “apple” into the list. It uses the methods called “handleRequest,” “createString,” and “main”. This method first takes in the path of the website and checks that it contains “/add”. Then it splits the query using “=”, and adds the string to the list after “=.”

### *Searching Query* ###

![Image](https://elbbeele.github.io/cse15l-lab-reports/query.png)

This photo shows the items in the list that include the phrase that was inputted into the query.  It uses methods called “handleRequest,” “createString,” and “main”. This method first takes in the path and checks that it contains “/search.” If so, it splits the query and searches through the already existing list for elements that contain the phrase. It creates a separate new list and adds the elements from the original list that fits the conditions. Then it combines the elements of the list into a string to print on the website. 


### *Full List Result* ###
![Image](https://elbbeele.github.io/cse15l-lab-reports/fullList.png)

## Part 2: Bugs from ArrayExamples.java and ListExamples.java

### *ArrayExamples.java ReversedInPlace* ###
*Failure inducing input:* As the original array was being reversed, because the whole code was only working with one array, the switched elements were reswitched and doubled  instead of just reversed. 

*Symptom:* The error message that popped up was an Assertion Error (Please check image below)

![Image](https://elbbeele.github.io/cse15l-lab-reports/arrayAssertionError.png)

*Bug:* The code fix that was needed was to create a new array where all the numbers were reversed correctly, and then assign the values of the new array into the original array.

![Image](https://elbbeele.github.io/cse15l-lab-reports/ArrayReverseInPlaceFix.png)

The connection between the symptom and the bug stems from trying to do everything with one single. Because it was continuously getting updated, the updated values were the only ones left in the array to “reverse.”


### *ListExamples.java Filter* ###

*Failure inducing input:* As the list was being filtered, the order of the list was messed up in a way that did not end up with the correct same order as they appeared in the inputted list. 

*Symptom:* The error message that popped up in the terminal was an Assertion error. (Please check image below)

![Image](https://elbbeele.github.io/cse15l-lab-reports/assertionError.png)

*Bug:* The code fix that was needed was to create a new array where all the numbers were reversed correctly, and then assign the values of the new array into the original array.

![Image](https://elbbeele.github.io/cse15l-lab-reports/ListFilterFix.png)

The connection between the symptom and the bug stems from always adding the element that passed the checkString interface method at the front of the array instead of at the end. 
