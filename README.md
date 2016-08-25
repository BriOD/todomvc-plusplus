# TodoMVC++ : Taking TodoMVC To Production

TodoMVC++ is the companion application for Zero to Production with Node.js.
To learn more about how this application works, check out the video course on 
[Frontend Masters](https://www.frontendmasters.com).

This application is based on [TodoMVC](http://todomvc.com/), and specifically
on a [Vue.js implementation](http://todomvc.com/examples/vue/) by Evan You.

## Running Locally

### Installing Node.js and npm

This application has been tested on Node.js 6 and npm 3 - these packages should
be available for download [here](https://nodejs.org/en/) - choose the "Current"
version for download.

### Installing Node.js modules

Once you have Node and npm installed and this repository downloaded, you'll need
to install the application's dependencies. Do this with:

    npm install

For development (and local verification of production commands), you'll also 
want to install the following modules globally:

    npm install -g pm2 grunt-cli sequelize-cli

### Setting up the database

To run this application locally, you'll require a Postgres database. On a Mac,
the easiest path to installing Postgres is [Homebrew](http://brew.sh/). Once
installed, grab Postgres with:

    brew update
    brew install postgres

If Postgres is installed using the method above, you should now have a few 
Postgres administrative commands on your system path. Begin by firing up another
Terminal tab and starting the database:

    postgres -D /usr/local/var/postgres

Next, create the development and test databases:

    createdb todos
    createdb todos-test

And finally, apply the database migrations:

    npm run-script migrate
    
### Running the application

To run the application in development mode:

    grunt

To run the application simulating production settings:

    NODE_ENV=production
    grunt collect_static
    npm start

## License

MIT
    