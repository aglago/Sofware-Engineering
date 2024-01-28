# Learning Objectives
At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

## General
- What a URL is

A URL, or Uniform Resource Locator, is the address that you type into your browser to visit a website. For example, the URL for Google is "google.com". URLs contain the domain name (like "google.com") as well as the path to the specific page you're trying to visit (like "search?q=How+are+you+doing"). A URL tells the browser where to find the content you're looking for.


- What HTTP is

HTTP, or HyperText Transfer Protocol, is the underlying protocol that makes the web work. It's a set of rules that govern how web servers and browsers communicate with each other. When you visit a website, your browser sends an HTTP request to the server, and the server responds with the requested content using HTTP. HTTP is what makes it possible for you to view web pages, download files, and do all the other things you can do on the web. In recent years, HTTP has been replaced by HTTPS (HyperText Transfer Protocol Secure), which adds an extra layer of security.


- How to read a URL

Reading a URL is actually pretty straightforward. The first part of the URL is the protocol (like "http://" or "https://"). After that comes the domain name (like "google.com"). Finally, there's the path (like "search?q=How+are+you+doing"). When you're reading a URL, you can ignore the protocol and focus on the domain name and path. For example, if you're looking for Google's homepage, you'd want to type "google.com" into your browser.


- The scheme for a HTTP URL

In a URL, the "scheme" refers to the protocol (like "http" or "https"). So, when you see a URL like "https://google.com", the scheme is "https". The scheme is important because it tells the browser how to interpret the rest of the URL. In the case of "https", it means that the browser should use the secure version of HTTP. There are lots of other schemes, like "ftp" for File Transfer Protocol or "mailto" for email.

- What a domain name is

A domain name is the unique name that identifies a website. For example, "google.com" is the domain name for Google's website. A domain name is part of a URL and it's used to help people find websites. Domain names are usually registered with a domain name registrar. Anyone can register a domain name, as long as it hasn't been taken by someone else. There are lots of different top-level domains (like ".com", ".org", or ".net"), and you can choose which one you want when you register your domain name. Do you have a domain name for your website?


- What a sub-domain is

A subdomain is a part of a domain name that's used to organize different parts of a website. For example, "mail.google.com" is a subdomain of "google.com". A subdomain can be anything you want, as long as it doesn't conflict with any other subdomains or the main domain name. Subdomains are often used to create different sections of a website, like "blog.google.com" or "calendar.google.com". Subdomains can also be used to create unique URLs for different purposes, like "help.google.com" or "support.google


- How to define a port number in a URL

When defining a port number in a URL, you use the format "port:number". For example, to access a website using port 80, you would use the URL "http://example.com:80". If the website uses a different port, such as port 8080, you would use the URL "http://example.com:8080". Most websites use port 80 for HTTP and port 443 for HTTPS, but you can specify any port number that the server is listening on. Some websites may also use non-standard ports for other services, such as FTP or SMTP.

- What a query string is

A query string is a string of characters that is added to the end of a URL to send additional information to the server. The query string is separated from the rest of the URL by a question mark (?) and is composed of key-value pairs. For example, a URL might look like this: "http://example.com/page.html?q=search-term". The query string in this example includes the key "q" with the value "search-term". The server can then use this information to perform a search for the given term. Query strings can also be used to pass other types of information, such as including parameters for filtering search results, logging in to a website, and tracking analytics. They're a common way to send information to the server without changing the URL itself.
Is there anything else you want to know about query strings?


What an HTTP request is
What an HTTP response is
What HTTP headers are
What the HTTP message body is
What an HTTP request method is
What an HTTP response status code is
What an HTTP Cookie is
How to make a request with cURL
What happens when you type google.com in your browser (Application level)