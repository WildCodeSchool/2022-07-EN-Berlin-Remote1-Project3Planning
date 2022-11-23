# Quick start

---
## Backend

* clone the repository: [https://github.com/WildCodeSchool/2022-07-EN-Berlin-Remote1-Project3Backend](https://github.com/WildCodeSchool/2022-07-EN-Berlin-Remote1-Project3Backend)
* go to the project folder `cd 2022-07-EN-Berlin-Remote1-Project3Backend`
* run `npm install` command to install dependencies.
* open project with VSCode `code .`
* create `.env` file and fill enviromental variables following the [`.env.sample`](https://github.com/WildCodeSchool/2022-07-EN-Berlin-Remote1-Project3Backend/blob/main/.env.sample).

>
> **NOTE** in `.env` file the variable FRONTEND_URL schould link to your local **frontend**. Example `http://localhost:3000`
>

* run `npm start` script to build and start the server.
* run `npx prisma studio` command to explore data in the Database
>
> **NOTE** if you are not able to run prisma studio run the command `npx prisma migrate dev`
>

* for creating new database change in `.env` file variable `DATABASE_URL` and apply connection string for new database. Then run command `npx prisma migrate dev`


For more details go to [README](https://github.com/WildCodeSchool/2022-07-EN-Berlin-Remote1-Project3Backend/blob/main/README.md)


---
## Frontend

* clone the repository: [https://github.com/WildCodeSchool/2022-07-EN-Berlin-Remote1-Project3Frontend](https://github.com/WildCodeSchool/2022-07-EN-Berlin-Remote1-Project3Frontend)
* go to the project folder `cd 2022-07-EN-Berlin-Remote1-Project3Frontend`
* run `npm install` command to install dependencies.
* open project with VSCode `code .`
* create `.env` file and fill enviromental variables following the [`.env.sample`](https://github.com/WildCodeSchool/2022-07-EN-Berlin-Remote1-Project3Frontend/blob/master/.env.sample).

>
> **NOTE** in `.env` file the variable REACT_APP_BASE_API_URL schould link to your local **backend**. Example `http://localhost:3000`
>

* run `npm start` script to build and start app.
