---
title: "Week 1 Reflection"
date: 2019-02-11T11:28:01+11:00
draft: false
image: "/img/unsplash-photos-nehfi_SfqtU.jpg"
thumbnail: /img/rowan.png
---

<h1>Introduction and Learning Contract</h1>
<img src="/img/rowan.png" style="float:left;width:250px;height:250px;padding:10px" alt="Rowan">
<p>Hi, my name is Rowan Puckeridge. I am in my fourth year of my undergraduate bachelor’s degree in Science in Information Technology, majoring in Internetworking and Applications. As someone who is currently working as a Web Systems Developer at a startup company, I recognize the criticality and importance of protecting an application against a range of vulnerabilities that can be exploited through different attacks. This includes SQL injection, XSS attacks and many others. This is especially true in financially applications which deal with large sums of money where the CIA trifecta of security is of upmost importance.</p>
<p>With this being said, my motivation for taking this subject is to predominately expand my knowledge in the realm of web system security and to learn how to mitigate the risks of well-known attacks. My objectives are to be able to perform basic attacks on web sites in a CTF environment as well as on virtual machines. This will give me a better understanding and perspective from the red team (the attacker), which from what I understand is vital in adopting the mindset of defending against such attacks. Using this knowledge and renewed perspective, I wish to improve my ability to defend against common vulnerabilities and attacks that exist in web applications.</p>
<h2>SLO 1: Engage with stakeholders to identify a problem</h2>
<p>On Tuesday the 06/02/19, we had the privilege of listening to Robert from GitLab give a presentation on his experiences in the cyber security industry and its evolution from hobbyists to a profession consisting of security engineers, consultants and both ethical and unethical hackers. As part of his presentation, Robert mentioned businesses often have to way-up the resources and finances required to mitigate a security vulnerability verses the impact that would be caused if the vulnerability wasn’t resolved and the attack actually happened. Based on this topic, I asked Robert a question about whether businesses were not only willing to accept financial risk, but also the risk of being non-compliant with certain regulations. The question is as follows:</p>
<p>“When a business decides to accept the risk involved with a security vulnerability instead of attempting to resolve or mitigate it, can the risk also include regulatory risk where the business may no longer comply with industry regulations and therefore lose their accreditation?”.</p>
<p>Robert simply responded that yes, some unethical decision makers within an organisation may make the choice to accept the risk for being in breach of their industry’s regulations if a particular known vulnerability to their system’s or premises’ physical or network security is not resolved. Looking back on this response, I am quite surprised by the sheer number of vulnerabilities that business’ face to both their physical, network and cyber security. Furthermore, I am now more aware of the complex decisions that have to be made by the key decision makers of businesses and the financial and regulatory consequences that occur when the risks of a vulnerabilities or vector are not reasonably considered.</p>
<p>Based on this verbal feedback received from Robert, I decided to investigate further into why key decision makers of businesses would deliberately make the decision to risk being non-compliant.
https://www.cio.com/article/2386558/data-protection/compliance-vs--risk-in-enterprise-security.html</p>

<h2>SLO 2: Apply design thinking to respond to a defined or newly identified problem</h2>
<p>As part of the CTF (Capture the Flag) challenge released on Friday (08/02/19), we were given free roam to explore and apply multiple attack vectors to gain access or cause unexpected/unauthorised behaviour to the OWASP Juice Shop provided at this address: https://juice-shop-uts.herokuapp.com/.</p>
<p>One of the well-known attacks vectors I decided to attempt on the CTF site was an SQL injection. The reason I was able to identify this vulnerability was due to the fact that the site had login functionality, and therefore would have to compare the username and password combination against a database. There was a good chance that the database which was being used by the web app was a SQL database, and therefore the site would vulnerability to an SQL injection if the input was not properly sanitised using parameterised queries.</p>
<p>With the help from an article on bypassing logins using SQL injection, I was able to successfully perform an SQL injection in order to login as an admin: http://www.securityidiots.com/Web-Pentest/SQL-Injection/bypass-login-using-sql-injection.html.</p>
<ol>
    <li>
    Firstly, I went to the Login in page of the Juice Shop.
    </li>
    <li>
    I made the assumption that the site would be using an SQL database engine of some kind and would we vulnerable to an SQL injection due to non-sanitised SQL parameters.
    </li>
    <li>
    I also made the assumption that the query that the app was using would look something like this: $query="select username, pass from users where username='$username and password='$password’";
    </li>
    <li>
    With this in mind, I used in a single quotation to close the username parameter string and then added OR 1 = 1;. This ensures that the condition of the query is always true, and therefore, allowing me to bypass the login.
    </li>
</ol>
<p>The feedback I received from Larry whilst attempting to complete this challenge was that the SQL injection was simpler than I was initially attempting. This allowed me to rethink the way I was approaching the problem and go back to the basics of what I knew about SQL conditions and parameters.</p>
 
<img src="/img/juiceShopLogin.png"> 
<img src="/img/juiceShopProfile.png">
<img src="/img/juiceShopSuccess.png">   
 
<h2>SLO 3: Apply technical skills to develop, model and/or evaluate design</h2>
<p>One of our main assignments for week 1 was to conduct research into a particular area of cyber security, whether that be a vulnerability or exploit that was found or an attack vector which was executed. Our team decided to research a recent DDoS attack which was performed against a client of Imperva, a well know cyber security company which provides security products. This particular DDoS attack relied on exploiting the TCP protocol, specifically a TCP 3-way handshake, by executing a SYN Flood attack.</p>
<p>Through this research, we discovered that there were two main attack vectors used when impacting the availability of a site or server; a high bandwidth attack and a high PPS (packets per second) attack. Each of these attack vectors uses a different tool set and affects the server different, whilst providing the same end result. A high bandwidth attack uses a relatively low number of packets consisting of a large packet load, whilst a high PPS attack uses a large number of packets which are relatively small. As such, the mitigation techniques involve applying a high capacity network backbone or utilizing high performance routers and switches, respective to the attack which is attempting to be mitigated.</p>
<p>I received positive one-on-one feedback regarding my research and contribution to this presentation by Larry. Although he was pleased with my presentation style and my apparent knowledge of the content, he alerted me to the fact that my presentation time went for roughly 7 minutes. As this was over the total time allowed for the presentation, I will make an intentional effort in the future to time my speaking in order to cut down my presentation time to meet what is expected.</p>

<table style="borderColor:none;">
    <tr>
        <td>
            <img src="/img/slide1.png">
        </td>
        <td>
            <img src="/img/slide2.png">
        </td>
    </tr>
    <tr>
        <td>
            <img src="/img/slide3.png">
        </td>
        <td>
            <img src="/img/slide4.png">    
        </td>
    </tr>
</table>

<a href="{{ .Page.Site.BaseUrl }}/{{ (.Resources.GetMatch "mylogo.png").Content | base64Encode }}"/>

<h2>SLO 4: Demonstrate effective collaboration and communication skills</h2>
<p>Through the presentation referenced above, I was able to demonstrate that I can clearly communicate the key impacts and consequences of security vulnerabilities and potential threats to an audience. In this case, the potential threats to a system is a DDoS SYN flood attack and the impact is negatively affecting the availability of the server or network. The audience that I delivered to was our class. As previously mentioned, my feedback for the presentation was the I went over my allocated time. Therefore, I will need to make an intentional effort to be my concise in the delivery of my content in order to more effectively communicate key points.</p>
<p>Our presentation required us to effectively collaborate and communicate in order to research, prepare and deliver our presentation successfully. This involved utilizing Microsoft Teams chat as well as Microsoft Planner to organize our research as well as who would be presenting which section. As seen below, I believe that our team was quite proactive at communicating what needed to be done in terms of both delegating research and presentation delivery. In retrospect, it would have been desirable to have decided who was undertaking which section during class, as this would have been much more effective than attempting to do this via chat. Moving forward, I will attempt to make a more intentional effort to have key discussions and decisions made whilst we are together in class for group assignments such as these.</p>

<img src="/img/chat1.png">
<img src="/img/chat2.png">
<img src="/img/chat3.png">
<img src="/img/task1.png">

<p>On the Friday of Week 1 (08/02/19), we conducted our first stand up meeting as a group where we gave the milestones and challenges we’d encountered over the past week. As someone who had been working full time as a developer with a project due this week, it had been quite a challenge to manage my time efficiently. I found it difficult to prioritize university work alongside my project, and often found that I struggle to switch my headspace and be efficient at what I was working towards. As a side effect, I did not achieve as much as I’d hope for as part of my static website. However, I did manage to setup a domain name (rjpuc.me) through NameCheap, as well as create and host a Hugo.io site through Netify.com. This involved setting up the DNS servers, as is evinced through the following artefacts.</p>

<img src="/img/netlify1.png" style="max-width:500px;max-height:500px;">
<img src="/img/netlify2.png" style="max-width:500px;max-height:500px;"> 
<img src="/img/hugoSite.png">

<h2>SLO 5: Conduct: Critical self and peer review and performance evaluation</h2>
<table>
    <tr>
        <td>
        Group Reflection sheet
        </td>
    </tr>
    <tr>
        <td>
        Group name: Bare Minimum Bandits
        </td>
    </tr>
    <tr>
        <td>
        Date: 10/02/2019
        </td>
    </tr>
    <tr>
        <td>
        What have we ACHIEVED? – evidence of progress, artefacts created
        </td>
        <td>
        What have we LEARNED? What do we need to Learn?
        </td>
        <td>
        What do we need to do NEXT? collectively – both students and staff
        </td>
    </tr>
    <tr>
        <td>
        As a group, we have achieved a substantial amount of research into DDoS attacks, more specifically SYN Flood attacks. This research gave us better insight into not only the technical process behind the attack, but also the different attack vectors that can be applied and the impact that they can cause. Furthermore, we created a PowerPoint presentation which was delivered during Week 1 which demonstrates our ability to operate as a coordinated group in order to take a concept and turn it into something tangible. The artefacts of these achievements are evinced by the presentation slides and research dialog over MS teams which is displayed above in SLO 4.
        </td>
        <td>
        Apart from the knowledge we have gained from our case study research, I believe we have come to understand a fair bit about each other and how we work together as a whole. It has been very interesting to learn about both Corey and Chris’ journey with the Cyber Security society so far and the competitions they have been involved with. Additionally, it has been eye-opening to talk with Junwei, particularly about his background and overcoming his challenges when moving to Australia.
        I believe that as a team, we need to continue to learn more about how we operate individually, as well as to learn from the technical knowledge and experience that each of us have developed from both uni and professional work environments. 
        </td>
        <td>
        For me personally, I believe that in order to succeed and make the most out of this subject, I must learn to push myself as much as I can to learn from failing as well as from other class members. This may resonate with other students in the class as well.
        Additionally, I now know the challenges I will face in balancing both uni and work projects. This will require to plan ahead and use my time efficiently in order to be successful in both of these endevours.
        </td>
    </tr>
</table>
