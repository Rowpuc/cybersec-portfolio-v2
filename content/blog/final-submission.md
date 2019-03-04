---
title: "Final Submission"
date: 2019-03-04T01:02:01+11:00
draft: false
image: "/img/unsplash-photos-nehfi_SfqtU.jpg"
thumbnail:
---

<h3>Introduction</h3>
<p>Hi, my name is Rowan Puckeridge. I am in my fourth year of my undergraduate bachelor’s degree in Science in Information Technology, majoring in Internetworking and Applications. To follow my journey in a chronological way, please start with my proper <a href="https://www.rjpuc.me/blog/week-1-reflection/">introduction and first reflection here</a>, and then make your way through <a href="https://www.rjpuc.me/blog/week-2-reflection/">week 2</a>, <a href="https://www.rjpuc.me/blog/week-3-reflection/">week 3</a> and finally <a href="https://www.rjpuc.me/blog/week-4-reflection/">week 4’s submission</a> before getting to this conclusion.</p>

<h3>Conclusion</h3>
<p>I started this journey with little to no practical experience regarding offensive security. From subjects such as Cyber Security, I only caught a glimpse of how a practical attack, such as a SYN attack, could be performed. However, we were often taught in a way which held our hand and led us directly to the answer. This did not make for an engaging or thought-provoking learning exercise. My initial objectives for this subject were quite restricted and mainly focused on web application security, as that was what I was predominately interested in, having come from a background of web application development. The first week allowed me to achieve this objective in part, as I was able to develop my skills in performing SQL injection and other basic web attacks through the OWASP Juice shop and Natas challenges.</p>
<p>As I progressed into the second week, I was able to broaden my scope even more to encompass being able to understand and perform both XSS (Cross-site scripting) and XSRF (Cross-site request forgery) attacks. These goals were met during the week, as I was able to gain a much deeper understanding of XSS during Luke’s XSS talk which involved the use of a diagram. By continuing both Natas and Bandit Challenges, I was able to improve both my Linux and web app skills. This allowed to undertake the stored-XSS challenge on root-me where I was successfully able to steal the admin’s cookie.</p>
<p>During the course of week 3, I realised that there was a much greater aspect to offensive security than I had realised; Pen Testing of vulnerable boxes. This is the ultimate challenge as seen by most of the cyber security community. As I had never “owned” a vulnerable machine before, I knew I would have to work up to the more difficult live challenges, such as HackTheBox. I was therefore delighted to receive an introduction to enumeration and exploitation, through tools such as nmap and Metasploit respectively, by both Darsh and the team at Deloitte. This provided me with the tools necessary to start learning and eventually own my first box; Mr. Robot from TryHackMe.</p>
<p>Now that I had had a taste for owning vulnerable boxes, my objective naturally developed into hacking an Active box from HackTheBox. This was a long and tedious process, however, with help from teaching staff, fellow students and Google I was able to own my first live box called Access. Although I had successfully achieved my radically changing objectives, this was only a small portion of what can be learnt and achieved in the Pen Testing community.</p>

<h3>Final Reflective Statement with Artefacts</h3>
<p>The following breaks down my reflection of the ways in which my learning was achieved:</p>

<h4>1. Engage with stakeholders to identify a problem</h4>

<p>As indicated in my conclusion, engaging with stakeholders either one-on-one or through presentations has been a significant part of my learning experiences. This was first evinced with Robert from Gitlab who provided a basis for my understanding of the current state of the security industry and how it got to where it is now. This opportunity also allowed to ask questions about the advantages and disadvantages between Bitbucket and Gitlab as CI/CD products, allowing me to take abstract ideas and put it into a way that made sense for me.</p>
<p>Furthermore, interactive workshops from Darsh, Luke, Deloitte and Rubin gave me a deeper understanding of their respective subject matter. This is definitely true for Luke’s XSS talk, which was perfect for me as it included a whiteboard session in which he broke down concepts into easily understandable ideas. As a visual learner, I greatly appreciated this and was able to identify the problems which cause XSS much more easily.</p>

<img src="/img/reflection-week-2/luke-talk.png" alt="Luke's Talk">
<img src="/img/reflection-week-3/deloitte-talk.png" alt="Deloitte Talk">

<h4>2. Apply design thinking to respond to a defined or newly identified problem</h4>

<p>Throughout the Summer Studio, I had many opportunities to identify security vulnerabilities within a system or web application before formulating a way to exploit these vulnerabilities (as after all, we are looking at the offensive side of security). This was clearly seen during the enumeration process of both the vulnerable machines that I gained ownership of.</p>
<p>Learning the fox and the rabbit hole mentality from Luke provided the basis for this learning. After that, I was able to begin my own enumeration process on Mr Robot. This taught me a valuable lesson; that enumeration is time consuming and requires a lot of research. This definitely affirmed what I had learnt from Luke, making me aware that there is no substitute for experience. However, as I progressed to the HackTheBox challenge, I was able to utilise the small amount of experience I had in order to develop my own basic enumeration methodology.</p>

<img src="/img/final-submission/enumeration.png" alt="Enumeration">

<h4>3. Apply technical skills to develop, model and/or evaluate design</h4>

<p>As I believe the last learning outcome crosses over, I will discuss this SLO as a continuation of my idea in the previous SLO. Having developed a method of enumerating, I was then able to more effectively identify vulnerabilities in order to begin exploiting them. This process was a very tedious but rewarding one, as it required me to do go down many dead ends and attempt many exploits before finding one that achieved my purpose. This taught me that there are many different ways to achieve the same goal, all of which depend on your approach and past experiences.</p>
<p>Furthermore, I found that the more that I investigated exploits for vulnerable systems, the more I was acutely aware of the dangers they could cause to a business. This enhanced my ability to research and present mitigations to these vulnerabilities. Refer to my Hack The Box writeup for evidence of this.</p>

<img src="/img/final-submission/exploitation.png" alt="Exploitation">

<h4>4. Demonstrate effective collaboration and communication skills</h4>

<p>Throughout the 4 weeks, I was required to present to the class or an individual on multiple occasions. This helped me to solidify my understanding of key concepts and increased my confidence in demonstrating a practical attack to an audience. This was especially true for my presentation with Roger, where I was able to demonstrate a practical attack to someone who had no prior understanding. Although I may not have expressed key concepts as clearly as I could have, I do believe this experience helped me to find simpler ways of explaining things.</p>
<p>As a team, the Bare Minimum Bandits worked very well together when we had to collaborate on either a presentation or a group-based task. We utilised tools such as MS Teams and MS Planner in order keep on track and delegate tasks. I believe these tools were vital for successful presentations, as it meant that we could count on one another due to being able to provide instant progress updates and feedback.</p>

<img src="/img/reflection-week-4/final-presentation-1.png" alt="Final Presentation 1">
<img src="/img/reflection-week-3/Teams-chat.png" alt="MS Teams Chat">

<h4>5. Conduct critical self and peer review and performance evaluation</h4>

<p>I believe that throughout each reflection process, I was conducting a thorough and comprehensive critical self and peer review. The sheer amount of both theoretical and practical knowledge I had to comb over convinced me that I was continually doing well when it came to my actual learnings and engagement with the subject content as a whole. However, as I was consistently in a state of feeling rushed and short of time, I believe that my time management could have been more effective as a whole. As I write this submission, I am pushed for time due to underestimating the sheer amount of content required in this subject.</p>
<p>As for assessing the performance of my peers, I believe that the vast majority of my interactions with fellow students was very positive. When it came to collaborating on a presentation, they were always available to discuss ideas and progress on MS Teams. And when the presentation itself came around, we had delegated well enough that it came together with little practice.</p>

<img src="/img/final-submission/peer-review.png" alt="Peer Review">
