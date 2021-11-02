# Writeup for the challenge **_`Obligatory Shark`_** from Killer Queen CTF 2021
----

- ## Challenge Information:

| Name             | Category          | Difficulty | Points | Dev          |
|------------------|-------------------|------------|--------|--------------|
| Obligatory Shark | Digital Forensics | Easy       |        | sampinkerton |


[Click to try the challenge for yourself](https://anonfiles.com/3dZce0S6u4/challenge_pcapng)<br>
file hash: 704DA72FB393A819CA631BE91C1F33273EC55190CA7EA9EFF872DA51AC511053
----


# Solution:
If you know at least a little bit about networks or network forensics you know about pcap files, if you don't pcap files are just a network traffic files or network packets usually opened with wireshark which is a program used to capture, sniff and analyse network traffic etc... 

### In this challenge we were given a traffic capture :
![capture](https://user-images.githubusercontent.com/33517160/139755452-40a3df44-5324-4984-9cfd-2815cae76ca0.png)

from a basic look you won't know what to look for but there is something caught my attention which is the telnet protocol, the telnet protocol is known to be old and insecure its insecure because its a plaintext protocol aka text-based protocol and its used to open a command line on a remote computer these days its replaced with ssh or secure shell, ssh is better because its a cryptographic protocol and was made to be secure.

### SSH:
![ssh](https://user-images.githubusercontent.com/33517160/139755524-6e0d0ff9-bbc8-4973-a1bf-4519bcf7261b.jpg)

Back to the challenge, I followed the TCP stream for the telnet data and its the login data for the user.

```red
thecompany login: uusseerr22
Password: 33a465747cb15e84a26564f57cda0988
```
[crackstation]: https://crackstation.net
the password looks like md5, which is a  message-digest algorithm i know its an md5 because i deal with md5 everyday but a good way to check is checking if the hash is 32 of length, and before i try cracking the hash myself i try [crackstation] which is an online password/hash cracking website.

![crackstation](https://user-images.githubusercontent.com/33517160/139755694-8ec73d8f-900e-4dda-ac4a-50656e797d14.png)


## Flag: **`kqctf{dancingqueen}`**
