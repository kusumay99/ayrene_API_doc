# Ayrene API Documentation

This API allows users to register with an email address and password, and log in securely using mail credentials and also to sent and recieve and delivery purpose and upload posts and Designed for integration into web and mobile applications.

---

## 🌐 Base URL

https://api.ayrene.com

---

## 📬 Endpoints Overview

 ### 1. `post /https://api.ayrene.com/api/auth/register` — Register User

Requires user credentials

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

Requires a refreshToken
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

Requires a body and authentication bearer with valid tocken 

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

Requires a body and authentication bearer with valid tocken 

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

### 6. `Get /https://api.ayrene.com/api/users`

Requires an active & valid tocken 

```json
{
  "email": "kusuma7dev@gmail.com",
    "password": "Kusuma@123",
    "username": "Kusuma"
}

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
### 7. `Get /https://api.ayrene.com/api/users/profile`

Requires an ID and authentication bearer with valid tocken 

```json
{
   "_id": "6932bc503d76faaaee7b413e"
}

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

### 8. `PUT /https://api.ayrene.com/api/users/profile`

Requires an ID and authentication bearer with valid tocken 

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

### 10. `PUT /https://api.ayrene.com/api/users/status`

Requires a body as ID and Status and authentication bearer with valid tocken 

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


