# SkyHub---A-Flight-Management-System
SkyHub: Node.js, Express.js, Sequelize, MySQL, ES6+, Git, Dotenv, JWT. Ensures seamless API creation, efficient DB interactions, modern codebase, version control, and robust security. Following RESTful principles and MVC architecture, SkyHub delivers an efficient Flight Management System for the aviation industry.
Welcome to Flights Service Project Setup:

1. Clone the project to your local machine.
2. Execute `npm install` in the root directory of the downloaded project.
3. Create a `.env` file in the root directory and add the following environment variable:
   ```
   PORT=3000
   ```
4. Inside the `src/config` folder, create a new file `config.json` and add the following JSON snippet:
   ```json
   {
     "development": {
       "username": "<YOUR_DB_LOGIN_NAME>",
       "password": "<YOUR_DB_PASSWORD>",
       "database": "Flights_Search_DB_DEV",
       "host": "127.0.0.1",
       "dialect": "mysql"
     }
   }
   ```

Once you've added your database config as listed above, go to the `src` folder from your terminal and execute:
```bash
npx sequelize db:create
```
and then execute:
```bash
npx sequelize db:migrate
```

## DB Design
- Airplane Table
- Flight
- Airport
- City 

- A flight belongs to an airplane, but one airplane can be used in multiple flights.
- A city has many airports, but one airport belongs to a city.
- One airport can have many flights, but a flight belongs to one airport.

## Tables

### City
- id
- name
- created_at
- updated_at

### Airport
- id
- name
- address
- city_id
- created_at
- updated_at

**Relationship:** City has many airports, and an airport belongs to a city (one-to-many).

To generate the Airport model with the specified attributes, run the following command:
```bash
npx sequelize model:generate --name Airport --attributes name:String,address:String,cityId:integer
```
