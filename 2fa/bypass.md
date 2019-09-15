# 2FA BYPASS 

Hey there learners , so i got you my write-up on how i bypassed 2fa (2 factor authentication)  by changing the response from authenticated one to unauthenticated so basically i was being to get into the dashboard when i changed response and got into it as fully authenticated user , less theory and lets just jump in :D

* First i've logged in my account using the right credentials account 1. kishan_456

1.png here

* After login it asked me for OTP which was sent on my number

2.png 

* Entered  the OTP which was sent on my phone 

3.png

* Clicked "Verify code " and Intercepted the request and intercepted the Response and copy the response to your notepad.
* 4.png 
* Response 
 5.png
* im logged in now
 6.png

* logged out from the browser and opened a firefox private browsing tab
logged in with the creds as kishan_123 (2nd account)
it asked for a OTP, enter OTP as 123456

7.png

* Click verify code and intercept the request and response , the response will be 200 which will be a error so instead of 200 response paste the response which we intercepted earlier on the 1st account.

Initial response:
8.png
modified response:
9.png

* Once clicked forward in Burpsuite it redirected me directly into the dashboard 

10.png
