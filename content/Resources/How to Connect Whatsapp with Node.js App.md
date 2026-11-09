---
publish: true
title: How to Connect Whatsapp with Node.js App
description: In the following steps we will use this library to create a sample Node.js application that connects simple whatsapp from scratch. Here you can find basic information and additional documentation of…
created: 2025-04-20
modified: 2026-10-15T16:16:14.555Z
published: 2026-10-15T16:16:14.555Z
tags: fleeting
socialImage: https://miro.medium.com/v2/resize:fit:1200/1*aT37SHIIas29ln5zneEGtA.png
source: https://vkri.medium.com/how-to-connect-whatsapp-with-node-js-app-f80d46a02112
author:
  - Muhhamad Firrki
cover: https://miro.medium.com/v2/resize:fit:1200/1*aT37SHIIas29ln5zneEGtA.png
reference:
type: literature
---

The project’s website can be found at <https://wwebjs.dev/>

In the following steps we will use this library to create a sample Node.js application that connects simple whatsapp from scratch. Here you can find basic information and additional documentation of whatsapp-web.dev.

## Step 1: Create a new node project

Create a new project by running the following command:

```c
$ mkdir node-whatsapp-web
$ cd node-whatsapp-web
$ npm init -y
```

## Step 2: Install whatsapp-web.js

Install whatsapp-web.js, you can see docs. Enter the following commands:

```c
$ npm install whatsapp-web.js
```

## Step 3: Connect to whatsapp-web.js

Now we’re ready to write a Node.js program which is making use whatsapp-web.js. We start by creating a new empty file:

```c
$ touch app.js
```

Insert the following lines of code:

```c
const { Client } = require('whatsapp-web.js');
const client = new Client();

client.on('qr', (qr) => {
    console.log('QR RECEIVED', qr);
});

client.on('ready', () => {
    console.log('Client is ready!');
});

client.initialize();
```

Let’s run the script by typing in:

```c
$ node app.js
```

Now you should see something similar to

## Step 4: QR code generate

Since whatsapp-web.js works by running WhatsApp Web in the background and automating its interaction, you’ll need to authorize the client by scanning a QR code from WhatsApp on your phone. Unfortunately we’re receiving the QR code not as an image which we can use for authentification but instead as a text string. To change this behavior we need to install another package:

```c
$ npm i qrcode-terminal
```

And now we’ll modify our code to use this new module:

```c
const qrcode = require('qrcode-terminal');

const { Client } = require('whatsapp-web.js');
const client = new Client();

client.on('qr', qr => {
    qrcode.generate(qr, {small: true});
});

client.on('ready', () => {
    console.log('Client is ready!');
});

client.initialize();
```

There we go! You should now see something like this after running the file:

After scanning this QR code, the client should be authorized and you should see a Client is ready! message being printed out.

## Step 5: Listening for messages

As the WhatsApp client is ready now, we’re able to perform some WhatsApp tasks like sending and receiving messages.

```c
client.on('message', message => {
  console.log(message.body);
  
  if(message.body === '!hello') {
    message.reply('Hello!');
  }
});
```

Here we’re registering on event handler function for the message event type. This event is raised everytime a new message is received. The message is then printed out to the command line.

## Step 6: Replying to messages

From the last example you could also learn how to send messages as a reply to a received message. The logic which is implemented here is checking if a message text “!hello” has been received. If this is true, we’re making use of the _message.reply_ method to send back an answer to the message sender.

We could also send back a normal message (not as a reply) by simple using the client.sendMessage method instead.

```c
client.sendMessage(message.from, 'Thanks for sending a test message!');
```

In this case the method is expecting two parameters: first we need to specify to whom the message should be sent. As the message should be send to the sender of the original message we can simple use _message.form_ here. The second parameter contains the message text as a string.

Here’s for example code: <https://github.com/fikri-batawi/node-whatsapp-web>

Please Clap if you liked!
