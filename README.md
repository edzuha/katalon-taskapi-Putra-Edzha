# katalon-taskapi-Putra-Edzha

# **Objective**
This application focuses on how the API works by testing all API end points.

# **App Usage Guide**
**Requirements that must be inserted before running this application are :**
* Using Groovy language based on Katalon Studio ```version 9.7.2```
* Testing is done on the End-Point API provided by [herokuapp](https://restful-booker.herokuapp.com/)
* Testing was carried out with the Google Chrome Website Browser ```Version 130.0.6723.117``` (Official Build) (64-bit)

# **Summary of Testing Results**
In the implementation of testing, testing was carried out on 4 Test Cases with the results:
```
4 Passed
0 Failed
0 Not Executed
```
So the test result is 100% Passed

# **Report**
In testing, if you have to test one test case at a time, it will take a long time, so a **Test Suite** is made, so that you can run several test cases simultaneously, namely:
```
TS Booking
```
In the **Test Suite** there are 4 test cases:
```
TC CreateBooking
TC GetBookingID
TC UpdateBooking
TC DeleteBooking
```

# **End Point**
The overall endpoints in this project are :

First create new ```staging``` profiles that contain global variables
```
baseURL = https://restful-booker.herokuapp.com/
username_admin = admin
password_123 = password123
refresh_token = ""
refresh_ID = ""
```
In each Object Repository, add local variables
```
host = GlobalVariable.baseURL
username = GlobalVariable.username_admin
paswword = GlobalVariable.password_123
token = GlobalVariable.refresh_token
ID = GlobalVariable.refresh_ID
```

**POST Create Token**

To Create Token, provided 1 pages that will generate a response code ```200 OK``` and result user
```
${host}/auth
```
**POST Create Booking ID**

```
${host}/booking
```
To create id, by entering in the ```HTTP BODY``` with the ```TEXT``` and ```JSON``` attributes, which will produce a ```200 OK``` response code and the results of adding data:
```
{
    "firstname" : "Putra",
    "lastname" : "edzha",
    "totalprice" : 4800,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2024-11-01",
        "checkout" : "2024-11-03"
    },
    "additionalneeds" : "Dinner"
}
```
**GET Booking IDs by ALL ID**

Used for viewing all IDs
```
${host}/booking
```
**GET Booking IDs by ID**

View one of the IDs that have been created
```
${host}/booking/${ID}
```
**GET Booking IDs by Name**

View one of the IDs that have been created by filling in the firstname and lastname
```
${host}/booking?firstname=Putra&lastname=Edzuha
```
**PUT Update Booking ID**
```
${host}/booking/${ID}
```
To update id, by entering in the ```HTTP BODY``` with the ```TEXT``` and ```JSON``` attributes, which will produce a ```200 OK``` response code and the results of adding data:
```
{
    "firstname" : "Putra",
    "lastname" : "edzha",
    "totalprice" : 48000,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2024-11-01",
        "checkout" : "2024-11-03"
    },
    "additionalneeds" : "Massage"
}
```
**PATCH Partial Update Booking ID**
```
${host}/booking/${ID}
```
To partial update id, by entering in the ```HTTP BODY``` with the ```TEXT``` and ```JSON``` attributes, which will produce a ```200 OK``` response code and the results of adding data:
```
{
    "firstname" : "Putra",
    "lastname" : "Edzuha"
}
```
**DELETE Booking ID**

To delete ID, Will generate response code ```201 OK``` and ```Created```, because it has been deleted.
```
${host}/booking/${ID}
```
