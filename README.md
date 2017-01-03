# Loggr v1.0 (Release)

### Introduction
Loggr is a convenient way to log, track and visualize workplace records. It offers a clean interface encapsulating all the grunt work of organization and data storage behind the scene. It takes minimal time to set up Loggr.

>With Loggr, you can do the following essential things:
  - Make customized 'Lines' or spreadsheets with complete control over column names and types
  - Add Entries with real-time filtering
  - Manage multiple lines at the same time
  - Add/Edit Employees who have access to the lines in the company

>You can also:
  - Update Lines and columns if the need arises
  - Mark each entry as in-progress by default unless updated clocked-out
  - Export entire spreadsheets as .csv

### Tech
From the technical point of view, Loggr leverages the following main open source projects/libraries:

* [ReactJS] - The popular libary by Facebook to build user interfaces
* [Webpack] - the go-to build-system/module-bundler for React projects
* [Material-UI] - UI Components for React that implement Google's Material Design
* [MongoDB] - The household name for NOSQL Databases 
* [node.js] - for the server
* [Express] - fast node.js network app framework
* [Mongoose] - elegant mongodb object modeling for node.js

## Getting Started
Installing Loggr is a three step process.

  - Install/Host the **database** and run an instance
  - Start the **server** with the correct address of the database instance
  - Open the **client** in a web browser after editing the config file with the server address
 
To get started, first download and extract the [latest pre-built release](https://github.com/an5rag/loggr-release/archive/master.zip). 


### Database
While it is highly encouraged to host the database using a cloud storage solution (like [MLab](https://mlab.com), [compose](https://www.compose.com/mongodb)), download and install [MongoDB] using the relevant guide [here](https://docs.mongodb.com/manual/installation/).

Make sure the database is up and running before proceeding to the next step.


### Server

After extracting the downloaded release, you'll see a folder named **server**.
Inside it is a .bat file called ```start.bat```.

Open it using your favorite text editor. You'll see the following one line in it:

```sh
server.exe mongodb://.../loggr-sample 4000
```

Here's how the command is broken up:
```
server.exe <mongo-database-address> <port number>
```

Edit the database-address and port number appropriately. Save it.

Double-clicking on ```start.bat``` will now start the server and host it on the given port number (4000 by default)
Be sure to grant all access privileges to the server if a prompt shows up.

>Next, let's initialize the default admin user for the app.

Open any web-browser and go to 
```
http://server-address:port-number/api/user/initialize
```
For example, if the server was located at localhost at port 4000, you would go to
```
http://localhost:4000/api/user/initialize
```

If everything goes well, you should something like this in your browser:
```js
{"success":true,"message":"Default Admin Added!","user":{"__v":0,"username":"admin2","firstName":"Administrator","lastName":"","password":"admin","_id":"586c27f196c60014a82558a8","companyId":"000","userType":"ADMIN"}}
```


### Client

After extracting the downloaded release, you'll see a folder named **client**.
Inside it is a .js file called ```config.js```.

Open it using your favorite text editor. You'll see the following contents:

```js
// replace the api_address below with the custom server address
// the current api_address is for sample purpose only
const API_ADDRESS = "http://localhost:4000/api";
window._API_ADRESS = API_ADDRESS;
```

Edit the api-address (server-address) appropriately. Make sure you append ```/api``` to the end of the address. Save it.

Double-clicking on ```index.html``` will now run the app in the default browser.

That's it!

License
----

MIT

[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)


   [git-repo-url]: <https://github.com/joemccann/dillinger.git>
   [node.js]: <http://nodejs.org>
   [express]: <http://expressjs.com>
   [ReactJS]: <hhttps://facebook.github.io/react/>
   [MongoDB]: <https://www.mongodb.com/>
   [Mongoose]: <http://mongoosejs.com/>
   [Webpack]: <https://webpack.github.io/>
   [Material-UI]: <http://www.material-ui.com/#/>

