install express ,nodemon first

install dotenv for handling environment variables

process.env.PORT defines the port

app.use(express.json()) -this function parses json into..

routes folder for the paths
controller folder for the logic of routes
middleware folder for the middle logic and parsing

while we interact with mongodb we get responses as promises , in order to resolve it we use async and await

express-async-handler for handling exceptions

install mongoose for object model and connection to mongodb

don't forget to import files it will cause error

use config folder to define configs for things

now use the methods to define various logics in controllers

use bcrypt for hashing passwords

use jsonwebtoken for auth,authoriz, and sso services