---
title: "Week 4 Reflection"
date: 2019-03-03T22:02:01+11:00
draft: false
image: "/img/unsplash-photos-nehfi_SfqtU.jpg"
thumbnail:
---

<h3>Preface</h3>
<p>Last week’s objective was to gain root access to a public virtual machine. I was successful in this endeavour, as I was able to gain root to the Mr Robot box on tryhackme.com. Following on from this, I’ve decided that this week’s main goal is to own an Active box on hackthebox.eu. This is the logic progression in order to challenge myself, although I believe that this will be a substantial task to undertake as I have only completed the one box so far.</p>

<h3>Reverse Engineering Talk</h3>
<p>On Monday of this week, we had Rubin come and deliver a workshop on reverse engineering. This was quite insightful for me and it was interesting to be able to understand the differences between registers, the stack and the heap. As well as this, we learnt keywords to remember, such as a move or a put in regard to data. It was initially quite overwhelming when we opened the binary files in Binary Ninja, as there were so many files with seemingly random character strings, containers and links. However, once Rubin broke the data and functions down, it was much easier to identifier the if-else statements and recursive loops which are integral to the logic of programming languages.</p>
<p>Below are some screenshots of Binary Ninja of me converting a registry pointer for a variable to a character constant in order to reveal the flag.</p>

<img src="/img/reflection-week-4/reverse-engineering-1.png" alt="Reverse Engineering">
<img src="/img/reflection-week-4/reverse-engineering-2.png" alt="Reverse Engineering">

<h3>HackTheBox – Access</h3>
<p>As part of our weekly sprint and final submission, we had to undertake to own an Active box on HackTheBox.eu. This proved to be a massive challenge to me and, as of the time of writing this, I still only have user level access and I am struggling to privilege escalate in order to gain root access. This has been very challenging due to the fact that it is a Windows box and lot of the cmd and PowerShell commands I am unfamiliar with. It was relatively easy to gain user by unlocking a zipped file downloaded by the FTP server. However, when using Metasploit and other exploits to gain a reverse PowerShell, the server which I had initialized and attempt to pull the reverse shell file down from was not allow connections. I believe this may have been due to the network traffic that was slowing connections down, as telnet is very slow as it is. EDIT: Since writing this, I have since spent more time with the challenge and have gained root access.</p>
<p>See my sprint submission uploaded on UTSOnline for a full report with artefacts.</p>

<h3>Final Presentation</h3>
<p>On Friday of this week, we had our final presentation day on where members of all the studio classes, along with staff and members of industry gathered together to recognise the work that had been achieved. It was a great atmosphere, seeing all the students in one room ready to show off all their hard work over the last month. It was interesting talking to Luke about his Wi-Fi jammer and rubber ducky and how easily they can be used to perform very malicious activities. It made something that was quite conceptual to me at the beginning of this course very tangible and real, giving me a greater sense of the harm that it can cause.</p>
<p>I decided to setup on the same table as Mitch for my presentation. Although we only had one faculty member approach us, it turned out to be Roger and was quite a positive experience. Mitch conducted his presentation first, which was quite broad and covered all of his experiences during the studio from developing the static website to owning Active HackTheBoxes such as Curling. Afterwards, I did my presentation which was more specific and showed the different elements involved in owning the Mr Robot box. This involved enumeration, Metasploit exploits, dictionary attacks and priv esc. Although this was quite in-depth and potentially overwhelming for Roger, I believe Mitch and I complimented each other with the two different approaches to our presentations. Looking back, there was quite a good dynamic between us, and we acknowledged that at the end of our presentations. </p>
<p>Although time management continued to be an issue for me this week, I am satisfied with the effort I have put in and the results of my performance.</p>

<img src="/img/reflection-week-4/final-presentation-1.png" alt="Final Presentation 1">
<img src="/img/reflection-week-4/final-presentation-2.png" alt="Final Presentation 2">
