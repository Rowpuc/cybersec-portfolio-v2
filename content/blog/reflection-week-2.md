---
title: "Week 2 Reflection"
date: 2019-02-17T22:02:01+11:00
draft: false
image: "/img/unsplash-photos-nehfi_SfqtU.jpg"
thumbnail:
---

<h3>Preface</h3>
<p>Before I get into the specifics and technical details of the work that have been undertaking over the course of week 2, I would first like to review what my objectives were in week 1 and how they have since changed.</p>

<p>In my first reflection, I stated that:</p>

<p style="font-style: italic;">“My objectives are to be able to perform basic attacks on web sites in a CTF environment as well as on virtual machines. This will give me a better understanding and perspective from the red team (the attacker), which from what I understand is vital in adopting the mindset of defending against such attacks. Using this knowledge and renewed perspective, I wish to improve my ability to defend against common vulnerabilities and attacks that exist in web applications.”.</p>

<p>This past week we have predominately looked at web app vulnerabilities, exploits and attacks. (As a slight tangent, I had to refresh my knowledge of these concepts over the week; exploiting is turning a vulnerability (or weakness) into a way to attack (or breach) a system (Ethical Hacker 2012).) This opportunity to increase my knowledge and skills with web app attacks has taught me a few things. The first being how to conduct and execute a basic stored XSS attack, which are one of the most common types of XSS. The second is the actual theory behind how these attacks work and why they are so malicious and effective. And lastly, why XSS are still so prevalent amongst web applications and remain at number 3 in the OWASP Top 10 Security Exploits.</p>

<p>Having said this, I have inadvertently realised that the initial scope of my objectives for this week has shrunk to focus on XSS, in particular stored XSS. Looking back on initial scope, it was very broad, and it would seem to be only natural that I would start pursing specific areas of web app that are common and still relevant. Additionally, having just deployed a web application into production for the first time, I am now very aware of the vulnerabilities that may be present and the difficulty in which they can be exploited. In the coming weeks it may be possible to do further research and perform XSS attacks on the development platform of this site in order to identify any weaknesses. This would all have to be subject to the approval of work obviously.</p>

<h3>Ethical Hacking and Bug Bounties</h3>
<p>As part of our research deliverable due on Wednesday (13/02/19) which can be found <a href="https://www.rjpuc.me/blog/ethical-hacking-and-bug-bounties/">here</a>, we had to research the ways in which bug bounty programs affect different stakeholders.</p>

<img src="/img/reflection-week-2/ethical-hacking.png" alt="Ethical hacking blog post">

<p>What I learnt through this process of research was quite eye opening to me. I was aware that in the traditional software development lifecycle, testing is always the stage which is conducted the least thoroughly and often skipped altogether. Enter Bug Bounties. Bug bounties provide a regulated and controlled marketplace platform for white hat hackers to identify and report on exploits for a monetary reward. With this relatively new phenomenon, companies are now adopting the mindset that that no system is invulnerable, and therefore will always have bugs. This can make companies slightly apathetic towards thoroughly testing before release, and they will instead release applications with the idea of patching after launch. Reflecting on this has made me aware of the drastically changing landscape of IT industry, in which companies are now welcoming the submission of bug reports. This is something that not too long-ago companies would have been dismissive or even apathetic towards.</p>

<h3>The XSS Problem Statement</h3>
<p>Our deliverable for Friday (15/02/19) was to define a problem statement and demonstrate a practical attack on an exploit which shows that this problem statement was explored.</p>
<p>In my case the problem statement was:</p>

<p style="font-style: italic;">“If relatively simple attacks such as XSS and CSRF are still in the OWASP Top 10, why do they still pose such a threat to businesses?”</p>

<p>As part of my demonstration, I thought it would be necessary to perform a simple XSS attack. The particular attack which I conducted was a Stored XSS attack provided by root-me (https://www.root-me.org/en/Challenges/Web-Client/XSS-Stored-1).</p>

<p>Stored XSS, often called second order XSS, is the most dangerous type of Cross-site scripting according to OWASP. This is because many applications allow users to store data on their site, and if this data is not sanitised or filtered correctly, the malicious data will appear to be part of the web site and run within the user’s browser under the privileges of the web app.
https://www.owasp.org/index.php/Testing_for_Stored_Cross_site_scripting_(OTG-INPVAL-002)</p>

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
