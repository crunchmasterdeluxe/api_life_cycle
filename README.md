# API Life Cycle
An explanation of how an API and interacting with an API works

## What is An API
Application Programming Interfaces (APIs) are the way that computers communicate with each other. Web applications, browsers, and servers use APIs to interact with each other. The API cycle consists of three main parts: the request, the receipt, and the response (*figure 1*).

![image](https://github.com/crunchmasterdeluxe/api_life_cycle/assets/83776204/e169f819-58fb-43f8-8b2c-aa42dda3e3f0)

*Figure 1. The API request and response cycle*

## Request, Receipt, and Response
1.	**Request**: A client (the user-side) triggers a “request”. The request consists of three parts: 1) a body of data that is being passed from the client to a server; 2) a command verb that tells the server what to do with the data, whether it be creating data on the server, reading data from the server, updating data on the server, or deleting data on the server; 3) a header, which includes any authentication necessary to perform this action verb. Authentication is sometimes necessary in case the data is sensitive or protected, and can be thought of similarly to login credentials. 
2.	**Receipt**: When the server receives a request, it typically checks it, much like grading a paper. It is programmed to ask questions like, “Is the data received in the proper format?” “Does this user have the proper permission set to execute the intended command (create, read, update, or delete)?” “Does this data need to be cleaned in any way (i.e. does the state or country need to be abbreviated, phone number need to be formatted, email need to verified, text need to be spell-checked, etc.)?” If any consequential API calls need to be made here, the server will do so. An example is when a request comes in to assign a task to a certain user; the server might perform another API call to itself to get (read) more user data. Once the request is checked, a response is sent back to the client.
3.	**Response**: After checking the API request, the server will either accept or reject the request. This acceptance or rejection has two parts: the response code and the response content. The response code is also known as an HTTP response, and is coded as numbers from the 100s to 500s (*figure 2*). 100-199 are informational responses; 200-299 are successful responses, meaning the request was accepted; 300-399 are redirect responses; 400-499 are error responses, meaning the request contains a mistake and is rejected; 500-599 are server responses, meaning the server made a mistake in the receipt stage1. The content is any data the server returns along with the code. If the request is rejected, the content might be about why it was rejected. On the other hand, if the data is accepted, the response content might include any data that that the client is requesting to see. After returning the response, the request finishes processing and the cycle is complete.



![image](https://github.com/crunchmasterdeluxe/api_life_cycle/assets/83776204/d6e76cee-d86b-4d9e-a05d-dfc02dda8deb)

*Figure 2. HTTP response codes and their meanings (courtesy of www.globalcool.org)*

## Example
A good example of an un-authenticated API request is the act of typing a URL in a browser. This request’s data is the URL typed, and its command verb is “Read”, meaning the user simply wants to get data back from the server. The server in this case is a Doman Name Server (DNS), which stores URLs and their corresponding IP addresses, or computers. The DNS then goes through its receipt stage by looking up the URL given in the request to make sure that it exists, and if it does, returning the response. If the URL exists as given, the server gives a 200 response (success) and reads out the contents of the response (the web page expected). If the URL does not exist, the server responds with a 401 error (page not found).

## Conclusion
The API cycle is very simple: a client makes a request to a server, the server processes the request, then then returns a response to the client.



### Sources
https://developer.mozilla.org/en-US/docs/Web/HTTP/Status
