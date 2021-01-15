# Read 05 - Notes: Heroku Deployment

## [Heroku: Getting Started with Node](https://devcenter.heroku.com/articles/getting-started-with-nodejs#introduction)
+ `heroku open` launches app
+ View logs by using the command `heroku logs --tail` 
  - provides information about your running app
  - Heroku treats logs as streams of time-ordered events aggregated from the output streams of all your app and Heroku components, providing a single channel for all of the events. 
  - `^ + C` a.k.a. `Control + C` stops the log stream.
+ Use a [Procfile](https://devcenter.heroku.com/articles/procfile), a text file in the root directory of your application, to explicitly declare what command should be executed to start your app. Additional reference available at: https://devcenter.heroku.com/articles/getting-started-with-nodejs#define-a-procfile
  - TODO: revisit the Procfile link from above later to determine if we need to add the Procfile to our root directory.
+ Right now, your app is running on a single web dyno. Think of a dyno as a lightweight container that runs the command specified in the `Procfile`.
+ Free dynos also consume from a monthly, account-level quota of free dyno hours - as long as the quota is not exhausted, all free apps can continue to run.
+ Scaling an application on Heroku is equivalent to changing the number of dynos that are running.

To scale down:
```
~ heroku ps:scale web=0
```
To scale up:
```
~ heroku ps:scale web=1
```
To run the app locally (use `^ + C` to exit):
```
~ heroku local web
```
+ By default, Heroku stores 1500 lines of logs from your application. However, it makes the full log stream available as a service - and several add-on providers have written logging services that provide things such as log persistence, search, and email and SMS alerts.

To see add-ons on my account:
```
~ heroku addons
```
To see the Papertrail web console:
```
~ heroku addons:open papertrail
```
+ [Config vars](https://devcenter.heroku.com/articles/getting-started-with-nodejs#define-config-vars)
  - Heroku lets you externalize configuration - storing data such as encryption keys or external resource addresses in config vars.
  - At runtime, config vars are exposed as environment variables to the application. 
  - run it with the command `heroku open times`

+ Connecting to database: use the command `heroku pg:psql` to start the app and `\q` to exit the app
  - learn more about [Heroku PostgreSQL](https://devcenter.heroku.com/articles/heroku-postgresql)

### [Additional Resources](https://devcenter.heroku.com/articles/getting-started-with-nodejs#next-steps):
1. [How Heroku Works](https://devcenter.heroku.com/articles/how-heroku-works) - a technical overview of the concepts you’ll encounter while writing, configuring, deploying and running applications.
2. [Node.js category](https://devcenter.heroku.com/categories/nodejs-support) - learn more about developing and deploying Node.js applications.
3. [Deploying Node.js Apps on Heroku](https://devcenter.heroku.com/articles/deploying-nodejs) - understand how to take an existing Node.js app and deploy it to Heroku.




****
## [Deploying a Simple Blog to Heroku](https://howtonode.org/deploy-blog-to-heroku)
+ Node.js is an open source, cross-platform runtime environment, which allows you to build server-side and networking applications.
+ It's written in JavaScript and can be run within the Node.js runtime on any platform. 
+ Heroku is a cloud platform as a service - it allows you to deploy your web server.
+ Node allows a server to handle a lot of connections and work with a number of requests at the same time. And you don't need much memory for that. It's designed to be responsive and fast. 
+ It's useful when you need to create an application that will be able to respond instantly to a large number of users.

(Note source: https://howtonode.org/deploy-blog-to-heroku)

***
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)


+ 