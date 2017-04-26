# Nodemailer

![Nodemailer](https://raw.githubusercontent.com/nodemailer/nodemailer/master/assets/nm_logo_200x136.png)

Send e-mails from Node.js – easy as cake! 🍰✉️

<a href="https://gitter.im/nodemailer/nodemailer?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge"><img src="https://badges.gitter.im/Join Chat.svg" alt="Gitter chat" height="18"></a> <a href="http://travis-ci.org/nodemailer/nodemailer"><img src="https://secure.travis-ci.org/nodemailer/nodemailer.svg" alt="Build Status" height="18"></a> <a href="http://badge.fury.io/js/nodemailer"><img src="https://badge.fury.io/js/nodemailer.svg" alt="NPM version" height="18"></a> <a href="https://www.npmjs.com/package/nodemailer"><img src="https://img.shields.io/npm/dt/nodemailer.svg" alt="NPM downloads" height="18"></a>

[![NPM](https://nodei.co/npm/nodemailer.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/nodemailer/)

See [nodemailer.com](https://nodemailer.com/) for documentation and terms.

-------

Nodemailer v4.0.0 and up is licensed under the [MIT license](./LICENSE)

  >> npm install nodemailer --save


```
'use strict';
const nodemailer = require('nodemailer');

// create reusable transporter object using the default SMTP transport
let transporter = nodemailer.createTransport({
    service: 'gmail',
    auth: {
        user: 'gmail.user@gmail.com',
        pass: 'yourpass'
    }
});

// setup email data with unicode symbols
let mailOptions = {
    from: '"Fred Foo 👻" <foo@blurdybloop.com>', // sender address
    to: 'bar@blurdybloop.com, baz@blurdybloop.com', // list of receivers
    subject: 'Hello ✔', // Subject line
    text: 'Hello world ?', // plain text body
    html: '<b>Hello world ?</b>' // html body
};

// send mail with defined transport object
transporter.sendMail(mailOptions, (error, info) => {
    if (error) {
        return console.log(error);
    }
    console.log('Message %s sent: %s', info.messageId, info.response);
});

```
