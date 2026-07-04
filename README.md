# Outer Commerce API

[![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white)](https://expressjs.com/)
[![Sequelize](https://img.shields.io/badge/Sequelize-52B0E7?style=flat-square&logo=sequelize&logoColor=white)](https://sequelize.org/)
[![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![dotenv](https://img.shields.io/badge/dotenv-ECD53F?style=flat-square&logo=dotenv&logoColor=black)](https://www.npmjs.com/package/dotenv)
[![npm](https://img.shields.io/badge/npm-CB3837?style=flat-square&logo=npm&logoColor=white)](https://www.npmjs.com/)

Outer Commerce is a backend API for managing core e-commerce catalog data: **products, categories, and tags**. It is built with Express and Sequelize, backed by MySQL, and designed for clean JSON-based CRUD workflows that can power a storefront or admin dashboard.

## Why this project

This service gives teams a practical starting point for e-commerce backend development:

- Organize products into categories
- Attach multiple tags to products via a join table
- Perform full CRUD operations through REST-style endpoints
- Seed realistic starter data for local development and testing

## Features

- Express API under `/api`
- Sequelize models and associations:
  - `Category` has many `Product`
  - `Product` belongs to `Category`
  - `Product` belongs to many `Tag` through `ProductTag`
  - `Tag` belongs to many `Product` through `ProductTag`
- JSON request/response handling with URL-encoded support
- Environment-based database configuration via `.env`
- Optional `JAWSDB_URL` support in the database connection layer

## Tech Stack

- **Runtime:** Node.js
- **Framework:** Express
- **ORM:** Sequelize
- **Database:** MySQL (`mysql2` driver)
- **Config:** dotenv
- **Dev tooling:** nodemon
- **Package manager:** npm

## Getting Started

### Prerequisites

- Node.js (LTS recommended)
- npm
- MySQL server

### Installation

1. Clone the repository
2. Install dependencies:

```bash
npm install
```

3. Create the database schema:

```bash
mysql -u <your_mysql_user> -p < db/schema.sql
```

4. Create a `.env` file in the project root:

```env
DB_NAME=ecommerce_db
DB_USER=your_mysql_user
DB_PW=your_mysql_password
# Optional (used instead of local DB fields when set)
# JAWSDB_URL=******host:port/database
```

5. Seed starter data:

```bash
npm run seed
```

6. Start the API:

```bash
npm start
```

For development with auto-reload:

```bash
npm run watch
```

## Available Scripts

- `npm start` - starts the server on `PORT` (default `3001`)
- `npm run watch` - starts the server with nodemon
- `npm run seed` - syncs and seeds database tables
- `npm test` - placeholder script currently not configured for automated tests

## API Overview

Base path: `/api`

- `/api/categories`
- `/api/products`
- `/api/tags`

Each resource supports standard CRUD routes:

- `GET /`
- `GET /:id`
- `POST /`
- `PUT /:id`
- `DELETE /:id`

The root router returns `Wrong Route!` for unknown endpoints.

## Project Structure

```text
config/      # Sequelize connection setup
models/      # Sequelize models + associations
routes/      # Express routers and API endpoints
seeds/       # Seed datasets and seed runner
db/          # SQL schema setup
server.js    # Application entry point
```

## Demo

- Walkthrough video: https://www.youtube.com/watch?v=BZ4SIYFjW-I&t=458s

## Contributing

Contributions are welcome. Open an issue or submit a pull request with a focused change and clear description.

## Contact

Karltunmoreno@gmail.com
