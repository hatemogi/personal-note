# Self introduction

Hi, I am Daehyun Kim, a backend software developer with Java, Ruby, and Clojure skills. I am currently a contarct developer and developing a gateway server using Java and Spring Boot for my client. Before becoming a contract developer, I had worked at a company named "Daum Communications" for 10+ years.

## Most Challenging Project

I was involved a project building a Messenger App for iOS called "MyPeople" which was very similar to WhatsApp. My boss told me whether it was possible to develop its working prototype in 3 weeks. It was a time-challenging project. I thought it was very hard to succeed and replied negatively to my boss, then he asked me "What resources do you need to accomplish it"? I mentioned some key members needed then he answered OK and gave all resources we needed. It was very chanlleging in time manner, but showed the prototype working in 21 days. And I learned that if decision makers have a strong desiren to do something and resources are met, some difficult tasks are able to accomplished. And I realized that I might have been a bit negative.

## Most Fun Project

It was to build a Git Repository system for my company. I was convinced that Git VCS has benefits over other VCS such as SVN. At the time, majority of developers in the company was using SVN, I thought it would be nice if my team and hopefully our entire company uses Git. One of the critical barriers using Git was that there was no common repository server in our company while there was a SVN server already. So I built basically a small intra service like GitHub system using Ruby, Sinatra and SQLite3. The timing was nice because many of our developers were getting intereseted in Git. So they were willing to accept my Git repository system. Until my lefting the company more than 90% of our developers used my system. It was very fun to build a small product from scratch and make it spread and used by hundreds of co-workers.

## The worst bug I had.

It was a long time ago, so I don't remember the details, but I remember how I suffered. It was a multi-threding issues on a server built on PThread in C. Frankly I am not so good in C programming. And, ann API function of PThread was ambiguous in Documentation, I assumed the consequences of the function in my own way, and it produced a threading issues having the server down once a week. A small bug in a multi-threaded application is hard to fix because, the problem is hard to reproduced for debugging. Some of the bugs were able to fix use valgrind which is a open-source instrumentation framework. But one of the bugs were unable to be noticed by valgrind, so I had to review entire source line by line few times. The bug I introduced was basically my fault to assume a API's action in my head. So I learned that I should be more careful even in using a simple API and not to make any falsy assumptions.

## The most recent issues

mitmproxy

## Conflicts

I had a sitation that introduced a system failure when our team colaborating with infrastruture team related with DNS system in Daum. I thougth recovering from the failure was most important. But the infra teams' manager was focused on blaming my team and lied about the issue was due to my team members mistake even thougth it was the quite opposite. I was quite angry and could not solve the conflict. I finally understand why he did lie, but I would not do such a thing. I learned that some people lies even the other clearly knows that he was lying. I learned that I need to be calm and react objectively not personally.
