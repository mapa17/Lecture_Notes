# Real Time Sentiment Analysis

by XXX

## Goal
Build a Application that can in real time analyze audio recordings extracting
the transcript, mentioned **terms**.

git.io/vpYET

## Start
Nexmo Web Service is the first point in analyzing the call. It receives the phone call / audio stream using web sockets

### Dependencies
We need a web API stuff. For that we use the python library **hug** and **Tornado**

> Note: There seems to be an pip alternative called **pipenv**

We start creating a Class

> router.py

    Class CallRouter(object):
    ...
    proxy(self):
        return[
            {'action': 'SomeAcctions'},
            ... ,
            {'action': 'Connect'}
        ]

> Note: A tool to tunnel web traffic from a public to a private machine
> using **ngrok**
> ngrog has a debug website, that shows all activity tunneled by ngrok

Nexmon is offering you to rent phone numbers world wide, and calls your web services associated with the number you rented.

> Note: Check IBM Watson web service text to speech https://speech-to-text-demo.ng.bluemix.net and https://speech-to-text-demo.ng.bluemix.net

> Coupon code: HB86MOT - 10 Euros


https://github.com/bonzanini/nlp-tutorial