# Burp Suite

Target website : https://ctf.apilchand.com.np/challenges

## Overview
Intercepting the web traffic and testing for vulnerabilities using burpsuite community edition. Using burp proxy to intercept the request, manipulating the request to check for vulnerabilities and using tools available to simplify this process.

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
![Repeater](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Screenshots/3.png)
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