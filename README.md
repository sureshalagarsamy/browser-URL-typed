# What happens when you type a URL in browser

Apart from being a very common interview question, this is one of the very basic thing will 'tick' in our mind every time we type any URL in a browser


### what happens in the background...

```Step 1``` URL is typed in the browser.

```Step 2``` DNS lookup to find the ip address of the server

when we want to connect to google.com, we actually want to reach out to a server where google web services are hosted. One such server is having an ip address of 10.236.xxx.xx. 

Now, if you type "http://10.236.xxx.xx" in your browser, this will take you to google home page itself. Which means, "http://google.com" and "http://10.236.xxx.xx" are nothing but same stuff. <b>But, it is not so.</b> Google has multiple servers in multiple locations to cater to the huge volume of requests they receive per second.Thus we should let Google decide which server is best suited to our needs.Using "google.com" does the job for us. When we type "google.com", <b><i>DNS(Domain Name System)</i></b> services comes into play and resolves the URL to a proper ip address. 

```Step 3``` Browser initiates a TCP connection with the server.

```Step 4``` Browser sends a HTTP request to the server.

Browser sends a GET request to the server according to the specification of <b>HTTP</b> (Hyper Text Transfer Protocol) protocol. 

```html
GET http://google.com/ HTTP/1.1
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
User-Agent: Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:29.0) Gecko/20100101 Firefox/29.0
Accept-Encoding: gzip, deflate
Connection: Keep-Alive
Host: google.com
Cookie: datr=1265876274-[...]; locale=en_US; lsd=WW[...]; c_user=2101[...]
```

Here, browser passes some meta information in the form of headers to the server along with the URL - "http://google.com". 

```Step 5``` Server handles the incoming request

HTTP request made from browsers are handled by a special software running on server - commonly known as web servers e.g. Apache, IIS etc. 

```Step 6``` Browser receives the HTTP response

HTTP response starts with the returned status code from the server. Following is a very brief summary of what a status code denotes:

```
1xx indicates an informational message
2xx indicates success message
3xx redirects the client to another URL
4xx indicates client error
5xx indicates server error
```

```Step 7``` Browsers displays the html content
