# A Crazy Open Redirect 

Hey there learners, today's lets look into something which we should always look into it, *"New Features"* yeah you heard it right many application have many new features and stuffs which try make users work more easy ,So here what i did was, I found a short link feature which lead to redirect once the user logins, so not gonna go much in theory lets just jump in :D.

First on the bottom left i found this tiny little option 

1.png

i clicked on it it generated a short link for the report i quickly sent it to burpsuite for analyzing 

2.png 

and checked the response i found a small hash like thing and after looking back at the actual short link ive notice that example.com/s/hash can redirect to other sites 

3.png

I quickly changed the url to https://evil.com in post request and got a another value 

4.png 

so i combined it with https://example.com/s/*"evil hash from response"*

5.png 

i opened it in other browser i was taken to the login page  :\

6.png

once i logged in to my account BOOM!! I was redirected to evil.com

7.png
