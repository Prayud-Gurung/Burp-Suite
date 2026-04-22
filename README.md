# Burp Suite

Target website : https://ctf.apilchand.com.np/challenges

## Overview
Intercepting the web traffic and testing for vulnerabilities using burpsuite community edition. Using burp proxy to intercept the request, manipulating the request to check for vulnerabilities and using tools available to simplify this process.

Performing bruteforce to find the password by adding payload in the intruder tab and studying the response generated

## Steps and Screenshots
1. Downloaded Burp Suite Community Edition
2. Started the application
![1](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Screenshots/1.png)
![2](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Screenshots/2.png)
![3](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Screenshots/3.png)

3. Dashboard
Central manager to view and manage all the tasks
![Dashboard](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Screenshots/Dashboard1.png)
4. Target
Opened burp's browser pre-configured for burp suite and started browsing the website. Then I explored the sitemap for the information Burp suite gathered. The cogwheel sign ⚙️ represent the dynamic path for the website and potential starting point for the testing
![3](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Screenshots/SiteMap.png)
5. Proxy
Intercepted the request after visiting the login page and turning the intercept on. On line 23 was the login credentials so I sent the request to repeater for testing with different credentials
![Proxy](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Screenshots/Proxy.png)
I also went through traffics stored in HTTP history tab, it allows to send previous trffic to repeater, intruder and others
![CompareText](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Screenshots/HTTPHistory.png)
6. Repeater
Using the repeater, I sent the request with different set of credentials to the server. I tried commonly used credentials like admin, user, administrator, guest, 123345 ,qwerty for different response
![Repeater](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Screenshots/Repeater.png)
7. Comparer
To find the difference in responses I sent the response to comparer
![Comparer](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Screenshots/Comparer.png)
![CompareText](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Screenshots/ComparerText.png)
8. Logger
The logs burp suite maintains for the activities in the applicaiton, also enables to view them
![Logs](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Screenshots/Logger.png)
9. Organizer
![Organizer](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Screenshots/Organizer.png)
Organizer allows to organize the request and response, for this session I added a login request to the organizer
10. Decoder
![Decoder](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Screenshots/Decoder.png)
Decoder tool is useful to decrypt the encrypted message in the response from the server or reverse. I explored available options like Base64, URL encoding, HTTP encryption

## Working with intruder tab
1. I sent the request to intruder for intruder attack
![Intruder](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Screenshots/Intruder.png)
2. I used sniper attack, on the target website and for the password I used payload with a short list of incorrect password with one correct password. For this session, I created a dummy account for learning purpose.
![Payload](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Screenshots/Payload.png)
3. The results of the intruder atack hit the combination against the website is visible in the table. I can see one of the password returned status code 302
![SniperAttack](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Screenshots/SniperAttack.png)
4. To compare the response, I sent the failed result and success to the comparer to compare them against each other
![Comapre](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Screenshots/Compare.png)
5. Also tried SQLi
![SQLi](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Screenshots/SQLi.png)

Obesrvation and Findings
Website lacks input validation or password strength requirement
Login was a HTTP post request with url encoded data
Rate limit was enabled in the website which burp suite handled it automatically
The server generates nonce value for each form generated as we see in the post request
Could not bypass authenticaiton via SQL injection or 1 = 1 , "or""="

