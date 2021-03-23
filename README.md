# kanban-board

## Setup

Because the backend API is hosted on heroku [here](https://kanban-cjk-api.herokuapp.com/api/tasks), you only need to clone the frontend to run it locally.

``` bash
$ git clone https://github.com/ckinateder/kanban-ui.git
```

You can start the frontend with

``` bash
$ cd kanban-ui
$ npm install
$ npm start
```

However, if you would like to clone the api as well, you may do so with

``` bash
$ git clone https://github.com/ckinateder/kanban-api.git
```

You can start the backend in the same way, with

``` bash
$ cd kanban-api
$ npm install
$ npm start
```

In order to run the app locally, you may have to modify the environment variables. If you only want to mess with the frontend, you just have to run `npm start` in the `kanban-ui` directory. However, if you want to update the API, you'll need to edit the `.env` variables. For example, when I'm developing locally, this is what my `.env` files look like.

In `kanban-api/`

```
PORT=5000
DB_URL=mongodb://localhost:27017
TEST_API_URL=http://localhost:5000
```

In `kanban-ui/`

```
PORT=5001
REACT_APP_SERVER_URL=http://localhost:5000
```

For another example, since by default the database is hosted on atlas, if I'm not messing with the database, my `DB_URL` looks like `mongodb+srv://<username>:<password>@<cluster-url>/<db-name>?retryWrites=true&w=majority`. 

And when **I'm only developing the front end**, my `kanban-ui/.env` file looks like

```
PORT=5001
REACT_APP_SERVER_URL=https://kanban-cjk-api.herokuapp.com/
```

## Tests

Just run

``` bash
$ npm test
```

to run the mocha tests.
