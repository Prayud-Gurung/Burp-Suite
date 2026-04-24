# Altoro
Target website: http://altoro.testfire.net/

## Overview
- To understand the functinosn of tools in burp suite properly.
- Analyse generated token in the sequencer
- Try different kinds of intruder attacks
- Decode encoded data

## Steps and screenshots
1. Started Burp suite, started burp browser and navigated to login page in the website
![login](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/login.png)
2. I entered "admin" as username and "12345" for password, then intercepted the post request in proxy tool as I clicked the link
![proxy](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/proxy.png)
3. I sent the request to the intruder and repeater, then selected the token names JSESSIONID and sent to the sequencer
![repeater](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/repeater.png)
Sequencer is used to analyse the randomness of the token issued by the server.
Token can be anti-CSRF token, password reset tokens, JSON web tokens, etc. In this instance, we are analysing session tokens
![sequencer](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/sequencer.png)
5. I captured 1500 tokens for the analysis
![tokenAnalysis](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/sequencerAnalysis.png)

> Intruder attacks performed
# Sniper Attack
Sniper attack is a straightforward, It adds payload to a single position in the request and commence the attack
![sniperAttack](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/sniper.png)
I received the status code of 302 for all the request, the incorrect credentials had response length of 126
![sniperAttack](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/sniperFail.png)
For the successful attack, The length of response was 397
![sniperAttack](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/sniperSuccess.png)
I sent the response of the attack to Comparer
![sniperAttack](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/sniperComparer.png)

# Battering Ram Attack
Battering ram attack uses a single payload across multiple position in the request
![batteringRam](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/batteringRam.png)
For proper example I added a third position SomeotherPayload in the request, and this is how the request is sent
![batteringRam](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/batteringRamFail.png)
![batteringRam](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/batteringRamSuccess.png)

# Pitchfork Attack
Pitchfork attack uses multiple payloads for each position, and sequencially executes the pairs the payload from each set
![pitchfork](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/pitchforkPositions.png)
I added payload for each positions
Position 1
![pitchfork](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/pitchforkPosition1.png)
Position2
![pitchfork](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/pitchforkPosition2.png)
This is how the payload is paired
![pitchforkAttack](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/pitchforkAttack.png)

# Cluster Bomb Attack
Cluster Bomb attack is set up the same as pitchfork attack, but it is executed differently
![clusterBomb](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/clusterBomb.png)
It pairs all elements payload1 with first index of payload 2, then moves along with second index of payload2 the same way
This generates all combinations possible with the payload
![clusterBomb](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/clusterBombAttack.png)

> Using Decoder
I sent an encoded text from the request to the Decoder and decoded using Base64
![decoder](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/encoded.png)
![decoder](https://github.com/Prayud-Gurung/Burp-Suite/blob/main/Altoro/Screenshots/decoder.png)