# Week 3 Lab Report

## Part 1
**Simplest Search Engine**
```
class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    int num = 0;

    public String handleRequest(URI url) {
        ArrayList<String> num = new ArrayList<String>();
        if (url.getPath().equals("/")) {
            return String.format("item: %d", inputs.toString());
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("d")) {
                    num.add(parameters[1]);
                    return String.format("item %d added", parameters[1]);
                }
            }
            return "404 Not Found!";
        }
    }
}

class SearchEngine {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }
    
        int port = Integer.parseInt(args[0]);
    
        Server.start(port, new Handler2());
    }
}
```
<img width="564" alt="Screen Shot 2022-10-14 at 10 08 05 PM" src="https://user-images.githubusercontent.com/114641719/195970159-7c3fef51-d68d-4ed3-9000-766d90993548.png">
<img width="331" alt="Screen Shot 2022-10-14 at 10 09 54 PM" src="https://user-images.githubusercontent.com/114641719/195970163-ad84e547-71b7-46f1-8406-6e8db86bcfc7.png">

1. I called add cat and add dog
2. Called the methods in Handlerequest() to add to the query
3. if those values were to change they would add new values to the item list.

## Part 2

**Array Methods Bug**

<img width="340" alt="Screen Shot 2022-10-13 at 9 05 24 AM" src="https://user-images.githubusercontent.com/114641719/195964339-2a38b96d-c6f6-4d8a-94f7-51fa786b0d75.png">
1. The following shows the input for the test cases

2. There were bugs in reverse in place and reversed when using something with multiple inputs.

testReverseLargerArrays(ArrayTests)
arrays first differed at element [2]; expected:<1> but was:<3>
ArrayTests.testReverseLargerArrays(ArrayTests.java:23)
        ... 32 trimmed
Caused by: java.lang.AssertionError: expected:<1> but was:<3>


3. The bugs were the following; 
In the reverse in place function there was a bug because when reversing the function through the same array the code would mess up the inputs before it was done reversing itself. To do this we would need a temp array that could save a database of the original array and use that to change the original way without the original array corrupting itself.
In the reverse function the bug was it would change the original array instead of the new array. It would pull from the new array to change the original array. To top it off it returned the original array instead of the new one. 

**List Method Bug**

<img width="425" alt="Screen Shot 2022-10-13 at 9 46 40 AM" src="https://user-images.githubusercontent.com/114641719/195964494-baaca8f8-e9e9-4226-8704-19e5e0b38d77.png">

1. The following shows the input in place for the test cases
 
2. The only bug was an implementation error in the list method
3. The bug was in the code was in the wrong order


