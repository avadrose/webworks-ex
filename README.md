How Web Works Exercise
Part One: Solidify Terminology
What is HTTP?

HTTP (Hypertext Transfer Protocol) is the set of rules that clients (like browsers) and servers use to send and receive data on the web.

What is a URL?

A URL (Uniform Resource Locator) is the address for an internet resource (where to find something on the web).

What is DNS?

DNS (Domain Name System) translates human-readable domain names (like example.com) into IP addresses computers use to locate servers.

What is a query string?

A query string is the part of a URL after the ? that contains key-value pairs, like ?name=Ava&color=blue.

What are two HTTP verbs and how are they different?

GET: requests data from the server (often used for search forms). Data is visible in the URL query string.

POST: sends data to the server (often used when creating/updating data). Data is sent in the request body.

What is an HTTP request?

An HTTP request is a message sent from a client to a server asking for a resource (or asking the server to do something), following HTTP rules.

What is an HTTP response?

An HTTP response is the server’s reply to the client’s request, including a status code, headers, and usually a response body.

What is an HTTP header? Give examples of request/response headers you have seen.

Headers provide extra metadata about the request or response.

Examples:

Request headers: Host, User-Agent, Accept, Cookie, Cache-Control

Response headers: Content-Type, Last-Modified, Set-Cookie, Cache-Control

What happens when you type http://somesite.com/some/page.html into a browser?

The browser uses DNS to resolve the domain name to an IP address.

The browser makes an HTTP request to that server for /some/page.html.

The server returns an HTTP response (success or error).

If successful, the browser parses the HTML into the DOM.

The browser finds other needed resources (CSS, JS, images, etc.) and makes additional HTTP requests for each.

The browser downloads those resources and renders the page.




Part Two: Practice Tools
1) Use curl to make a GET request for “pirate” jokes

PowerShell note: curl is an alias for Invoke-WebRequest, so I used curl.exe to run real curl.

Command:

curl.exe -H "Accept: application/json" "https://icanhazdadjoke.com/search?term=pirate" | py -m json.tool


Result (status 200, total_jokes = 5):

What does a pirate pay for his corn? A buccaneer!

Why couldn't the kid see the pirate movie? Because it was rated arrr!

What did the pirate say on his 80th birthday? Aye Matey!

Why do pirates not know the alphabet? They always get stuck at "C".

Why are pirates called pirates? Because they arrr!

2) Find the IP address for icanhazdadjoke.com

Command:

nslookup icanhazdadjoke.com


Result:

2606:4700:3033::6815:420f

2606:4700:3032::ac43:c6ad

172.67.198.173

104.21.66.15

3) Serve a simple web page using python http.server

Command:

python -m http.server


Result:

Visited http://localhost:8000

Page loaded successfully and displayed custom HTML content


Part Three: Explore DevTools

With GET, form fields appear in the URL as a query string (example: ?name=Ava&color=blue).

In Chrome DevTools, I viewed headers using:
DevTools → Network → click the request → Headers → Request Headers / Response Headers

With POST, the fields do not appear in the query string; they are sent in the request body.

In DevTools, I viewed POST form data using:
Network → click request → Payload → Form Data

Part Four: Explore the URL API

new URL(window.location.href) lets you read parts of the current page URL.

url.searchParams.get("key") reads query string values.

url.searchParams.set("key", "value") updates query params.

history.pushState({}, "", url) updates the address bar without reloading the page.