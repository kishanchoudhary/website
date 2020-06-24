


# BugBounty to OSWE (Conquering The Fear Of Failure)

_“*Just because you got failure doesn't mean you can't succeed!*”_ 


**Hey There**

As I have promised everybody that I will be sharing my experience of OSWE certification,  Firstly if you want to achieve this certification you must be handy with this book "**The Web Application Hacker's Handbook: Finding and Exploiting Security FLAWS**" else you won't understand what the course is for.


## Before taking the Course.

***Resources:*** 
-

`Hackers Handbook`
-
- [http://index-of.es/EBooks/11_TheWeb%20Application%20Hackers%20Handbook.pdf](http://index-of.es/EBooks/11_TheWeb%20Application%20Hackers%20Handbook.pdf)
	
 `Javascript for Pentesters`
-
- [https://www.pentesteracademy.com/course?id=11](https://www.pentesteracademy.com/course?id=11)

 `Java Deserialization `	
-
- [https://nytrosecurity.com/2018/05/30/understanding-java-deserialization/](https://nytrosecurity.com/2018/05/30/understanding-java-deserialization/)
- [https://diablohorn.com/2017/09/09/understanding-practicing-java-deserialization-exploits/](https://diablohorn.com/2017/09/09/understanding-practicing-java-deserialization-exploits/)

`SQL injections`
- 
- [https://www.infigo.hr/files/INFIGO-TD-2009-04_PostgreSQL_injection_ENG.pdf](https://www.infigo.hr/files/INFIGO-TD-2009-04_PostgreSQL_injection_ENG.pdf)(Thank me later for this :D )

- [https://www.sqlinjection.net/time-based/](https://www.sqlinjection.net/time-based/)

`Type Juggling`
-
- [https://owasp.org/www-pdf-archive/PHPMagicTricks-TypeJuggling.pdf](https://owasp.org/www-pdf-archive/PHPMagicTricks-TypeJuggling.pdf)

-[https://www.blackhat.com/presentations/bh-usa-07/Morin/Whitepaper/bh-usa-07-morin-WP.pdf](https://www.blackhat.com/presentations/bh-usa-07/Morin/Whitepaper/bh-usa-07-morin-WP.pdf)

 
 `Challenges`
-
- [https://www.vulnhub.com/entry/devrandom-pipe,124/](https://www.vulnhub.com/entry/devrandom-pipe,124/) (Php Deserialization)
- [https://edabit.com/](https://edabit.com/) (Javascript, Java, PHP)
- [https://sarthaksaini.com/2019/awae/xss-rce.html](https://sarthaksaini.com/2019/awae/xss-rce.html)(Must practice)
- [http://leettime.net/sqlninja.com/tasks/delay_ch4.php](http://leettime.net/sqlninja.com/tasks/delay_ch4.php)


 `Python`
-
- [https://requests.readthedocs.io/en/master/](https://requests.readthedocs.io/en/master/)
- [https://www.tutorialspoint.com/python3/index.htm](https://www.tutorialspoint.com/python3/index.htm)

These are some important resources to practice  before buying the course. Try to spend more time mastering these Vulnerabilities and exercises. 

# My Journey

I bought this course on 29 December 2019 was lucky enough and got this course for 1000$, The only bounty which I got in December 2019. If I speak about bug bounty I do bug bounty every alternative day and when I do I go for straight wide scope targets. So I lost my job on November 28, 2019 . and then I planned for OSWE,  But I had no $$ and didn't get paid by salary too and it was also a bit difficult to pay my bills and keep everything smooth. so in December working on both was a bit difficult but yeah its a good practice to keep a time table of work, and **do bug-bounty in silent place to focus on the target**, so I prefer bug-bounty at late nights with a cup of coffee. 

coffee.gif

 I took a challenge to earn 1000$ in 20 days.  but yeah I was looking for higher severity bugs. spent a week got none but a few P4 triaged. So I planned "Why don't I focus on 10 P4 bugs " to reach the target. its the same effort reporting 10 bugs with an easy methodology or spending a lot of time looking for P1 or P2. so I reported around 22 bugs, Out of 22 12 Triaged rest marked as NA, Duplicate, Won't fix. well, that was easy with less effort and less time in 2 weeks got 1200$ and also been practicing on the Resources which I have provided at the beginning of the blog. I paid and got my labs started on 29 December 2019, There were totally 5 machines in the lab, at first, I thought it's easy but it was not as I expected I spent 3 days watching videos and reading the pdf it was harder than I expected it was completely on reading source code and triggering the bug. PFFT holy hell this is some next-level thing, I knew only basic programming on python3. 

Nervous.gif

I was a lot nervous and did approach the lab slowly spending time on it and learning python along with labs, I was getting harder and harder day by day. I started spending more than 12 hours a day on lab and 5-6 hours on python. spending 16-18 hours on this course was really tough. once I thought I need more experience and wanted to quit but, I spent 1000$ I don't wanna waste it that way by giving up. So I took a break for a day and met my friends and told him how hard it is to work on front and backend as well its not like bug-bounty web, its a whole like a developer + pentester on steroids using all kinda debugging stuff,  My friend's response was simple "TRY HARDER", "Go Hard Else Go Home ". He pissed me off but yeah he was right. I finished my first machine in 4 days with Extra miles.

Exhausted GIF 

I moved to the 2nd machine which was also a PHP machine,  this was one of my favorite machines in the lab I enjoyed learning type juggling and Blind SQLI. holy moly I would never get to learn these things on the internet that easy, I finished this machine in 3-4 days.  10 days of my labs completed 2 machines. But life had other problems as I've been busy on labs also I had no source for income I planned to finish the next nodejs machine and will go for bug hunting for some time, This machine was a fortune for me. after completing this machine I felt a strong from inside as I learned to bypass safe eval :D,  18 days completed 3 machines.  it was harder than my expectations and far beyond my current skillset, I took a break for a day and was chilling out with my buddies, but still worried about the 2 last machines and nearly 11 days left I was worried a lot, and then I continued with my next machine, Oh god it was a nightmare JAVA machine. I hated java from the very beginning as I never understood a java code the bug was quite simple Postgre SQL injection but the source code was huge, I spent 3 days just scrolling and trying to understand what was happening in the code. I had less time but I tried my best to complete it as instructed in course. 

crazy,gif

 The last machine made me go crazy I was soo pissed at offsec yelling "How can they expect someone to look for a bug in such a huge code base which has nearly 1000 lines ". But damn I could only solve as it was instructed by the lab video instructor. 


## First Exam attempt 

On Feb 14, 2020, I gave my first exam attempt, I was really very nervous about the exam and I couldn't sleep well because I was tensed a lot. my exam started around the morning at 3:30 Am. I started with the first machine exploited the first stage and I thought the exam machine could be easy as I spent hours on exploiting auth bypass it was bit tricky but yeah it was a good experience as I was able to obtain 35 points after spending nearly 12-15 hours moved forward to achieve Remote code execution, But thanks to the hard practice on labs I was able to achieve RCE and I took me almost a day to finish the first machine. Moved to 2nd machine It was the worst of worst, Huge source code and I had no idea where to look for the bug I felt very low but still I tried to look for something and did spend like 3-4 hours just scrolling at the code and I couldn't make it on first because i didn't have enough skills to take down the machine and I gave and told the Procter to end my exam :(. I failed my first attempt, This put me in depression for a week.  I tried tackling and did bug-bounty in march with what all I learned in OSWE labs and first exam experience but yeah if you work hard the whole base is your I spent a week on synack and my first bug was accepted :D and same I earned another 2600$ from bug crowd. Whatever i learned in OSWE was not a failure.


## Second Attempt

On April 9, 2020, After a month of the first failure,  I traveled to Dehradun to meet my Infosec buddies and I paid the retake and it was my bad idea to schedule the exam in the place where there is no stable internet, A big mistake and also the exam machine was different it went insane on another level of insanity, at least i was able to dot after a lot of efforts was able to score 35 points but bad internet kept my proctor tab crashing and I was using my old laptop which was pretty crashing on running multiple tasks, again after spending 14 hours I gave up on my second attempt. I started to feel too low and I was on an edge to give up and leave this as I thought its beyond abilities, Depression didn't leave me alone I was quite depressed for weeks, I started hating myself and was very pissed and I did nothing for 2-3 weeks. But still, I didn't want to give up.


## Giving Up was not an option.

So at the end of April, i took advice from one of my senior friends, "how can I pass this exam this is worst than anything" his answer was simple "Try Harder" work on those skills where u lack a lot of concentrate on your weakness sharpen them. So I took a month challenge, I started python, java, PHP, and js. I didn't master these but I practiced a bit basic and up to the level of understanding the code. I started to practice day and night, I could see my eyes where totally dark and also I was curious about the vulnerability in the exam, which didn't let me sleep and thanks to my friend who helped me and motivated me on this journey, one month no excuses just one thing on my mind "TRY HARDER" its a CTF its meant to be vulnerable, I had a pretty good time spending COVID-19 Lockdown at a friends place in north India. 


## The Third Attempt ("GO HARD ELSE GO HOME")


 So after spending a good time in North India, i came back home to Bangalore, I was far from my home for 3 months, I was soo happy because all those 3 months spent there was not a waste but I was a lot productive in those 3 months, I scheduled my exam on 15 June 2020, But this time I was ready to face the BEAST, so my exam started at morning 7:30 am I was all ready with a Coffee MUG highly concentrated and strong coffee, after id verification, I choose to attempt the hard machine first, I spent around 2 hours analyzing the source code and understanding the application. so I found an entry after 2-3 hours of analysis and started to google the functions which were used in the application I spent nearly 6 hours and exploited the first vulnerability and I took enough break and coffee, I continued with the exam and finished the auth bypass in a single day. I was soo happy to finish the auth bypass of the hardest machine.  and I moved to another machine which was quite easy for me and I faced it earlier. so after spending like 8 hours on the other machine I have successfully exploited the machine and gained RCE,  So what am I thinking,  I'm already in a green zone I spent nearly 34 hours to get to 85 points, "YEAH!! GO HARD ELSE GO HOME".  I started to take a screenshot for my report and coded the exploit code for both the machines. :D 

After ending the exam I was so happy that I couldn't control myself and I was  in tears, I spent god damnn !! 6 months to get till here researching learning, reading other people blogs of their experiences, and  here I'm writing my own experience how I passed this toughest exam,


## Report Writing.

Offsec provides its own official report template for reporting, your report must contain all the steps and all the steps should be explained clearly with appropriate screenshot and details.

For more information: https://support.offensive-security.com/oswe-exam-guide/


## Achievements 

- 2018 - CEH (Certified Ethical Hacker)
- 2019 - OSCP (Offensive Security Certified Professional )
- 2020 OSWE (Offensive Security Web Expert )

