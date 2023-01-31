# Lab Report 2

# Part 1
The following is my code for StringServer.java:
![Image](wk4lrstrsvrorig.png)
I used the Server.java file from the Week 2 Lab as part of setting up the server. I also used the NumberServer.java 
file from the Week 2 Lab for examples for URI methods and writing the StringServer main method.

The following screenshot shows the website with the given query string in the URL being “FirstLine”. When I went to 
the website (entered the URL), the main method of StringServer was called. The field was String[] args, which had a 
value which was the URL, which was [http://localhost:4000/add-message?s=FirstLine]http://localhost:4000/add-message?s=FirstLine. 
Since `args.length == 0` is false, the body of the if statement is skipped. The field int port is found by using the `parseInt()` 
method, and the value is 4000. A new instance of `Server` is instantiated and the `start()` method is called, with the value of 
4000 for the `port` field, and a new `Handler()` instance being created for the `URLHandler` field. Then, the method `handleRequest()` 
is called, with the URL being the value for the `url` field. Since `url.getPath().equals(“/”)` is not true, the body of the if 
statement is skipped. Since `url.getPath().contains(“/add-message”)` is true, the if statement body is executed. 
`url.getQuery().split(“=”)` is used to assign the URL (split on the “=” character) to a String array called `parameters`. In the
`parameters` array, the first element is the “s” from the URL, and the second element is the given query string, “FirstLine” in this 
instance. Then, `String.format(parameters[1] + “\n”)` is returned, which prints the given query string (“FirstLine”) and a new line 
on the webpage.
![Image](wk4lrpt11.png)
The following screenshot shows the website with the given query string in the URL being “SecondLine” (I am aware this 
output is incorrect, a test case and correction is made in Part 2). Most of the code execution is the same except for 
the last few lines. When I went to the website (entered the URL), the main method of StringServer was called, and the 
same lines executed. Then handleRequest is called, with most of the lines executing with the same results. Then 
url.getQuery().split(“=”) is used to assign the URL, split on the “=” character, to a String array called parameters. In 
the parameters array, the first element is the “s” from the URL, and the second element is the given query string, “SecondLine” 
in this instance. Then, String.format(parameters[1] + “\n”) is returned, which prints the given query string (“SecondLine”) 
and a new line on the webpage. The output is incorrect because the second input for the given query string is not concatenated 
to the first one. It is supposed to be “FirstLine” + “\n” + “SecondLine”, but instead, only “SecondLine” is printed when the 
second URL is entered.
![Image](wk4lrpt12.png)
