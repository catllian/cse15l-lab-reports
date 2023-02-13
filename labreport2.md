# Lab Report 2

# Part 1
The following is my code for StringServer.java:
![Image](wk4lrpt1(1).png)
I used the Server.java file from the Week 2 Lab as part of setting up the server. I also used the NumberServer.java 
file from the Week 2 Lab for examples for URI methods and writing the StringServer main method.

The following screenshot shows the website with the given query string in the URL being “FirstLine”.
![Image](wk4lrpt1(2).png)
When I went to the website (entered the URL), the main method of StringServer was called. The field was String[] args, which had a 
value which was the URL, which was [http://localhost:4000/add-message?s=FirstLine]http://localhost:4000/add-message?s=FirstLine.
```
public static void main (String[] args) throws IOException {...}
```
Since `args.length == 0` is false, the body of the if statement is skipped. 
```
if(args.length == 0){...}
```
The field `int port` is found by using the `parseInt()` method, and the value is 4000. A new instance of `Server` is instantiated and
the `start()` method is called, with the value of 4000 for the `port` field, and a new `Handler()` instance being created for the `URLHandler` field.
```
int port = Integer.parseInt(args[0]);

Server.start(port, new Handler());
```
Then, the method `handleRequest()` is called, with the URL being the value for the `url` field.
```
public String handleRequest(URI url) {...}
```
Since `url.getPath().equals(“/”)` is not true, the body of the if statement is skipped.
```
if (url.getPath().equals("/")) {...}
```
Since `url.getPath().contains(“/add-message”)` is true, the if statement body is executed. `url.getQuery().split(“=”)` is used to 
assign the URL (split on the “=” character) to a String array called `parameters`. In the `parameters` array, the first element is the “s” 
from the URL, and the second element is the given query string, “FirstLine” in this instance. Then, the local String variable `strTotal` is created, which is
a concatenation of 'strTotal', the given query string, and a new line character. `strTotal` is returned, which prints the given query string (“FirstLine”) 
and a new line on the webpage.
```
else if (url.getPath().contains("/add-message")) {
    String[] parameters = url.getQuery().split("=");
    strTotal = strTotal + parameters[1] + "\n";
    return String.format(strTotal);
}
```
The following screenshot shows the website with the given query string in the URL being “SecondLine”. 
![Image](wk4lrpt1(3).png)
Most of the code execution is the same as the first input except for the last few lines. When I went to the website (entered the URL), 
the main method of StringServer was called, and the same lines executed. Then `handleRequest()` is called, with most of the lines executing 
with the same results. Then `url.getQuery().split(“=”)` is used to assign the URL (split on the “=” character) to a String array called `parameters`. 
In the `parameters` array, the first element is the “s” from the URL, and the second element is the given query string, “SecondLine” in this instance. The 
local String variable `strTotal` is modified to a String that is a concatenation of 'strTotal', the given query string, and new line character. `strTotal` 
is returned, which prints the "FirstLine" on the first line and "SecondLine" on the second line.

# Part 2
For this part, I chose to investigate the bugs of the `averageWithoutLowest()` method in the ArrayExamples.java file.

* Failure-inducing test 1: This test uses an array with three values: 1.0, 1.0, and 2.0. It checks if the `averageWithoutLowest()` method can correctly 
calculate the average of the double values in an array when there are duplicates of the lowest value. In this case, the average without lowest value should 
be 2.0.
```
@Test
  public void testAverageWithoutLowest1() {
    double[] input4 = {1.0, 1.0, 2.0};
    assertEquals(2.0 / 1, ArrayExamples.averageWithoutLowest(input4), 0.0);
  }
```
* No-failure test: This test uses an array with two values: 1.0, 2.0. It checks if the `averageWithoutLowest()` method can correctly 
calculate the average of unique double values of an array. In this case, the average without lowest value should be 2.0.
```
@Test
  public void testAverageWithoutLowest2() {
    double[] input5 = {1.0, 2.0};
    assertEquals(2.0 / 1, ArrayExamples.averageWithoutLowest(input5), 0.0);
  }
```
* Output of running JUnit tests:
![Image](wk4lrpt2(1).png)
* Code before fixes:
```
public String handleRequest(URI url) {
    if (url.getPath().equals("/")) {
        return "";
    }
    else if (url.getPath().contains("/add-message")) {
        String[] parameters = url.getQuery().split("=");
        return String.format(parameters[1] + "\n");
    }
```
* Code after fixes:
```
String strTotal = "";

public String handleRequest(URI url) {
    if (url.getPath().equals("/")) {
        return "";
    }
    else if (url.getPath().contains("/add-message")) {
        String[] parameters = url.getQuery().split("=");
        strTotal = strTotal + parameters[1] + "\n";
        return String.format(strTotal);
    }
```
The main change I made was creating a new String variable called `strTotal` that additional query strings could be concatenated 
to. Due to making this change, I also had to change the body of the else-if statement. I added a line to modify `strTotal` and 
edited the line to return it.

# Part 3
One thing I learned from the past few weeks is how the student’s definition of a working program differs from the professional definition. 
The student definition only requires that the program exhibits correct I/O most of the time. Technically, this can be sufficient enough to 
accomplish the assigned task.


