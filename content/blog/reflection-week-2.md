---
title: "Week 2 Reflection"
date: 2019-02-17T22:02:01+11:00
draft: false
image: "/img/unsplash-photos-nehfi_SfqtU.jpg"
thumbnail:
---

<h3>Preface</h3>
<p>Before I get into the specifics and technical details of the work that I have been undertaking over the course of week 2, I would first like to review what my objectives were in week 1 and how they have since changed.</p>

<p>In my first reflection, I stated that:</p>

<p style="font-style: italic;">“My objectives are to be able to perform basic attacks on web sites in a CTF environment as well as on virtual machines. This will give me a better understanding and perspective from the red team (the attacker), which from what I understand is vital in adopting the mindset of defending against such attacks. Using this knowledge and renewed perspective, I wish to improve my ability to defend against common vulnerabilities and attacks that exist in web applications.”.</p>

<p>This past week we have predominately looked at web app vulnerabilities, exploits and attacks. As a slight tangent, I had to refresh my knowledge of these concepts over the week; exploiting is turning a vulnerability (or weakness) into a way to attack (or breach) a system (Ethical Hacker 2012). This opportunity to increase my knowledge and skills with web app attacks has taught me a few main things. The first being how to conduct and execute a basic stored XSS attack, which are one of the most common types of XSS. The second is the actual theory behind how these attacks work and why they are so malicious and effective. And lastly, why XSS attacks are still so prevalent amongst web applications and remain at number 3 in the OWASP Top 10 Security Exploits.</p>

<p>Having said this, I have inadvertently realised that the initial scope of my objectives for this week has shrunk to focus on XSS, in particular stored XSS. Looking back on the initial scope, it was very broad and it would seem to be only natural that I would start pursing specific areas of web app security that are common and still relevant. Additionally, having just deployed a web application into production for the first time at my work, I am now very aware of the vulnerabilities that may be present and the difficulty in which they can be exploited. In the coming weeks it may be possible to do further research and perform XSS attacks on the development platform of this site in order to identify any weaknesses. This would all have to be subject to the approval of work obviously.</p>

<h3>Ethical Hacking and Bug Bounties</h3>
<p>As part of our research deliverable due on Wednesday (13/02/19) which can be found <a href="https://www.rjpuc.me/blog/ethical-hacking-and-bug-bounties/">here</a>, we had to research the ways in which bug bounty programs affect different stakeholders.</p>

<img src="/img/reflection-week-2/ethical-hacking.png" alt="Ethical hacking blog post">

<p>What I learnt through this process of research was quite eye opening to me. I was aware that in the traditional software development lifecycle, testing is always the stage which is conducted the least thoroughly and often skipped altogether. Enter Bug Bounties. Bug bounties provide a regulated and controlled marketplace platform for white hat hackers to identify and report on exploits for a monetary reward. With this relatively new phenomenon, companies are now adopting the mindset that no system is invulnerable, and therefore will always have bugs. This can make companies slightly apathetic towards thoroughly testing before release, and they will instead release applications with the idea of patching after launch. Reflecting on this has made me aware of the drastically changing landscape of IT industry, in which companies are now welcoming the submission of bug reports. This is something that not too long-ago companies would have been dismissive or even hostile towards.</p>

<h3>Luke’s XSS Talk</h3>
<p>On Wednesday (13/02/19), we had a talk on XSS by Luke. This was very insightful to me, as it gave me an understanding of the criticality of XSS vulnerabilities and why they are the number one exploit on the web.</p>

<p>Luke also drew up a simple diagram of how the 3 types of XSS attacks are performed, as seen in the image below. I’d predominately covered stored XSS this week, so I was able to gain better understanding of how this attack worked in a practical sense. In essence there are 2 requests to the application server for this attack to work. The first is the saving of the information on the server’s database. The second is getting someone to execute that information to perform the attack and gain some information.</p>

<p>As it says on the diagram: “Attack is performed on anyone accessing the database. Can be very bad if an admin visits this infected DB i.e. admin cred’s lifted”. Having since completed a stored XSS attack where I lifted the admin’s cookie, I now have the practical knowledge of how this might come about. This talk was very useful in providing me with the theory necessary to understand the attack properly. Going forward, it would be good to attempt challenges involving the other 2 types of XSS in order to increase my understanding of these attacks.</p>

<img src="/img/reflection-week-2/luke-talk.png" alt="Luke's XSS Talk">

<h3>The XSS Problem Statement</h3>
<p>Our deliverable for Friday (15/02/19) was to define a problem statement and demonstrate a practical attack on an exploit which shows that this problem statement was explored.</p>
<p>In my case the problem statement was:</p>

<p style="font-style: italic;">“If relatively simple attacks such as XSS and CSRF are still in the OWASP Top 10, why do they still pose such a threat to businesses?”</p>

<p>As part of my demonstration, I thought it would be necessary to perform a simple XSS attack. The particular attack which I conducted was a Stored XSS attack provided by <a href="https://www.root-me.org/en/Challenges/Web-Client/XSS-Stored-1">root-me</a>.</p>

<p>Stored XSS, often called second order XSS, is the most dangerous type of Cross-site scripting according to OWASP. This is because many applications allow users to store data on their site, and if this data is not sanitised or filtered correctly, the malicious data will appear to be part of the web site and run within the user’s browser under the privileges of the web app.</p>

<p>As this is a stored XSS attack, we need some way of injecting the XSS through an input, in this case a textbox. It appears someone (the admin) is deleteing old messages, so we can hope that the injected JavaScript will run when they view the message This will hopefully steal or lift their cookie and send it to the supplied Request Bin URL. I will be using a Request Bin URL in order to collect requests that are made to the URL and this will be wrapped in an image tag. When the image is clicked, a request to the URL is made with the admin’s cookie. We can then look at Request Bin site linked to the URL to find the stolen cookie.</p>

<p>This attack would potentially allow us to login as the admin using their cookie, successfully escelating the privileges of the web app.</p>

<p>Firstly, I typed in a Javascript snippet into the textarea. This snippet just writes an image to the DOM (or Document Object Model) which has the Request Bin URL embedded into it. I then pressed sent.</p>

<img src="/img/reflection-week-2/xss-1.png" alt="XSS-1">

<p>The message has now been submitted. We can see the broken image icon displayed at the bottom, as the URL does not point to an actual image. Now when the admin clicks on the image out of curiousity, a request will be sent to the Request Bin URL containing the admin’s cookie.</p>

<img src="/img/reflection-week-2/xss-2.png" alt="XSS-2">

<p>After a few minutes, when we go to the Request Bin link and see the collected requested with the ADMIN_COOKIE. Theoretically, we now have the ability to access the web app with elevated privileges.</p>

<img src="/img/reflection-week-2/xss-3.png" alt="XSS-3">
<img src="/img/reflection-week-2/xss-4.png" alt="XSS-4">

<p>Completeting this challenge gave me a much greater sense of how easy an XSS attack could be performed if the proper vulnerabilities are not resolved. So many web apps these days are more than just displaying content, but allow the user to interact with it in a very powerful way. The more opportunties there are for the user to post or submit something to the database, the higher the risk of XSS vulnerabilities. Furthermore, this challenge has helped me to identify the two stages of a stored XSS attack; the script injection by the attacker and the URL hit by the victim.</p>

<p>You can find my presentation on The XSS Issue <a href="/img/reflection-week-2/The XSS Issue.pptx">here</a>.</p>

<h3>Receiving and Giving Static Site Assistance</h3>
<p>I mentioned previously in my week 1 reflection that I was having difficulties setting up my static site using Netlify and Github with a Name Cheap domain name. As you can see, I have now resolved those issues and my site is live using a custom domain. Junwei encountered a similar issue this week where he could deploy the site using a generic Netlify domain but was unable to deploy it on his custom domain. With my limited experience with Netlify, I was able to remove and re-add the CName containing the custom domain to get his site to deploy properly.</p>

<p>This experience gave me confidence using Netlify, as I find that teaching someone else gives me a better understanding of the tool myself.</p>

<img src="/img/reflection-week-2/netlify.png" alt="Netlify">

<h3>Over the Wire - Bandit</h3>
<p>As part of our homework, we were required to undertake the Bandit challenges from Over the Wire to about level 30. I was only able to get up to level 15 due to the increasing time and commands required for each challenge. This can be seen in the following image which shows the commands I used for level 12. Level 12 was quite complicated, requiring me to find out the type of file I was dealing with before using the appropriate decoding or decompression tool. A lot of this involved trial and error, looking up man pages and searching the web for hints. It has made me realise the time involved to perform even simple CLI commands to get a hidden secret. Moving forward, it is important that I don’t underestimate how long challenges may take and the research involved with it.</p>

<img src="/img/reflection-week-2/bandit12.png" alt="Bandit12">

<h3>Over the Wire – Natas</h3>
<p>Another homework task that I was assigned was the Natas challenges provided on Over the Wire. For the most part, I found the early challenges quite straightforward. One of the challenges, however, required that I change the Referrer URL in order to get the secret. I decided to use Burp Suite for this task, which I had used once before. I managed to configure Firefox to use the Burp Suite proxy, as seen below.</p>

<img src="/img/reflection-week-2/firefox-config.png" alt="Firefox Network Config">

<p>However, when I went to the Natas page, I realised that it would get stuck when loading. What I eventually discovered, was that the intercept toggle on the Proxy is enabled by default, meaning that the network packet for the site was frozen until forwarded on. This led me to understand how the proxy worked in a more practical sense, and I was able to add the Referrer and forward the packet to complete the challenge. I would like to increase my knowledge of Burp Suite in the coming weeks, having only touched the Proxy and an add on for a CSRF generator.</p>

<img src="/img/reflection-week-2/burp-suite.png" alt="Burp Suite">

<h3>Communication, Scrums and Free-for-Alls</h3>
<p>This week I felt as if I had the opportunity to branch out to talk and work with other students in the class who I didn’t have much contact with previously. On Friday (15/02/19), I participated in a free-for-all with Mitch, Max and Andrea. The following are some of the areas we discussed in reference to the questions in the PowerPoint slides:</p>
<ul>
    <li><b>Mitch</b> – He completed the Pen testers lab for XSS and SQL Injection. He did well with the XSS section, however, he struggled with the SQL injection. This was partially due to a lack of understanding about how he would be able to comment out the end of an SQL statement. This allowed the rest of the group the chance to provide ideas of how this might be achieved.</li>
    <li><b>Max</b> – He was attempting to complete some of the Hack the Box challenges as he was at a more advanced skill level already.</li>
    <li><b>Andrea</b> – He previously had some difficulty with his static sight, mainly trying to stop the navigation bar from closing automatically when in mobile mode.</li>
</ul>
<p>I found free-for-alls much more useful then stand-ups. I believe this is due to them being more personal, as it allows you to question others beyond the standard responses you might hear in a stand up. Furthermore, they are more engaging than someone talking vaguely to no one in particular. I believe that stand ups would be more effective with a smaller group of students.</p>

<p>As for our assigned group, the Bare Minimum Bandits, we did not have nearly as much collaboration or sharing as we did last week. This is mainly due to us all working on different challenges, whether that be Natas, Hack the Box or others. I do not believe this a particularly bad thing as it gave us all an opportunity to undertake things by ourselves. We still made use of MS Teams and Planner to share vital information and plan assignments, as seen below. I believe we should make better use of these tools over the next couple of weeks to maximise our collaboration and learning.</p>

<img src="/img/reflection-week-2/teams-chat.png" alt="MS Teams Chat">
<img src="/img/reflection-week-2/teams-tasks.png" alt="MS Teams Tasks">

<ol>
    <li>http://www.livehacking.com/2012/11/20/the-difference-between-an-expoit-and-vulnerability/</li>
    <li>https://www.owasp.org/index.php/Testing_for_Stored_Cross_site_scripting_(OTG-INPVAL-002)</li>
</ol>
