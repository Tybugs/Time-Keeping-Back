
## ✨ Requirements

- [Node.js](https://nodejs.org/) >= v16.13
- [SQLite](https://www.sqlite.org/index.html)

<br />

## ✨ How to use the code

> **Step 1** - Clone the project

```bash
$ git clone https://github.com/app-generator/api-server-nodejs.git
$ cd api-server-nodejs
```

<br />

> **Step 2** - Install dependencies via `Yarn`

```bash
$ yarn
```

<br />

> **Step 3** - Run the SQLite migration via TypeORM

```
$ yarn typeorm migration:run
```

<br />

> **Step 4** - Start the API server (development mode)

```bash
$ yarn dev
```

<br />

> **Step 5** - Production Build (files generated in `build` directory)

```bash
$ yarn build
```

<br />

> **Step 6** - Start the API server for production (files served from `build/index.js`)

```bash
$ yarn start
```

The API server will start using the `PORT` specified in `.env` file (default 5000).

<br />

## ✨ Codebase Structure

```bash
< ROOT / src >
     | 
     |-- config/                              
     |    |-- config.ts             # Configuration       
     |    |-- passport.ts           # Define Passport Strategy             
     | 
     |-- migration/
     |    |-- some_migration.ts     # database migrations
     |
     |-- models/                              
     |    |-- activeSession.ts      # Sessions Model (Typeorm)              
     |    |-- user.ts               # User Model (Typeorm) 
     | 
     |-- routes/                              
     |    |-- users.ts              # Define Users API Routes
     | 
     | 
     |-- index.js                   # API Entry Point
     |-- .env                       # Specify the ENV variables
     |                        
     |-- ************************************************************************
```

<br />

## ✨ SQLite Path

The SQLite Path is set in `.env`, as `SQLITE_PATH`

<br />

## ✨ Database migration

> Generate migration:

```bash
$ yarn typeorm migration:generate -n your_migration_name
```

> run migration: 

```bash
$ yarn typeorm migration:run
```

<br />

## ✨ API

For a fast set up, use this POSTMAN file: [api_sample](https://github.com/app-generator/api-server-nodejs-pro/blob/master/media/api.postman_collection.json)

> **Register** - `api/users/register`

```
POST api/users/register
Content-Type: application/json

{
    "username":"test",
    "password":"pass", 
    "email":"test@appseed.us"
}
```

<br />

> **Login** - `api/users/login`

```
POST /api/users/login
Content-Type: application/json

{
    "password":"pass", 
    "email":"test@appseed.us"
}
```

<br />

> **Logout** - `api/users/logout`

```
POST api/users/logout
Content-Type: application/json
authorization: JWT_TOKEN (returned by Login request)

{
    "token":"JWT_TOKEN"
}
```

<br />

## ✨ Run the Tests

```yarn test```

<br />
