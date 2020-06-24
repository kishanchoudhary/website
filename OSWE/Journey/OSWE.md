
# BugBounty to OSWE (Conquering The Fear Of Failure)

_“*Just because you got failure doesn't mean you can't succeed!*”_ 


**Hey There**

As I have promised everybody that I will be sharing my experience of OSWE certification,  Firstly if you want to achieve this certification you must be handy with this book "**The Web Application Hacker's Handbook: Finding and Exploiting Security Fl**" else you won't understand what the course is for.


## Before taking the Course.

***Resources:*** 
-
`Hackers Handbook`
-
- http://index-of.es/EBooks/11_TheWeb%20Application%20Hackers%20Handbook.pdf
	
 `Javascript for Pentesters`
-
- https://www.pentesteracademy.com/course?id=11 

 `Java Deserialization `	
-
- https://diablohorn.com/2017/09/09/understanding-practicing-java-deserialization-exploits/ 

- https://nytrosecurity.com/2018/05/30/understanding-java-deserialization/

- https://diablohorn.com/2017/09/09/understanding-practicing-java-deserialization-exploits/

`SQL injections`
- 
- https://www.infigo.hr/files/INFIGO-TD-2009-04_PostgreSQL_injection_ENG.pdf (Thank me later for this :D )

- https://www.sqlinjection.net/time-based/

`Type Juggling`
-
- https://owasp.org/www-pdf-archive/PHPMagicTricks-TypeJuggling.pdf

- https://www.blackhat.com/presentations/bh-usa-07/Morin/Whitepaper/bh-usa-07-morin-WP.pdf

 
 `Challenges`
-
- https://www.vulnhub.com/entry/devrandom-pipe,124/ (Php Deserialzation)
- https://edabit.com/ (Javascript, Java, PHP)
- https://sarthaksaini.com/2019/awae/xss-rce.html (Must practice)
- http://leettime.net/sqlninja.com/tasks/delay_ch4.php


These are some important to know before buying the course. and try to spend more time mastering these Vulnerabilities and excersies. 

# My Journey

I bought this course on 29 December 2019 was lucky enough and got this course for 1000$ , The only bounty which i got in December 2019. If i speak about bug bounty i do bug bounty every alternative days and when i do i go for straight wide scope targets. So i lost my job on November 28 2019 . and then i planned for OSWE ,  But i had no $$ and didn't get paid by salary too and it was also bit difficult to pay my bills and keep everything smooth. so in December working on both was bit difficult but yeah its a good practise to keep a time table of work , and **do bugbounty in silent place to focus on the target**  , so i prefer bugbounty at late nights with a cup of coffee.  i took a challenge to earn 1000$ in 20 days.  but yeah i was looking for higher serverity bugs. spent a week got none but a few P4 triaged . So i planned "Why don't i focus on 10 P4 bugs " to reach the target. its the same effort reporting 10 bugs with easy methodology or spening alot time looking for P1 or P2. so i reported around 22 bugs , Out of 22 12 Triaged rest marked as NA , Duplicate , Wont fix. well that was easy with less effort and less time in 2 weeks got 1200$ and also been practising on the Resources which i have provided at the begining of the blog. i paid and got my labs started on 29 December 2019  , There were totally 5 machines in the lab , at first i thought its easy but it was not as i expected i spent 3 days watching videos and reading the pdf it was harder than i expected it was compeltely on reading source code and triggering the bug. PFFT holy hell this is some next level thing , i knew only basic programming on python3. I was alot nervous and did approached the lab slowly spending time on it and learning python along with labs , i was getting harder and harder day by day. i started spending more than 12 hours a day on lab and 5-6 hours on python. spending 16-18 hours on this course was really tough. once i thought i need more experiance and wanted to quit but, I spent 1000$ i dont wanna waste it that way by giving up. So i took a break for a day and met my frienda and told him how hard it is to work on front and backend as well its not like bugbounty web , its a whole like a devloper + penestester on steroids using all kinda debuging stuffs ,  My friends response was simple "TRY HARDER" , "Go Hard Else Go Home ". He pissed me off but yeah he was right. i finished my first machine in 4 days with Extra miles.
 

Moved to 2nd machine which was also a php machine ,  this was one of my favorite machine in the lab i enjoyed learning type juggling and Blind sqli . holy moly i would never get to learn these things on internet that easy ,  i finished this machine in 3-4 days.  10 days of my labs completed 2 machines. But life had other problems as ive been busy on labs also i had no source for income i planned ill finish the next nodejs machine and will go for bug hunting for some time , This machine was a fortune for me . after completing this machine i felt a strong from inside as i learnt to bypass safe eval :D ,  18 days completed 3 machines .  it was harder than my expectations and far beyond my current skillset ,  i took a break for a day and was chilling out with my buddies , but still worried about the 2 last machine and nearly 11 days left i was worried alot , and then i continued with my next machine , Oh god it was a nightmare JAVA machine . I hated java from very begining as i never understood a java code the bug was quite simple Postgre SQL injection but the source code was huge , i spent 3 days just scrolling and trying to understand what was happening in the code. i had less time but i tried my best to complete it as instructed in course .  The last machine made me go crazyy i was soo pissed at offsec  yelling "How can they expect someone to look for a bug in such a huge code base which has nearly 1000 lines ". But damn i could only solve as it was instructed by the lab video instructer. 


## First Exam attempt 

On Feb 14 2020 , i gave my first exam attempt , I was really very nervous about the exam and i couldnt sleep well because i was tensed alot. my exam started around morning 3:30 Am . i started with the first machine exploited the first stage and i thought the exam machine could be easy as i spent hours on exploiting auth bypass it was bit tricky but yeah it was good experiance as i was able to obatain 35 points after spending nearly 12-15 hours moved forward to achieve Remote code execution , But thanks to the hard practice on labs i was able to achive RCE and i took me almost a day to finish first machine.Moved to 2nd machine It was the worst of worst , Huge source code and i had no idea where to look for the bug i felt very low but still i tried to look for something and did spend like 3-4 hours just scrolling at the code and i couldn't make it on first beacause i didnt have enough skills to take down the machine and i gave and told the procter to end my exam :( . I failed my first attempt , This put me in depreesion for a week.  i tried tackling and did bugbounty in march with what all i learnt in OSWE labs and first exam experiance but yeah if you work hard the whole base is your i spent a week on synack and my first bug was accpted :D and same i earned another 2600$ from bugcrowd. What ever i learnt in OSWE was not a failure.


## Second Attempt

On April 9 2020 After a month of first failure ,  I traveled to Dehradun to meet my Infosec buddies and i paid the retake and it was my bad idea to schedule the exam in the place where there is no stable internet , A big mistake and also the exam machine were different it went insane on another level of insanity , atleast i was able after a alot of efforts was able to score 35 points but bad internet kept my proctor tab crashing and i was using my old laptop which was pretty crashing on running multiple tasks , again after spending 14 hours i gave up on my second attempt. I started to feel tooo low and i was on a edge to give up and leave this as i thought its beyond abilities , Depression didnt leave me alone i was quite depreesed for weeks , I started hating myself and was very pissed and i did noting for 2-3 weeks. But still i didn't want to give up.


## Giving Up was not a option.

So in the end of april i took a advice from one of my senior friend , "how can i pass this exam this is worst than anything" his answer was simple "Try Harder" work on those skills where u lack alot concentrate on your weakness sharpen them. So i took a month challenge , i started python , java , php and js . i didnt master these but i practised a bit basic and upto level of understanding the code. i started to practice day and night , i could see my eyes where totally dark and also i was curious about the vulnerabilty in the exam ,which didn't let me sleep and thanks to my friend who helped me and motivated me on  this journey , one month no excuses just one thing on my mind "TRY HARDER" its a CTF its meant to be vulnerable, i had a pretty good time spending COVID-19 Lockdown at a friendsplace in north india. 


## The Third Attempt ("GO HARD ELSE GO HOME")


 So after spending a good time in North india i came back home to Bangalore , i was far from my home for 3 months , I was soo happy because all those 3 months spent there was not a waste but i was alot productive in those 3 months , i scheduled my exam on 15 june 2020, But this time i was ready to face the BEAST , so my exam started at morning 7:30 am i was all ready with a Coffee MUG highly concentrated and strong coffee , after id verification i choose to attemt the hard machine first , I spent around 2 hours analyzing the source code and understanding the application. so i found a entry after 2-3 hours of analysis and started to google the functions which were used in the application i spent nearly 6 hours and exploited the first vulnerabilty and i took enough break and coffee , i countinued with the exam and finished the auth bypass in a single day. i was soo happy to finish the auth bypass of the hardest machine.  and i moved to another machine which was quite easy for me and i faced it earlier . so after spending like 8 hours on the other machine i was successfully exploited the machine and gained RCE ,  So what am i thinking,  im already in a green zone i spent nearly 34 hours to get to 85 points , "YEAH!! GO HARD ELSE GO HOME".  i started to take screenshot for my report and coded the exploit code for both the machines . :D 

After ending the exam I was sooo happy that i couldnt control myself and i was  in tears , i spent god damnn !! 6 months to get till here researching learning , reading other people blogs of their experiance , and  here im writing my own experiance how i passed this toughest exam ,


## Report Writing.

Offsec provides their own official report template for reporting , your report must contain all the steps and all the steps should be explained clearly with appropriate screenshot and details.

For more information : https://support.offensive-security.com/oswe-exam-guide/


## Achievements 

- 2018 - CEH (Certified Ethical Hacker)
- 2019 - OSCP (Offensive Security Certified Professional )
- 2020 OSWE (Offsensive Security Web Expert )


