# node-js-sample (debian package)

A barebones Node.js app using [Express 4](http://expressjs.com/).

This fork of a basic node app from heroku demonstrates of how to package node apps 
and have them run as a service. This approach sould not interfere with npm and the 
standard ways developers like to work on these things. 

It also aims to be minimalistic in nature and only depend on v8 and node for deployment 
into raw, virtuale, or namespaces (containers). It really doesn't matter since its a 
package.

Simply:
```
debuild
```
Now you can deploy the binary wherever you have debian.

```
$ sudo dpkg -i ../node-js-sample*_all.deb

$ curl -I localhost:5000
HTTP/1.1 200 OK
X-Powered-By: Express
Content-Type: text/html; charset=utf-8
Content-Length: 12
ETag: W/"c-1c291ca3"
Date: Sat, 17 Jan 2015 20:12:53 GMT
Connection: keep-alive

$ curl localhost:5000
Hello World!
```

## Running Locally

Make sure you have [Node.js](http://nodejs.org/) and the [Heroku Toolbelt](https://toolbelt.heroku.com/) installed.

```sh
git clone git@github.com:heroku/node-js-sample.git # or clone your own fork
cd node-js-sample
npm install
npm start
```

Your app should now be running on [localhost:5000](http://localhost:5000/).

## Deploying to Heroku

```
heroku create
git push heroku master
heroku open
```

Alternatively, you can deploy your own copy of the app using this experimental
web-based flow:

[![Deploy to Heroku](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

## Documentation

For more information about using Node.js on Heroku, see these Dev Center articles:

- [10 Habits of a Happy Node Hacker](https://blog.heroku.com/archives/2014/3/11/node-habits)
- [Getting Started with Node.js on Heroku](https://devcenter.heroku.com/articles/getting-started-with-nodejs)
- [Heroku Node.js Support](https://devcenter.heroku.com/articles/nodejs-support)
- [Node.js on Heroku](https://devcenter.heroku.com/categories/nodejs)
- [Using WebSockets on Heroku with Node.js](https://devcenter.heroku.com/articles/node-websockets)
