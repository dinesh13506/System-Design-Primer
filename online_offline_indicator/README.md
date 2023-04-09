# Online offline indicator

## System Requirements

1. User should be able to see if other users are online or offline.
2. System should be scalable, Daily Active users is 100M.
3. A user is said to be online if his/her latest online time is in range of X seconds (configrable) with current time. If difference between current time and his/her latest online time is more than X seconds (configrable) then user is considered to be offline.
4. System should support bulk api to fetch user's status.




## Database Design

| user_id | last_timestamp |
|:-------:| :-------------:|


1. user_id is the unique identifier for a user.
2. last_timestamp is the last timestamp sent by user_id to backend.



## Estimations

Let's suppose that user_id is an integer value of 4 Bytes and time stamp is 4 Bytes.

Total space taken for a user = 8 Bytes

Assume that Daily Active Users = 100 M

Total Storage required  = 800 MBytes


## API's

1. POST, /api/timestamp

Request Body: {
    user_id : int,
    timestamp: int
}

Response Body: {
    code : int,
    message : string
}

2. GET /api/timestamp

Request Body: [{
    user_id : int
}...]

Response Body: {
    code : int,
    data : [{
        user_id : int,
        timestamp: int
    }...]
}