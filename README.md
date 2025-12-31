# Ayrene API Documentation

This API allows users to register with an email address and password, and log in securely using mail credentials and also to sent and recieve and delivery purpose and upload posts and Designed for integration into web and mobile applications.

---

## 🌐 Base URL

https://api.ayrene.com

---

## 📬 Endpoints Overview

## Authentication API Documentation


 ### 1. `POST /api/auth/register` — Register User

Description: Register user by using Email, Password, profileId & username. In this registration profileId is optional. It will generate from other platform.  



Request Body
```json
{
    "email": "kusumayekula0191@gmail.com",
    "password": "Kusuma@123",
    "username": "Kusuma Yekula",
    "profileId": "123"
}

Success response

{
    "message": "User registered successfully",
    "user": {
        "id": "69548a3603343d3c3554da86",
        "username": "Kusuma Yekula",
        "email": "kusumayekula0191@gmail.com",
        "profileId": 123,
        "avatar": "",
        "gender": "prefer_not_to_say",
        "onlineStatus": "offline"
    },
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2OTMyYmM1MDNkNzZmYWFhZWU3YjQxM2UiLCJpYXQiOjE3NjQ5MzI2ODgsImV4cCI6MTc2NDkzMzU4OH0.LDo4HsZXCc5kkGTCEzshDwpIpXP1iKH1onzVWUlMpaY",
    "refreshToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2OTMyYmM1MDNkNzZmYWFhZWU3YjQxM2UiLCJpYXQiOjE3NjQ5MzI2ODgsImV4cCI6MTc2NTUzNzQ4OH0.iiU78i81U_E6dUE5G5vabgvavOafJp4KftABsYhT4ZI"
}
```
### 2. `POST /https://api.ayrene.com/api/auth/login`— Log In

Description: Login user by using Email, Password & username.

Request Body
```json

{
     "email": "kusuma7dev@gmail.com",
    "password": "Kusuma@123"
}

Success Response

{
    {
    "success": true,
    "message": "Login successful",
    "user": {
        "id": "69548a3603343d3c3554da86",
        "username": "Kusuma Yekula",
        "email": "kusumayekula0191@gmail.com",
        "profileId": 123,
        "avatar": "",
        "gender": "prefer_not_to_say",
        "onlineStatus": "online"
    },
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2OTU0OGEzNjAzMzQzZDNjMzU1NGRhODYiLCJpYXQiOjE3NjcxNDgzOTQsImV4cCI6MTc2NzE0OTI5NH0.-Q3EA9G6cuzkXd7jHteRkueLH9359wBmP3nDHlnPimE",
    "refreshToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2OTU0OGEzNjAzMzQzZDNjMzU1NGRhODYiLCJpYXQiOjE3NjcxNDgzOTQsImV4cCI6MTc2Nzc1MzE5NH0.yKHQapT3lLfSOmOsuO3KEQ9tYSCTWmQYKdD9A3e_Gy0"
}

```
### 3. `POST /https://api.ayrene.com/api/auth/refresh` — Refresh Token

Description: Giving refresh token we can get access and request token as well. We can get accessToken from login end point. By copying from login end point at the header in the authorization section we need to select Bearer Token after that we need to paste access token. Let's coming to body section pick raw body select JSON file paste refresh token as shown in below. After sending request from post man will get success response. 

#### 🔸 Headers

#### Go to authorization -> Select Bearer Token -> Give Access Token

#### We can get Access token from Login API  


Request Body
```json

{
     "refreshToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2OTMyYmM1MDNkNzZmYWFhZWU3YjQxM2UiLCJpYXQiOjE3NjQ5MzI4NTUsImV4cCI6MTc2NTUzNzY1NX0.Lgv1de1PtGPSOrr4sOEaw8PtdZbHCBhO4D46L9n_5vM"
}

Successful Response 
{
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2OTMyYmM1MDNkNzZmYWFhZWU3YjQxM2UiLCJpYXQiOjE3NjQ5MzQ1MTgsImV4cCI6MTc2NDkzNTQxOH0.jG2nwrFoQlIu3FfV0V1Wei-ALtftb3iGhfm1I2LPeLk",
    "refreshToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2OTMyYmM1MDNkNzZmYWFhZWU3YjQxM2UiLCJpYXQiOjE3NjQ5MzQ1MTgsImV4cCI6MTc2NTUzOTMxOH0.ntTZUqOzTzKRMefAEkU9zpcYRb8HU4BHZq7vzblu3FM"
}

```

### 4. `GET /https://api.ayrene.com/api/auth/me` - My-profile

Description: Get our profile details by giving Access token. After getting access Token from login end point we need to give this acces token at the header in the authorization section after selection Bearer token. 


#### 🔸 Headers

#### Go to authorization -> Select Bearer Token -> Give Access Token

#### We can get Access token from Login API 

Request body

```json

success response

{
    "user": {
        "_id": "69548a3603343d3c3554da86",
        "username": "Kusuma Yekula",
        "email": "kusumayekula0191@gmail.com",
        "profileId": 123,
        "avatar": "",
        "gender": "prefer_not_to_say",
        "onlineStatus": "online",
        "lastSeen": "2025-12-31T02:57:00.608Z",
        "createdAt": "2025-12-31T02:28:06.096Z",
        "updatedAt": "2025-12-31T02:57:00.608Z",
        "__v": 0
    }
}
```

### 5. `POST /https://api.ayrene.com/api/auth/logout` - Logout

Description: Logout profile by using Access token only.

#### 🔸 Headers

#### Go to authorization -> Select Bearer Token -> Give Access Token

#### We can get Access token from Login API 

Request body

```json
{
    "email": "kusumayekula0191@gmail.com",
    "password": "Kusuma@123"
}

success response

{
    "message": "Logout successful"
}
```

### 6. `POST /https://api.ayrene.com/api/auth/delete-by-profileId` - Delete profile by ProfileId

Description: Delete profile by profileId using ProfileId.

#### 🔸 Headers

#### Go to authorization -> Select Bearer Token -> Give Access Token

#### We can get Access token from Login API 

Request body

```json

{
    "profileId": "123"
}

success response

{
    "success": true,
    "message": "User deleted successfully"
}
```

## Users API Documentation


### 1. `GET /https://api.ayrene.com/api/users` - Users

Description: Getting all users.

#### 🔸 Headers

#### Go to authorization -> Select Bearer Token -> Give Access Token

#### We can get Access token from Login API 


```json
success response
{
    "users": [
        {
            "avatar": "",
            "onlineStatus": "offline",
            "_id": "68db5b27ef9d647bf9bd867c",
            "email": "kusumayekula0191@gmail.com",
            "lastSeen": "2025-12-05T12:50:47.900Z"
        },
        {
            "_id": "69240122e0963acdc6f09361",
            "username": "John",
            "email": "infinitelookss@gmail.com",
            "avatar": "",
            "onlineStatus": "online",
            "lastSeen": "2025-11-28T09:17:57.701Z"
        },
        {
            "_id": "69269d4a5f9c22a67b4096f6",
            "username": "kusumayekula872@gmail.com",
            "email": "kusumayekula872@gmail.com",
            "avatar": "",
            "onlineStatus": "offline",
            "lastSeen": "2025-11-26T06:25:14.546Z"
        },
        {
            "_id": "69292b586065d43dd4fbb504",
            "username": "narendrajanga22@gmail.com",
            "email": "narendrajanga22@gmail.com",
            "avatar": "",
            "onlineStatus": "offline",
            "lastSeen": "2025-11-28T04:56:45.455Z"
        }
    ]
}
```
### 2. `POST /https://api.ayrene.com/api/users/profile/by-user-id` - Getting profile by User by ID

Description: Getting user through the user_id along with access token.

#### 🔸 Headers

#### Go to authorization -> Select Bearer Token -> Give Access Token

#### We can get Access token from Login API 

```json
{
    "userId": "6932bc503d76faaaee7b413e"
}

success response

{
    "profile": {
        "_id": "6932bc503d76faaaee7b413e",
        "username": "Kusuma",
        "email": "kusuma7dev@gmail.com",
        "avatar": "",
        "gender": "female",
        "dateOfBirth": "2001-05-10T00:00:00.000Z",
        "address": "Jupudi,Amaravati,Guntur,AP-522436",
        "onlineStatus": "online",
        "lastSeen": "2025-12-29T17:41:47.292Z",
        "profileId": 699
    }
}
```
### 3. `POST /https://api.ayrene.com/api/users/profile/by-by-email` - Getting profile by Email

Description: Getting user through the email along with access token.

#### 🔸 Headers

#### Go to authorization -> Select Bearer Token -> Give Access Token

#### We can get Access token from Login API 

```json
{
    "email": "kusuma7dev@gmail.com"
}

success response

{
    "profile": {
        "_id": "6932bc503d76faaaee7b413e",
        "username": "Kusuma",
        "email": "kusuma7dev@gmail.com",
        "avatar": "",
        "gender": "female",
        "dateOfBirth": "2001-05-10T00:00:00.000Z",
        "address": "Jupudi,Amaravati,Guntur,AP-522436",
        "onlineStatus": "online",
        "lastSeen": "2025-12-29T17:41:47.292Z",
        "profileId": 699
    }
}
```

### 4. `POST /https://api.ayrene.com/api/users/profile/by-profileId` - Getting profile by ProfileId

Description: Getting user through the email along with access token.

#### 🔸 Headers

#### Go to authorization -> Select Bearer Token -> Give Access Token

#### We can get Access token from Login API 

```json
{
    "profileId": "699"
}

success response

{
    "profile": {
        "_id": "6932bc503d76faaaee7b413e",
        "username": "Kusuma",
        "email": "kusuma7dev@gmail.com",
        "avatar": "",
        "gender": "female",
        "dateOfBirth": "2001-05-10T00:00:00.000Z",
        "address": "Jupudi,Amaravati,Guntur,AP-522436",
        "onlineStatus": "online",
        "lastSeen": "2025-12-29T17:41:47.292Z",
        "profileId": 699
    }
}
```

### 5. `PUT /https://api.ayrene.com/api/users/profile` - Update profile

Description: Updating profile through giving an extra information.

Request Body

#### 🔸 Headers

#### Go to authorization -> Select Bearer Token -> Give Access Token

#### We can get Access token from Login API 

```json
{
  "username": "Kusuma",
  "gender": "female",
  "dateOfBirth": "2001-05-10",
  "address": "Jupudi,Amaravati,Guntur,AP-522436"
}
success response

{
    "message": "Profile updated successfully",
    "user": {
        "_id": "6932bc503d76faaaee7b413e",
        "username": "Kusuma",
        "email": "kusuma7dev@gmail.com",
        "avatar": "",
        "gender": "female",
        "dateOfBirth": "2001-05-10T00:00:00.000Z",
        "address": "Jupudi,Amaravati,Guntur,AP-522436",
        "onlineStatus": "online",
        "lastSeen": "2025-12-05T11:42:28.954Z",
        "createdAt": "2025-12-05T11:04:48.214Z",
        "updatedAt": "2025-12-05T17:20:07.731Z",
        "__v": 0
    }
}
```

### 6. `PUT /https://api.ayrene.com/api/users/status` - Giving status

Description: Giving the status to the user .

Request Body

#### 🔸 Headers

#### Go to authorization -> Select Bearer Token -> Give Access Token

#### We can get Access token from Login API 

```json
{
     "status": "online"
}

success response

{
     "message": "Status updated successfully",
    "status": "online"
}
```



## Messages API Documentation


### 1. `POST /https://api.ayrene.com/api/messages/send` - Send Message

Description: Sending a message from sender to reciever.

Request Body
```json
{
  "receiverId": "69240122e0963acdc6f09361",
  "content": "Hello John"
}

success response
{
"message": {
        "sender": {
            "_id": "6932bc503d76faaaee7b413e",
            "username": "Kusuma",
            "avatar": ""
        },
        "receiver": {
            "_id": "69240122e0963acdc6f09361",
            "username": "John",
            "avatar": ""
        },
        "content": "Hello John",
        "messageType": "text",
        "fileUrl": null,
        "fileName": null,
        "fileSize": null,
        "status": "sent",
        "deliveredAt": null,
        "readAt": null,
        "isDeleted": false,
        "deletedAt": null,
        "_id": "6935ce203d76faaaee7b4191",
        "createdAt": "2025-12-07T18:57:36.609Z",
        "updatedAt": "2025-12-07T18:57:36.609Z",
        "__v": 0
    }
}
```

### 2. `PUT /https://api.ayrene.com/api/messages/mark-read/6935ce203d76faaaee7b4191` - Read Message

Description: Reading a mesage through reciver_id.

Request Body

#### 🔸 Headers

#### Go to authorization -> Select Bearer Token -> Give Access Token

#### We can get Access token from Login API 

```json
{
    "content": "Hello John"
}

success response
{
    "message": "Messages marked as read"
}
```

### 3. `GET /https://api.ayrene.com/api/messages/conversation/6932bc503d76faaaee7b413e` - Getting conversations

Description: Getting conversation by using user_id.

#### 🔸 Headers

#### Go to authorization -> Select Bearer Token -> Give Access Token

#### We can get Access token from Login API 

```json


success response
{
    "messages": [],
    "conversation": "6935d29c3d76faaaee7b41a0"
}
```

### 4. `Post /https://api.ayrene.com/api/messages/send-file` - Sending File

Description: Send a file to receiver through receiverId.

Request body
#### 🔸 Headers

#### Go to authorization -> Select Bearer Token -> Give Access Token

#### We can get Access token from Login API 

Body → form-data

| KEY            | VALUE → What you enter     | TYPE |
| -------------- | -------------------------- | ---- |
| **file**       | (choose file)              | File |
| **receiverId** | `69240122e0963acdc6f09361` | Text |


```json

success response

{
    "message": {
        "sender": {
            "_id": "6932bc503d76faaaee7b413e",
            "username": "Kusuma",
            "avatar": ""
        },
        "receiver": {
            "_id": "69240122e0963acdc6f09361",
            "username": "John",
            "avatar": ""
        },
        "messageType": "image",
        "fileUrl": "/uploads/files/1765182418450-3021888-ChatGPT Image Dec 4, 2025, 11_35_14 PM.png",
        "fileName": "ChatGPT Image Dec 4, 2025, 11_35_14 PM.png",
        "fileSize": 4630,
        "status": "sent",
        "deliveredAt": null,
        "readAt": null,
        "isDeleted": false,
        "deletedAt": null,
        "_id": "69368bd23d76faaaee7b421b",
        "createdAt": "2025-12-08T08:26:58.453Z",
        "updatedAt": "2025-12-08T08:26:58.453Z",
        "__v": 0
    }
}
```

### 5. `GET /https://api.ayrene.com/api/messages/conversations` - Getting conversation

Description: Getting  all conversations.

#### 🔸 Headers

#### Go to authorization -> Select Bearer Token -> Give Access Token

#### We can get Access token from Login API 

```json

success response
{
    "conversations": [
        {
            "_id": "6935d29c3d76faaaee7b41a0",
            "participants": [
                {
                    "_id": "6932bc503d76faaaee7b413e",
                    "username": "Kusuma",
                    "avatar": "",
                    "onlineStatus": "online",
                    "lastSeen": "2025-12-05T11:42:28.954Z"
                },
                {
                    "_id": "69240122e0963acdc6f09361",
                    "username": "John",
                    "avatar": "",
                    "onlineStatus": "online",
                    "lastSeen": "2025-11-28T09:17:57.701Z"
                }
            ],
            "lastMessage": {
                "_id": "69368bd23d76faaaee7b421b",
                "sender": "6932bc503d76faaaee7b413e",
                "receiver": "69240122e0963acdc6f09361",
                "messageType": "image",
                "fileUrl": "/uploads/files/1765182418450-3021888-ChatGPT Image Dec 4, 2025, 11_35_14 PM.png",
                "fileName": "ChatGPT Image Dec 4, 2025, 11_35_14 PM.png",
                "fileSize": 4630,
                "status": "sent",
                "deliveredAt": null,
                "readAt": null,
                "isDeleted": false,
                "deletedAt": null,
                "createdAt": "2025-12-08T08:26:58.453Z",
                "updatedAt": "2025-12-08T08:26:58.453Z",
                "__v": 0
            },
            "unreadCount": {
                "69240122e0963acdc6f09361": 2,
                "6932bc503d76faaaee7b413e": 0
            },
            "lastMessageAt": "2025-12-08T08:26:58.453Z",
            "createdAt": "2025-12-07T19:16:44.449Z",
            "updatedAt": "2025-12-08T08:26:59.039Z",
            "__v": 0
        },
        {
            "_id": "69362c573d76faaaee7b4207",
            "participants": [
                {
                    "_id": "6932bc503d76faaaee7b413e",
                    "username": "Kusuma",
                    "avatar": "",
                    "onlineStatus": "online",
                    "lastSeen": "2025-12-05T11:42:28.954Z"
                }
            ],
            "lastMessage": null,
            "unreadCount": {},
            "lastMessageAt": "2025-12-08T01:39:35.895Z",
            "createdAt": "2025-12-08T01:39:35.896Z",
            "updatedAt": "2025-12-08T01:39:35.896Z",
            "__v": 0
        }
    ]
}
```

## Posts API Documentation


### 1. `POST /https://api.ayrene.com/api/posts`

Description: Post a posts.

Request Body
```json
{
  "title": "Morning Whishes",
  "description": "Whishes",
  "content": "Hello Friends a very good morning"
}

success response
{
    "success": true,
    "post": {
        "title": "Morning Whishes",
        "content": "Hello Friends a very good morning",
        "description": "Whishes",
        "author": {
            "_id": "6932bc503d76faaaee7b413e",
            "username": "Kusuma",
            "avatar": ""
        },
        "status": "active",
        "_id": "693615f43d76faaaee7b41c3",
        "likes": [],
        "comments": [],
        "createdAt": "2025-12-08T00:04:04.487Z",
        "updatedAt": "2025-12-08T00:04:04.487Z",
        "__v": 0
    }
}
```

### 2. `POST /https://api.ayrene.com/api/posts/693615f43d76faaaee7b41c3/like`

Description: Liking a post by using post_id.

Request Body
```json
{
  "title": "Morning Whishes",
  "description": "Whishes",
  "content": "Hello Friends a very good morning"
}

success response
{
    "success": true,
    "post": {
        "_id": "693615f43d76faaaee7b41c3",
        "title": "Morning Whishes",
        "content": "Hello Friends a very good morning",
        "description": "Whishes",
        "author": {
            "_id": "6932bc503d76faaaee7b413e",
            "username": "Kusuma"
        },
        "status": "active",
        "likes": [
            {
                "user": {
                    "_id": "6932bc503d76faaaee7b413e",
                    "username": "Kusuma"
                },
                "_id": "6936183a3d76faaaee7b41c8",
                "createdAt": "2025-12-08T00:13:46.916Z"
            }
        ],
        "comments": [],
        "createdAt": "2025-12-08T00:04:04.487Z",
        "updatedAt": "2025-12-08T00:13:46.918Z",
        "__v": 1
    },
    "likes": [
        {
            "user": {
                "_id": "6932bc503d76faaaee7b413e",
                "username": "Kusuma"
            },
            "_id": "6936183a3d76faaaee7b41c8",
            "createdAt": "2025-12-08T00:13:46.916Z"
        }
    ]
}
```

### 3. `POST /https://api.ayrene.com/api/posts/693615f43d76faaaee7b41c3/comment`

Description: Giving comment a post by using post_id.

Request Body
```json
{
  "title": "Morning Whishes",
  "description": "Whishes",
  "content": "Hello Friends a very good morning"
  "text": "Nice Post"
}

success response
{
    "success": true,
    "comments": [
        {
            "user": {
                "_id": "6932bc503d76faaaee7b413e",
                "username": "Kusuma",
                "avatar": ""
            },
            "text": "Nice Post",
            "_id": "693619c33d76faaaee7b41d8",
            "createdAt": "2025-12-08T00:20:19.160Z"
        }
    ]
}
```

### 4. `GET /https://api.ayrene.com/api/posts/my-posts`

Description: Getting existing post with that login profile.

#### 🔸 Headers

#### Go to authorization -> Select Bearer Token -> Give Access Token

#### We can get Access token from Login API 

```json
{
  "email": "kusuma7dev@gmail.com",
    "password": "Kusuma@123",
    "username": "Kusuma"
}

success response
{
    "success": true,
    "posts": [
        {
            "_id": "693615f43d76faaaee7b41c3",
            "title": "Morning Whishes",
            "content": "Hello Friends a very good morning",
            "description": "Whishes",
            "author": {
                "_id": "6932bc503d76faaaee7b413e",
                "username": "Kusuma",
                "avatar": ""
            },
            "status": "active",
            "likes": [
                {
                    "user": {
                        "_id": "6932bc503d76faaaee7b413e",
                        "username": "Kusuma"
                    },
                    "_id": "6936183a3d76faaaee7b41c8",
                    "createdAt": "2025-12-08T00:13:46.916Z"
                }
            ],
            "comments": [
                {
                    "user": {
                        "_id": "6932bc503d76faaaee7b413e",
                        "username": "Kusuma",
                        "avatar": ""
                    },
                    "text": "Nice Post",
                    "_id": "693619c33d76faaaee7b41d8",
                    "createdAt": "2025-12-08T00:20:19.160Z"
                }
            ],
            "createdAt": "2025-12-08T00:04:04.487Z",
            "updatedAt": "2025-12-08T00:20:19.161Z",
            "__v": 2
        }
    ]
}
```

### 5. `PUT /https://api.ayrene.com/api/posts/693615f43d76faaaee7b41c3`

Description: Updating a post by giving an extra information.

#### 🔸 Headers

#### Go to authorization -> Select Bearer Token -> Give Access Token

#### We can get Access token from Login API 

```json
{
  "content": "Hello Friends a very good morning. A very sweet message fron your friend"
}

success response
{
    "success": true,
    "post": {
        "_id": "693615f43d76faaaee7b41c3",
        "title": "Morning Whishes",
        "content": "Hello Friends a very good morning. A very swwet message fron your friend",
        "description": "Whishes",
        "author": {
            "_id": "6932bc503d76faaaee7b413e",
            "username": "Kusuma",
            "avatar": ""
        },
        "status": "active",
        "likes": [
            {
                "user": "6932bc503d76faaaee7b413e",
                "_id": "6936183a3d76faaaee7b41c8",
                "createdAt": "2025-12-08T00:13:46.916Z"
            }
        ],
        "comments": [
            {
                "user": "6932bc503d76faaaee7b413e",
                "text": "Nice Post",
                "_id": "693619c33d76faaaee7b41d8",
                "createdAt": "2025-12-08T00:20:19.160Z"
            }
        ],
        "createdAt": "2025-12-08T00:04:04.487Z",
        "updatedAt": "2025-12-08T00:37:35.639Z",
        "__v": 2
    }
}
```

### 6. `GET /https://api.ayrene.com/api/posts`

Description: Getting all the posts.

#### 🔸 Headers

#### Go to authorization -> Select Bearer Token -> Give Access Token

#### We can get Access token from Login API 

```json
success response
{
    "success": true,
    "posts": [
        {
            "_id": "693615f43d76faaaee7b41c3",
            "title": "Morning Whishes",
            "content": "Hello Friends a very good morning. A very swwet message fron your friend",
            "description": "Whishes",
            "author": {
                "_id": "6932bc503d76faaaee7b413e",
                "username": "Kusuma",
                "avatar": ""
            },
            "status": "active",
            "likes": [
                {
                    "user": {
                        "_id": "6932bc503d76faaaee7b413e",
                        "username": "Kusuma"
                    },
                    "_id": "6936183a3d76faaaee7b41c8",
                    "createdAt": "2025-12-08T00:13:46.916Z"
                }
            ],
            "comments": [
                {
                    "user": {
                        "_id": "6932bc503d76faaaee7b413e",
                        "username": "Kusuma",
                        "avatar": ""
                    },
                    "text": "Nice Post",
                    "_id": "693619c33d76faaaee7b41d8",
                    "createdAt": "2025-12-08T00:20:19.160Z"
                }
            ],
            "createdAt": "2025-12-08T00:04:04.487Z",
            "updatedAt": "2025-12-08T00:37:35.639Z",
            "__v": 2
        }
    ],
    "pagination": {
        "current": 1,
        "total": 1,
        "hasNext": false,
        "hasPrev": false
    }
}
```

### 7. `DELETE /https://api.ayrene.com/api/posts/693615f43d76faaaee7b41c3/comment/693619c33d76faaaee7b41d8`

Description: Deleting comment from the post.

#### 🔸 Headers

#### Go to authorization -> Select Bearer Token -> Give Access Token

#### We can get Access token from Login API 

```json
success response
{
    "success": true,
    "message": "Comment deleted successfully"
}
```

### 9. `DELETE /https://api.ayrene.com/api/posts/693615f43d76faaaee7b41c3`

Description: Deleting a post by post_id.

#### 🔸 Headers

#### Go to authorization -> Select Bearer Token -> Give Access Token

#### We can get Access token from Login API 

```json

success response
{
    "success": true,
    "message": "Post deleted successfully"
}
```

