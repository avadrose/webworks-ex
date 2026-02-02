# How Web Works Exercise

## Part One: Solidify Terminology

### What is HTTP?
Hyper text transfer protocol - how clients recieve and send data via a server

### What is a URL?
Uniform resource locator - an address for internet resources

### What is DNS?
Domain name system - a system mthat takes readble urls and converts them into unique IP addresses

### What is a query string?
Query strings allow you to pass key-value pairs into the url 

### What are two HTTP verbs and how are they different?
GET - gets data from the server (ex. search forms/input)
POST - sends data to the server (pages that change data on server)

### What is an HTTP request?
Request from a client to a server which follows the HTTP protocol

### What is an HTTP response?
Response from a server to a client which follows the HTTP protocol
 
### What is an HTTP header? Give examples of request/response headers you have seen.
Headers provide additional information about the request ot response
Request headers - host, user-agent, accept, cookies, cache control
Response headers - content-type, last-modified, set cookie, cache control

### What happens when you type “http://somesite.com/some/page.html” into a browser?
Browser resolves the name ino an IP address using DNS
Browser makes request to IP address for information
Server sends response is successful/unsuccessful
Browser makes a DOM from the HTML and finds any other resources needed (images, css, JS, ect..)
Browser makes seperate HTTP request for those resources and recieves response from the server for each

---

## Part Two: Practice Tools

1. Use curl, make GET request for “pirate” jokes
Command:
```bash
curl -H "Accept: application/json" "https://icanhazdadjoke.com/search?term=pirate"

PS C:\Users\HP\OneDrive\Desktop\Evee\SpringBoard\webworks>
 curl.exe -H "Accept: application/json" "https://icanhazdadjoke.com/search?term=pirate" | py -m json.tool
>>
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:100   589  100   589    0     0   4973      0 --:--:-- --:--:-- --:--:--  5034
{
    "current_page": 1,
    "limit": 20,
    "next_page": 1,
    "previous_page": 1,
    "results": [
        {
            "id": "QuscibaMClb",
            "joke": "What does a pirate pay for his corn? A buccaneer!"
        },
        {
            "id": "2gii3LeN7Ed",
            "joke": "Why couldn't the kid see the pirate movie? Because it was rated arrr!"
        },
        {
            "id": "SvzIBAQS0Dd",
            "joke": "What did the pirate say on his 80th birthday? Aye Matey!"
        },
        {
            "id": "exXSCtkOKe",
            "joke": "Why do pirates not know the alphabet? They always get stuck at \"C\"."
        },
        {
            "id": "SnOf2gqjiqc",
            "joke": "Why are pirates called pirates? Because they arrr!"
        }
    ],
    "search_term": "pirate",
    "status": 200,
    "total_jokes": 5,
    "total_pages": 1
}

2. Use dig to find IP address
Command:
nslookup icanhazdadjoke.com
>>
Server:  syn-2603-6011-9a00-68ce-0000-0000-0000-0001.res6.spectrum.com
Address:  2603:6011:9a00:68ce::1

Non-authoritative answer:
Name:    icanhazdadjoke.com
Addresses:  2606:4700:3033::6815:420f
          2606:4700:3032::ac43:c6ad
          172.67.198.173
          104.21.66.15

3. Simple web page 
Command:
python -m http.server

Result:
- Visited http://localhost:8000
- Page loaded successfully and displayed custom HTML content
