## Udacity - Udagram Infrastructure description
### Infrastructure diagram

![Infrastructure Diagram](./Application%20Architecture%20Diagram.png)

#### AWS S3
S3 used to store static files such as images, Javascript, css and deployment packages. It also provides web static hosting for our application.

#### AWS Elastic Beanstalk
Elastic Beanstalk(EB) used for backend api web hosting. It handles authentication, data processing, and interactions with the database.

To run applicatoin locally,remove `dialectOptions: { ssl: { require: true, rejectUnauthorized: false } }` from `udagram-api/src/sequelize.ts`, and add or update .env file according to the configuration specified in `udagram-api/src/config/config.ts`.

There may be issues with installing typescript@3.5.3 on the Circle CI container. To address it, I added the command to install Typescript package before executing `npm install` for the backend API. 

#### AWS RDS Postgres
The Postgres database is used to store user information, authentication data and Feed data. After deploying the database, we need to config inbound security rules to allow access access from the backend API and other clients.