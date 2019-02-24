---
title: "Week 3 Reflection"
date: 2019-02-24T22:02:01+11:00
draft: false
image: "/img/unsplash-photos-nehfi_SfqtU.jpg"
thumbnail:
---

<h3>Preface</h3>
<p>In the previous week, we were predominately looking at web application vulnerabilities, exploits and attacks. Specifically, I decided to focus on XSS as the attack I wished to understand in full and perform against a web application. I was ultimately successfully in this endeavour, as I learnt a lot about XSS from a combination of Luke’s talk, practical examples and by attempting stored XSS challenges on root-me myself.</p>
<p>This week was quite a bit different. We were required to attack a virtual machine (or box) in order to gain root permission, also known as ownership. This posed to be quite a challenge as it required me to overcome a steep learning curve and achieve something I’d never attempt before; that is, utilising and stringing together many different attacks to exploit a vulnerable system. As we are encouraged to constantly refine our objectives or problem statement, achieving this feat will be my goal. </p>

<h3>Presentation on Wireshark and Cyberchef</h3>
<p>We were required to present on Wednesday (20/02/19) about some of the tools used for performing enumeration or attacks. For our presentation, we decided to look at the packet analyser tool Wireshark and the multi-operation tool Cyberchef. Having already used Wireshark in networking and security subjects before, I was fairly familiar with it. However, since working on a web API at my work, I was now aware of something I would not have picked up on previously within Wireshark. I had to demonstrate both of these tools in a pico2017 challenge, and whilst doing this, I was able to recognise specific information within one of the packets that helped me identify that it was the one I was looking for. Firstly, the content-type parameter immediately told me it was an API call. As it was a POST request with query parameters, it was safe to say that the user would be posting some confidential data, such as a username and password. This realisation helped me to bridge the gap between academic learnings and the knowledge that I had accumulated at work.</p>

<img src="/img/reflection-week-3/Presentation1.png" alt="Presentation">
<img src="/img/reflection-week-3/Presentation2.png" alt="Presentation">
<img src="/img/reflection-week-3/Presentation3.png" alt="Presentation">
<img src="/img/reflection-week-3/Presentation4.png" alt="Presentation">

<h3>Deloitte Presentation</h3>
<p>On Wednesday (20/02/19), we have the privilege of being visited by members of the penetration testing team at Deloitte. This was very insightful for me, as it dramatically changed my perspective of who a penetration tester actually was. As Viren mentioned, they are not top-secret hackers who are anonymous and lurk in the shadows. Rather, they are customer facing professionals who consult with other companies whilst also performing both physical and cyber penetration testing. The tests that these guys conduct are very specific in nature and have a limited scope; they are only testing one part of security.</p>
<p>A lot of their job as a pentester requires them to adopt a certain red teaming mindset, which was referenced in Luke’s talk back in week 1. This means that the scenarios are designed to mimic realistic attacks, carried out by realistic adversaries. As part of their presentation, the people at Deloitte gave us access to one of their virtual machines, or boxes. Having never attempt a box before, this was quite daunting due to my lack of experience. Receiving help from other students and getting hints from Deloitte members helped to start to enumerate possible exploits. Beyond that, this experience made me realise how much didn’t know and what was required of me if I were to achieve my objective.</p>

<h3>Free-for-alls</h3>
<p>We had our first free-for-all for the week on Monday (18/02/19). The following is what was discussed by Brendan, Jason and me:</p>
<p>Brendan:</p>
<ul>
    <li>Brendan was working on remote code injection (RCE) for a particular challenge. This involved exploiting GREP with a command such as the following ; ls ; in order to escape grep and execute the CLI command. This concept was new to me and having an example gave me a good understanding of how RCE might be achieved and what it would be useful for.</li>
    <li>Brendan wanted to work on getting to Bandit14, which was roughly where I was up to at the time. Furthermore, he was stuck on Natas11 which it appears that many others including me are bottlenecked by. I believe this is probably due to the steep learning curve that Natas11 presents, as it requires you to perform multiple operations, including reversing a string which is XOR encrypted.</li>
</ul>
<p>Jason:</p>
<ul>
    <li>Jason has been working on his reflection.</li>
    <li>He is working on an exploited XVWA web server image. Apparently, it is an extremely vulnerable web application. He is following a walkthrough of this in order to train himself to recognise certain vulnerabilities so that he is able to do it by himself in the future.</li>
    <li>He is also been using Hydra which has proved to be a challenge for him.</li>
</ul>
<p>On Wednesday (20/02/19) we had our 2nd free-for-all discussion. This one was with Oliver, Ian, Andy and me:</p>
<p>Oliver:</P>
<ul>
    <li>When asked what his greatest discover had been this week, he mentioned how interesting he had found using Beef was. I agreed with him, as I had found that demonstration quite engaging and insightful on how many web browser attacks can be performed.</li>
    <li>Oliver was also working on a Dutch VM called Fristileaks. He had said that it was quite easy to get a user but escalating privileges proved to be a challenge. His friend David had sent him a document with some useful commands for achieving this. I feel like this would be quite useful, as I have found it to be quite difficult to enumerate after having user credentials.</li>
</ul>
<p>Ian</p>
<ul>
    <li>Ian has been working on the APointB website and believes he has found some interesting things. He has found that the website using Wordpress and thinks that there might be an XSS vulnerability on the login page.</li>
    <li>He did Hack the Box Curling. He recommends to try that one as it is fairly beginner friendly. It starts off with Natas 1 and 2. He got root on that machine. However, he got into some rabbit holes and tried things that he thought should work but obviously didn’t. Looking back on my experiences, I can empathize with that and understand that it’s good to start looking down other paths earlier on. </li>
</ul>

<img src="/img/reflection-week-3/Collab.png" alt="Collaboration">

<h3>Team work and Collaboration</h3>
<p>Last week, I mentioned that I did not have a whole of collaboration with my team mates The Bare Minimum Bandits. This week, as we worked on the presentation together, we had a lot more involvement and collaboration with each other. We worked well as a team and were able to allocate tasks fairly and with an even amount of workload. This was achieved by some of us undertaking to do the demo, whilst other members researched and presented their findings. Overall, I’m satisfied with how we worked as a team in order to spread out the load evenly.</p>

<img src="/img/reflection-week-3/Teams-chat.png" alt="Teams Chat">
<img src="/img/reflection-week-3/Teams-planner.png" alt="Teams Planner">

<h3>Tryhackme Mr Robot – Writeup</h3>
<p>Firstly, I ran ifconfig to see that the point-to-point VPN connection was up. I then have to enumerate some vulnerabilities in order to find potentially exploits. I run nmap -Pn -sV to see which ports are open for the host.</p>

<img src="/img/reflection-week-3/writeup1.png" alt="writeup 1">

<p>As it turns out, port 80 http is open which means that there is likely a website running on the host. It turns out there is, and it is a terminal looking application. I try /files which does not give me a directory, but gives me a Wordpress page not found.</p>

<img src="/img/reflection-week-3/writeup2.png" alt="writeup 2">

<p>I then perform a nmap -sV <"ip address"> to enumerate some possible vulnerabilities. This provides me with some interesting possibilities. The first is that there is a /robots.txt file which I have learn often is a good place to start for useful information. The second is that I can confirm that it is a Wordpress site which has an admin login /wp-login.php.</p>

<img src="/img/reflection-week-3/writeup3.png" alt="writeup 3">

<p>By going to robots.txt, I am able to find the first secret inside key-1-of-3.txt. There is also a file fsocity.dic which I am not sure how to use at this stage.</p>

<img src="/img/reflection-week-3/writeup4.png" alt="writeup 4">

<p>As I am familiar with wpscan from Darsh’s tutorial on Monday, I decide to perform a scan.</p>

<img src="/img/reflection-week-3/writeup5.png" alt="writeup 5">

<p>The results of the scan tell me that there are 57 vulnerabilities. However, spending some time looking for exploits for these vulnerabilities, including a SQL Injection attack for Simple:Press  4.3.0 plugin on ExploitDB, proves to be a fruitless endevour.</p>
<p>After looking at the help for wpscan, my next attempt is to perform a dictionary attack on the admin login. I initially try doing this using an inbuilt dictionary, before realising one is provided in fsocity.dic. I perform the attack and wait 45 minutes before cancelling as it has only progressed 0.25%.</p>

<img src="/img/reflection-week-3/writeup6.png" alt="writeup 6">
<img src="/img/reflection-week-3/writeup7.png" alt="writeup 7">

<p>I decide I have to find another method, as this approach may way work, but would take many hours to complete. As I know Jason has used Hyrdra before, I decide to get his help to perform this attack with no success.</p>
<p>I then receive a hint from a fellow student suggesting that there might be duplicate rows within the dictionary file. With that, I perform a sort for all unique rows.</p>

<img src="/img/reflection-week-3/writeup8.png" alt="writeup 8">
<img src="/img/reflection-week-3/writeup9.png" alt="writeup 9">

<p>The dictionary is now only 9 words long, and I use this to successfully gain the password. I use this password to access the Wordpress console through the admin login page. I now need to start a reverse shell somehow. I try install malicious Wordpress themes and plugins in order to exploit vulnerabilities for the specific version of Wordpress, however none of these attempts succeed. I then attempt to use a Metasploit Wordpress exploit. Initially, I faced difficulties due to certain exceptions being thrown and stopping the attack. After some research, I found out that by commenting out 2 of these failure messages, the attack would succeed.</p>

<img src="/img/reflection-week-3/writeup10.png" alt="writeup 10">
<img src="/img/reflection-week-3/writeup11.png" alt="writeup 11">

<p>I was then able to launch a reverse shell to gain base level access to the machine. Changing directories to /usr/robot/ I found the 2nd key file along with another password file. I did not have permission for the key file, but I was able to cat the password.raw-md5 file. I attempted to use Cyberchef to reverse the md5 hash with no success. After some research, I came across hashcat and the rockyou dictionary. Using this combination allowed me to reverse the md5 hash and get the plaintext password.</p>

<img src="/img/reflection-week-3/writeup12.png" alt="writeup 12">
<img src="/img/reflection-week-3/writeup13.png" alt="writeup 13">

<p>I was then able to login as a superuser with su robot and providing the plaintext password.</p>

<img src="/img/reflection-week-3/writeup14.png" alt="writeup 14">

<p>I was then able to cat the 2nd key and enter this into tryhackme.com.</p>

<img src="/img/reflection-week-3/writeup15.png" alt="writeup 15">

<p>I now needed to priv esc to achieve root permissions. I knew that Jai had spoken about some priv esc checker tools, such as a Linenum Script which would indicate which programs may run as root without a password, and therefore are vulnerable. I tried to download multiple Github repos through the shell, however they ultimately all timed out when downloading. My next attempt was to use the unix-privesc-check tool built into Kali Linux. I quickly realised that there would be no way to use that through the shell.</p>

<img src="/img/reflection-week-3/writeup16.png" alt="writeup 16">

<p>After a fair amount of research and looking at priv esc walkthroughs, I came across a command that indicates applications which run as root.</p>

<img src="/img/reflection-week-3/writeup17.png" alt="writeup 17">

<p>One of these was nmap v3.81. After some research, I found a priv esc exploit for this nmap version and successfully performed this attack using the nmap repl (or interactive) to gain root access.</p>

<img src="/img/reflection-week-3/writeup18.png" alt="writeup 18">

<p>I then went to the root folder to find the 3rd and last key.</p>

<img src="/img/reflection-week-3/writeup19.png" alt="writeup 19">

<p>As I look back on this experience, it was just as challenging and time consuming as I had assumed. It made me understand that there is no substitute for the time and effort that must be put in, in order to successfully gain root access. As discussed many times during this subject, enumeration is often a lengthy process that leads to many dead ends and rabbit holes. I can attest to that with the Wordpress vulnerabilities that I tried to find and exploit with no success. Fortunately, I did not waste too much time with these after a few failed attempts and was able to find another means through Metasploit. This box has given me a much clearer understanding of the typical paths to take when gaining root access and what to look out for.</p>
