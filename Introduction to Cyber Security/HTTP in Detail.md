## What is HTTP?
- HTTP stands for HyperText Transfer Protocol.
- This is the protocol that is used when you visit a website.
- It was developed by Tim Berners-Lee and his team in around 1990.
- It is used to transfer webpage data i.e HTML, images, and videos.

## What is HTTPS?
- Secure version of HTTP - HTTP(Secure).
- In HTTPS protocol, the data being trasferred is encrypted, and therefore, secure.

## HTTP Requests and Responses
- When we access a website, your browser will need to make requests to a web server for assets such as HTML, Images, and download the responses. Before that, you need to tell the browser specifically how and where to access these resources, this is where `URLs` will help.

### URL
If you’ve used the internet, you’ve used a URL before. A URL is predominantly an instruction on how to access a resource on the internet. The below image shows what a URL looks like with all of its features (it does not use all features in every request).
![the-structure-of-a-url](https://user-images.githubusercontent.com/60597290/222886272-9f707a00-5401-4530-829d-597fbc4dfee6.png)
- The image above shows the basic structure of a URL (Uniform Resource Locator)

## Making a Request:
- It's possible to make a request to a web server with just one line "GET / HTTP/1.1"
- But for a much richer web experience, you’ll need to send other data as well. This other data is sent in what is called headers, where headers contain extra information to give to the web server you’re communicating with.

## Response Example
```HTML
HTTP/1.1 200 OK
Server: nginx/1.15.8
Date: Fri, 09 Apr 2021 13:34:03 GMT
Content-Type: text/html
Content-Length: 98

<html>
<head>
    <title>TryHackMe</title>
</head>
<body>
    Welcome To TryHackMe.com
</body>
</html>
```

To breakdown each line of the response:
- Line 1: HTTP 1.1 is the version of the HTTP protocol the server is using and then followed by the HTTP Status Code in this case "200 Ok" which tells us the request has completed successfully.
- Line 2: This tells us the web server software and version number.
- Line 3: The current date, time and timezone of the web server.
- Line 4: The Content-Type header tells the client what sort of information is going to be sent, such as HTML, images, videos, pdf, XML.
- Line 5: Content-Length tells the client how long the response is, this way we can confirm no data is missing.
- Line 6: HTTP response contains a blank line to confirm the end of the HTTP response.
- Lines 7-14: The information that has been requested, in this instance the homepage.

## HTTP Methods
HTTP methods are a way for the client to show their intended action when making an HTTP request. There are a lot of HTTP methods but we'll cover the most common ones, although mostly you'll deal with the GET and POST method.
- `GET Request:` Getting information from a web server.
- `POST Request:` Used for submitting data to create new records.
- `PUT Request:` This is used for submitting data to a web server to update information.
- `DELETE Request:` This is used for deleting information/records from a web server.

## HTTP Status Codes


- `100-199 - Information Response`
    - These are sent to tell the client the first part of their request has been accepted and they should continue sending the rest of their request. These     codes are no longer very common.
- `200-299 - Success`
    - This range of status codes is used to tell the client their request was successful.
- `300-399 - Redirection`
    - These are used to redirect the client's request to another resource. This can be either to a different webpage or a different website altogether.
- `400-499 - Client Errors`
    - Used to inform the client that there was an error with their request.
- `500-599 - Server Errors`
    - This is reserved for errors happening on the server-side and usually indicate quite a major problem with the server handling the request.

## Headers
Headers are additional bits of data you can send to the web server when making requests.
Although no headers are strictly required when making a HTTP request, you’ll find it difficult to view a website properly.
