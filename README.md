
# Chat Application

This is a chat application built with Node.js, Express, and SQLite. It includes user registration, authentication, chat room creation, and friend request functionality.

## Features

- User registration and authentication using JWT.
- Prime members can create chat rooms.
- Invite participants to chat rooms.
- Non-prime members can join a chat room for free once.
- Send and receive friend requests.

//user registration

http://localhost:3000/api/register
request type : POST

insert in to body
{
    "userId": "unique_user_id",
    "deviceId": "device_id",
    "name": "User Name",
    "phone": "1234567890",
    "availCoins": 100,
    "password": "password"
}


#user login

http://localhost:3000/api/login
request type : POST 

insert in to body
{
    "phone": "1234567890",
    "password": "password"
}

it give a JWT_Token copy the token



#chat room creation
http://localhost:3000/api/chatrooms
request type : POST

go to the Headers tab and add a new header:
Authorization with the value Bearer YOUR_JWT_TOKEN 
(replace YOUR_JWT_TOKEN with the token you received from the login response)

{
    "roomId": "unique_room_id",
    "createdBy": 1,
    "maxCapacity": 6
}
response indicating that the chat room is created successfully


#join chatroom
http://localhost:3000/api/joinroom
request type : POST

Go to the Headers tab and add a new header: Authorization with the value Bearer YOUR_JWT_TOKEN

{
    "roomId": "unique_room_id"
}

 response indicating that you have successfully joined the room.

 
#Test Profile Viewing 
http://localhost:3000/api/profile/

request type : GET.

URL: http://localhost:3000/api/profile/1 (replace 1 with the actual user ID)

Headers tab and add a new header: Authorization with the value Bearer YOUR_JWT_TOKEN.

 response receive the user's profile details.

 
 #Sending Friend Requests 
 http://localhost:3000/api/friend-request

request type : POST

URL: http://localhost:3000/api/friend-requests

Headers tab and add a new header: Authorization with the value Bearer YOUR_JWT_TOKEN


Enter JSON data
{
    "receiverId": 2
}

response indicating that the friend request has been sent successfully.
