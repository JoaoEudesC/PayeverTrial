Simple REST Application
This is a simple REST application that communicates with the reqres.in API. The application uses the NestJS framework, MongoDB, and RabbitMQ.

Prerequisites
NodeJS 12 or above
TypeScript 3.4 or above
MongoDB 4.4 or above
RabbitMQ 3.7 or above
Installation
Clone this repository
Install dependencies using npm install
Copy the .env.example file to .env and update the variables as necessary
Running the application
To start the application, run npm start

Endpoints
POST /api/users
Creates a new user entry in the database.

Request body:

perl
Copy code
{
"name": "John Doe",
"email": "johndoe@example.com"
}
GET /api/user/{userId}
Retrieves data from https://reqres.in/api/users/{userId} and returns the user in JSON representation.

GET /api/user/{userId}/avatar
Retrieves the user's avatar image by URL. On the first request, it saves the image as a plain file and stores it as a MongoDB entry with the userId and hash. Returns the base64-encoded representation of the image.

On following requests, it returns the previously saved file in base64-encoded representation retrieved from the database.

DELETE /api/user/{userId}/avatar
Removes the user's avatar image file from the FileSystem storage and removes the stored entry from the database.

Testing
To run the tests, use npm test

Linting
This project uses ESLint for code linting. To run the linter, use npm run lint.

Conclusion
This application is a simple example of how to use NestJS, MongoDB, and RabbitMQ to create a REST API. If you have any questions or feedback, please let us know!
