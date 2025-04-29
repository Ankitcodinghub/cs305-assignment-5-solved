# cs305-assignment-5-solved
**TO GET THIS SOLUTION VISIT:** [CS305 Assignment 5 Solved](https://www.ankitcodinghub.com/product/cs305-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;116227&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;0&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;0&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;0\/5 - (0 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS305 Assignment 5  Solved&quot;,&quot;width&quot;:&quot;0&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 0px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            <span class="kksr-muted">Rate this product</span>
    </div>
    </div>
A local DNS server is a server which is setup inside of a company, homes network, or residential ISP for address/name translations. The goal of this assignment is to implement a local DNS server in Python.

IMPORTANT NOTES:

Your python code should be named as “LocalDNSServer.py” using UTF-8 as file encoding.

The local DNS server should listen on port 5533 (do NOT change it!!!) and IP address 127.0.0.1 (do NOT change it!!!) .

When querying, the RD in DNS message should be set to 0* (or set the flag to be 0x0000), which means that your DNS query is iterative.

Comments in code is MUST.

Python 3.9.7

Implementation detail

1. The local DNS server should listen on port 5533 and IP 127.0.0.1. The main functionalities of the local DNS server include:

(1) Listen and accept DNS queries from client, support default query type: A type.

(2) Maintain a Cache: ① Cache should be human-readable, following the RR format: (name, value, type, ttl).

② A new query should be recorded if not in the cache already.

(3) Maintain a list of records about the domain names and IPv4 addresses of Root DNS servers.

(4) Search related DNS responses in cache according to the received query.

(5) Invoke DNS queries to other DNS servers if needed and cache the new response.

(6) Reply to client with the response.

2. Take a DNS query to “www.example.com” as an example what your need to implement is about:

(1) The client sends a DNS query about “www.example.com” to the local DNS server.

(2) The local DNS server searches its mapping in the cache.

if the mapping is found in Cache, the local DNS server replies to the client as a DNS response object.

If a mapping is not found, then a translation is resolved iteratively as follows:

(a) the local DNS server sends the query to root level DNS Server, and gets a DNS response message about the list of .com level DNS servers.

(b) the local DNS server then sends a query to .com level DNS server, and gets the DNS response message about the list of example.com level name servers.

(c) the local DNS server then sends the query to example.com. level DNS Server, and gets the DNS response message about the mapping of the original DNS query.

(d) the local DNS server caches the mapping in cache.

(e) the local DNS server replies to the client with the mapping.

3. Grading criteria

Basic iterative query to get a name/address translation (80)

Caching (20)

Multi-threading local DNS server and concurrency control (bonus, up to 20)

Implement a multi-thread version local DNS server that can serve multiple queries concurrently.

Provide at least one implementations to tackle the problem when several clients access the server in the same time, which means that you should ensure the thread safety in cache, since it could be overwritten by multi threads at the same time.

5. NOTE again: in the DNS message’s flag, RD should be set to 0 which means it does not query recursively!

Test detail

Input format

There are two places that you need to input.

The first one is when you run the LocalDNSServer.py , you need to input the ip address of your network interface card.

The second one is when you open dig, you should input a dig DNS request, e.g., dig @”your ipv4 address” “queried domain name” a -p “your port” Here please specify the port as 5533

Output format

The output format is standard DNS message format, you can use dnslib library to construct and resolve it (we have this example in the template).

When the DNS mapping is read from cache your should print “read from cache” on the console ( “” is not need)

Test process

① Run LocalDNSServer.py.

② Enter IP address (you can use ipconfig to search your IP address) and port (this port is arbitrary but youshould avoid conflict with other process) in console. If success, it will print the information about the root DNS server.

This means that you can use this IP address and port to complete and resolve a basic DNS query.

③ Open another command line and input the command:

dig @127.0.0.1 www.baidu.com a -p 5533

Then the console should print your local DNS server’s response.

and if it is read from cache, you should print “read from cache” in the python console where your server runs

If you resolve a domain name and get a result in cname type, you should keep that result and include it in the response

The above output example shows when you search www.baidu.com and find a cname type record of www.a.shifen.com, you need to print www.a.shifen.com and then use www.a.shifen.com to query the final response, which is shown as the above screenshot.

④ We will test about more than 4 testcases continuously.

What to submit

You should provide your implementation in the file LocalDNSServer.py and another file such as the cache if needed.

Please provide detailed comments in your code to explain different parts of your code. You need to at least illustrate in your implementation about basic part, cache part, and concurrency part (if any). A PDF file that includes some necessary screenshots to show your code works and some brief explanations.

TIPS

The below WireShark screenshots show the process about resolving a DNS query iteratively.

① query 8.8.8.8 and get records of root DNS server in NS type

query:

answer:

② query 8.8.8.8 and get IP address of root DNS server

query:

answer:

③ query root DNS server and get IP address of top-level DNS server

query:

answer:

④ query top-level server and try to find authoritative domain name server

query:

answer:

⑤ by iteratively querying, finally get a mapping of A type

query:

answer:

query:

answer:

Another test examples

when read from cache
