# Ayrene API Documentation

This API allows users to register with an email address and password, and log in securely using mail credentials and also to sent and recieve and delivery purpose and upload posts and Designed for integration into web and mobile applications.

---

## 🌐 Base URL

https://api.ayrene.com

---

## 📬 Endpoints Overview

## Authentication API Documentation

 ### 1. `post /https://api.ayrene.com/api/auth/register` — Register User


Request Body
```json
{
   "email": "kusuma7dev@gmail.com",
    "password": "Kusuma@123",
    "username": "Kusuma"
}

Success response

{
    "message": "User registered successfully",
    "user": {
        "username": "Kusuma",
        "email": "kusuma7dev@gmail.com",
        "avatar": "",
        "gender": "prefer_not_to_say",
        "dateOfBirth": null,
        "address": "",
        "onlineStatus": "offline",
        "_id": "6932bc503d76faaaee7b413e",
        "lastSeen": "2025-12-05T11:04:48.214Z",
        "createdAt": "2025-12-05T11:04:48.214Z",
        "updatedAt": "2025-12-05T11:04:48.466Z",
        "__v": 0
    },
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2OTMyYmM1MDNkNzZmYWFhZWU3YjQxM2UiLCJpYXQiOjE3NjQ5MzI2ODgsImV4cCI6MTc2NDkzMzU4OH0.LDo4HsZXCc5kkGTCEzshDwpIpXP1iKH1onzVWUlMpaY",
    "refreshToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2OTMyYmM1MDNkNzZmYWFhZWU3YjQxM2UiLCJpYXQiOjE3NjQ5MzI2ODgsImV4cCI6MTc2NTUzNzQ4OH0.iiU78i81U_E6dUE5G5vabgvavOafJp4KftABsYhT4ZI"
}
```
### 2. `post /https://api.ayrene.com/api/auth/login`— Log In

Request Body
```json

{
     "email": "kusuma7dev@gmail.com",
    "password": "Kusuma@123",
    "username": "Kusuma"
}

Success Response

{
    "message": "Login successful",
    "user": {
        "_id": "6932bc503d76faaaee7b413e",
        "username": "Kusuma",
        "email": "kusuma7dev@gmail.com",
        "avatar": "",
        "gender": "prefer_not_to_say",
        "dateOfBirth": null,
        "address": "",
        "onlineStatus": "online",
        "lastSeen": "2025-12-05T11:04:48.214Z",
        "createdAt": "2025-12-05T11:04:48.214Z",
        "updatedAt": "2025-12-05T11:07:35.336Z",
        "__v": 0
    },
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2OTMyYmM1MDNkNzZmYWFhZWU3YjQxM2UiLCJpYXQiOjE3NjQ5MzI4NTUsImV4cCI6MTc2NDkzMzc1NX0.nrjKKvCJ8fEu3NpWd08QCATDnUkAF_45VaK65vSUU88",
    "refreshToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2OTMyYmM1MDNkNzZmYWFhZWU3YjQxM2UiLCJpYXQiOjE3NjQ5MzI4NTUsImV4cCI6MTc2NTUzNzY1NX0.Lgv1de1PtGPSOrr4sOEaw8PtdZbHCBhO4D46L9n_5vM"
}

```
### 3. `post /https://api.ayrene.com/api/auth/refresh` — Refresh Token
Requires a valid credentils

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

### 4. `Get /https://api.ayrene.com/api/auth/me`

Request body
#### 🔸 Headers

Authorization: Bearer <JWT_ACCESS_TOKEN>

```json
{
  "email": "kusuma7dev@gmail.com",
    "password": "Kusuma@123",
    "username": "Kusuma"
}

success response

{
    "user": {
        "_id": "6932bc503d76faaaee7b413e",
        "username": "Kusuma",
        "email": "kusuma7dev@gmail.com",
        "avatar": "",
        "gender": "prefer_not_to_say",
        "dateOfBirth": null,
        "address": "",
        "onlineStatus": "online",
        "lastSeen": "2025-12-05T11:42:28.954Z",
        "createdAt": "2025-12-05T11:04:48.214Z",
        "updatedAt": "2025-12-05T11:51:01.895Z",
        "__v": 0
    }
}
```

### 5. `post /https://api.ayrene.com/api/auth/logout`

Request body
```json
{
  "email": "kusuma7dev@gmail.com",
    "password": "Kusuma@123",
    "username": "Kusuma"
}

success response

{
    "message": "Logout successful"
}
```

## Users API Documentation
### 1. `Get /https://api.ayrene.com/api/users`


🔸 Headers
Authorization: Bearer <JWT_ACCESS_TOKEN>

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
### 2. `GET /https://api.ayrene.com/api/users/6932bc503d76faaaee7b413e`

Requires an ID and authentication bearer with valid tocken 

🔸 Headers
Authorization: Bearer <JWT_ACCESS_TOKEN>

```json
success response

{
    "message": "Profile updated successfully",
    "user": {
        "_id": "6932bc503d76faaaee7b413e",
        "username": "Kusuma",
        "email": "kusuma7dev@gmail.com",
        "avatar": "",
        "gender": "prefer_not_to_say",
        "dateOfBirth": null,
        "address": "",
        "onlineStatus": "online",
        "lastSeen": "2025-12-05T11:42:28.954Z",
        "createdAt": "2025-12-05T11:04:48.214Z",
        "updatedAt": "2025-12-05T14:11:30.695Z",
        "__v": 0
    }
}
```

### 3. `PUT /https://api.ayrene.com/api/users/profile`

Requires an ID and authentication bearer with valid tocken 
Request Body

🔸 Headers
Authorization: Bearer <JWT_ACCESS_TOKEN>

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

### 4. `PUT /https://api.ayrene.com/api/users/status`

Requires a body as ID and Status and authentication bearer with valid tocken 

Request Body

🔸 Headers
Authorization: Bearer <JWT_ACCESS_TOKEN>

```json
{
 
     "_id": "6932bc503d76faaaee7b413e",
     "status": "online"
}

success response

{
     "message": "Status updated successfully",
    "status": "online"
}
```

## Messages API Documentation
### 1. `POST /https://api.ayrene.com/api/messages/send`

Requires a body as Reciver ID & Content and  authentication bearer with valid tocken

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

### 2. `PUT /https://api.ayrene.com/api/messages/mark-read/6935ce203d76faaaee7b4191`

Requires a body as Reciver ID & Content and  authentication bearer with valid tocken 

Request Body

🔸 Headers
Authorization: Bearer <JWT_ACCESS_TOKEN>

```json
{
    "content": "Hello John"
}

success response
{
    "message": "Messages marked as read"
}
```

### 3. `GET /https://api.ayrene.com/api/messages/conversation/6932bc503d76faaaee7b413e`

Requires a body as Reciver ID & Content and   authentication bearer with valid tocken 

#### 🔸 Headers

Authorization: Bearer <JWT_ACCESS_TOKEN>


```json

{
    "messages": [],
    "conversation": "6935d29c3d76faaaee7b41a0"
}
success response
{
    "message": "Messages marked as read"
}
```

## Posts API Documentation
### 1. `POST /https://api.ayrene.com/api/posts`

Requires a body as Reciver ID & Content and  authentication bearer with valid tocken 

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

Requires a body as Reciver ID & Content and  authentication bearer with valid tocken 

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

Requires a body as Reciver ID & Content and  authentication bearer with valid tocken 

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

#### 🔸 Headers

Authorization: Bearer <JWT_ACCESS_TOKEN>

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

#### 🔸 Headers

Authorization: Bearer <JWT_ACCESS_TOKEN>

```json
{
  "content": "Hello Friends a very good morning. A very swwet message fron your friend"
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

#### 🔸 Headers

Authorization: Bearer <JWT_ACCESS_TOKEN>

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

Requires authentication bearer with valid tocken 

#### 🔸 Headers

Authorization: Bearer <JWT_ACCESS_TOKEN>

```json
success response
{
    "success": true,
    "message": "Comment deleted successfully"
}
```

### 9. `DELETE /https://api.ayrene.com/api/posts/693615f43d76faaaee7b41c3`

Requires authentication bearer with valid tocken 

#### 🔸 Headers

Authorization: Bearer <JWT_ACCESS_TOKEN>

```json

success response
{
    "success": true,
    "message": "Post deleted successfully"
}
```

