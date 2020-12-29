# Tutorial Source (My Blog)
[Dev.to - Getting Started with Express-Generator (Express/Node.js)](https://dev.to/matthewpalmer9/getting-started-with-express-generator-express-node-js-4483)

# Introduction
Hi there! :wave: Welcome to my tutorial for setting up a new Express application. This isn't a tutorial for how to *use* it, but I'll cover getting yourself set up including ES6+ revisions. (I'll be writing future tutorials moving forward on how to use Express)

# Let's get started

### Step 1 - Installing the Generator
Assuming you already have Node.js installed, you will want to open your IDE of choice (I personally recommend VsCode) and type into your terminal: `npm i express-generator -g`

This will install the express generator on your machine.

### Step 2 - Generating an Express App
Next, you'll want generate your first Express app by typing into your terminal: 
`express --view=ejs your-app-name`

At this point, you'll want to open your project in your IDE. Alternatively, you can `cd` into your project. Whichever you prefer.

Once in, type into your terminal `npm i` or `npm install` to generate your `package-lock.json` and `node_modules`.

### Step 3 - Fixing Declarations in App.js (Optional)
Lines 1 through 10 will be filled with declarations that are declared with `var`. Change all of them to `const` for the sake of ES6+ syntax. It doesn't matter in the beginning, but `var` is known to have some scope issues. Especially in much larger applications. This is optional... but highly suggested.

### Step 4 - Generating `devDependencies`
There are some necessary dependencies you'll want to install. Let's walk through each one:

Type into your terminal: `npm i mongoose passport`
**Explanation:** Here we are installing two (2) dependencies: mongoose and passport. Both are used together as our MongoDB database using `passport` for simplified user authentication.

Type into your terminal: `npm i -D locus`
**Explanation:** The `-D` stands for "Development Dependencies". This will stop it from being pushed onto Heroku when we deploy in the future.

Type into your terminal: `npm i -D dotenv`
**Explanation:** Again, The `-D` stands for "Development Dependencies". `dotenv` will allow us the ability to store secret keys for APIs and any general sensitive information. 

Type into your terminal: `npm i -g nodemon`
**Explanation:** `nodemon` is a dependency that will restart our server automatically when we change any of our files. If you're familiar with React, it's similar to a Virtual DOM, except the information we change doesn't automatically show the moment we change it. It requires us to refresh the page to see these changes. The purpose is to automate restarting the server instead of having to do it ourselves every single time we change something. 

*From here on out, normally we would start our server with `npm start`. Instead, we will be able to type `nodemon` into the terminal which will automatically call on `npm start`.*

**Once done, run `npm i` one more time to make sure `node_modules` is fully updated.**

### Step 5 - Creating Controllers, Models, & Middleware Folders
Part of a MVC (Model, View, Controller) framework requires necessary files that handle the underlying logic. If you're unfamiliar with how an MVC works, [here is some helpful information to bring you up to speed](https://www.tutorialspoint.com/struts_2/basic_mvc_architecture.htm#:~:text=MVC%20is%20popular%20as%20it,data%20needed%20by%20the%20View.&text=The%20MVC%20abstraction%20can%20be%20graphically%20represented%20as%20follows.). To accomplish this, type into your terminal:
`mkdir controllers models middleware`

### Step 6 - Creating `.gitignore` and `.env`
`.gitignore` will ignore any files specified in this folder. To generate this, type into your terminal `touch .gitignore`. Inside of this file, you should include this information:

```
.env
/node_modules
```

You'll notice `.env` is in there. Let's create this file also. In your terminal, type: `touch .env` to create this file. *When it comes time to use this file, we will go into depth on how it works and what the purpose is. Otherwise, you can give a quick google search get a general idea of what `.env` is.

### Step 7 - Fire It Up
You made it! Start your application by typing `nodemon` into your terminal. You can navigate to `http://localhost:3000/` in your browser to verify everything worked.


# Conclusion
Express / MongoDB are a great alternative to building a database for your applications. Personally, I come from a background of using Ruby on Rails as a backend API. As I learn, I will be sharing lessons in future blogs like this one! Once you're set up, you can follow along and grow with me. :) Hope to see you again soon!