TO USE THIS APP
Download the repository as zip file to your local computer or clone the repository
Open the downloaded file in any IDE of your choice, VSCODE preferrable
install the dependencies: using "npm i" in you command prompt or terminal
create a new file named .env in root folder of the project.
Connect mongodb locally using:
In .env: MONGODB_URI=mongodb+srv://<username>:<password>@cluster0.2edjquq.mongodb.net/<db_name>
In app.js: mongoose.connect("mongodb://localhost:27017/<db_name>", {
   useNewUrlParser: true,
   useUnifiedTopology: true
}).then(() => {
    console.log('Connected to the database')
}).catch(() => {
    console.log('There was an error connecting to your database')
});

ALTERNATIVELY

Use Mongo DB atlas (most use in production)

The App url for room
http://localhost:8080/api/v1/room (You must be authenticated create a room)
The App url for room Type
http://localhost:8080/api/v1/roomType
The App url for registration
http://localhost:8080/api/v1/user/register
The App url for login
http://localhost:8080/api/v1/user/login

Room type creation
{
    "codeName": "A12"
}

output

{
    "success": true,
    "message": "created room type",
    "data": {
        "codeName": "A12",
        "_id": "63f33eb856731d3ba8ce37cc",
        "__v": 0
    }
}

Room creation

{
    "name": "Executive3",
    "price": 900,
    "size": "small",
    "roomType": "63f00b3b98597f4239518790"
}

output

{
    "success": true,
    "message": "Room created successfully",
    "data": {
        "name": "Executive3",
        "price": 900,
        "size": "small",
        "roomType": "63f00b3b98597f4239518790",
        "_id": "63f33f0b56731d3ba8ce37d2",
        "__v": 0
    }
}

Registration

{
    "username": "Barth1",
    "email": "barth1@gmail.com",
    "password": "12345"
}

output

{
    "success": true,
    "message": "User created",
    "data": {
        "username": "Barth1",
        "email": "barth1@gmail.com",
        "password": "$2a$08$hIHwTDcxBQEJPy4GSbch4uYYX0roL8VGa6TmyUXY4wV2UGdMPFF4y",
        "role": "guest",
        "_id": "63f339c251739c320fa22c32",
        "__v": 0
    }
}

Login

{
    "username": "Barth",
    "password": "12345"
}

output

{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6IkJhcnRoIiwiaWF0IjoxNjc2ODg2MTQyfQ.QaJxmsPSbmjNVrp5qlkflob7mbadAN2aII5o6npNA9A"
}

The token generated after login can be use to access some restricted routes

In postman:

Click Authorization > type: Bearer Token > copy the above token excluding the double quotion mark and past it
in Token text space provided in postman. You can now access every restricted routes.
