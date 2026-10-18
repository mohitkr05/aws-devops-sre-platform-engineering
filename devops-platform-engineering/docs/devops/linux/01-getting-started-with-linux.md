# Getting started with Linux

## What is Linux?

### UNIX

Imagine the time, when computers were massive machines that could fill entire buildings- however, their physical size wasn't the biggest challenge – it was their lack of standardization.

Every computer ran its own unique operating system, making software compatibility a nightmare. Programs written for one machine wouldn't work on another, and expertise with one system didn't transfer to others. Problems were huge, lack of capability and skills, financial impact, immensive training and reinventing the wheel. This made the real cost per unit of computing power astronomical.

While the size issue would persist through the 1970s, a breakthrough came in 1969 when Bell Labs tackled the software compatibility problem. Their solution was UNIX, an operating system built on three revolutionary principles:

First, they prioritized simplicity and elegance in design. Second, they wrote it in the C programming language rather than machine-specific assembly code. Third, and perhaps most importantly, they made the code reusable.

This last feature marked a radical departure from existing systems. Before UNIX, commercial computers ran on custom-written code that worked only on specific hardware. 

UNIX introduced a new approach: a small, hardware-specific core called the kernel, which handled basic system operations, while the rest of the operating system was built around it in C. 

This meant only the kernel needed to be adapted for different machines, while the majority of the system remained consistent across platforms.


### Linux

By the early 1990s, PCs became powerful enough to run UNIX. Linus Torvalds, a computer science student at the University of Helsinki, envisioned creating a free academic version of UNIX and began development.

```
From: torvalds@klaava.Helsinki.FI (Linus Benedict Torvalds)
Newsgroups: comp.os.minix
Subject: Gcc-1.40 and a posix-question
Message-ID: <1991Jul3.100050.9886@klaava.Helsinki.FI>
Date: 3 Jul 91 10:00:50 GMT
Hello netlanders,
Due to a project I'm working on (in minix), I'm interested in the posix
standard definition. Could somebody please point me to a (preferably)
machine-readable format of the latest posix rules? Ftp-sites would be
nice.
```
His goal was full UNIX compatibility, which led him to focus on POSIX compliance - the primary UNIX standard. Despite the lack of plug-and-play technology at the time, enthusiasts eagerly embraced the project.

Two years post-launch, Linux had 12,000 users. While starting as a hobby project, it maintained POSIX compliance and steadily incorporated UNIX features. Linux evolved into a mature operating system suitable for workstations and servers across all performance tiers.

Today, major hardware and software companies maintain dedicated Linux development teams. Pre-installed Linux systems with official support are commercially available, though some hardware and software compatibility gaps remain.


### Open Source

The fundamental principle of Open Source revolves around transparency and collaboration in software development. 

When source code is freely available for anyone to read, modify, and distribute, it creates a powerful ecosystem of continuous improvement. 

This approach stands in stark contrast to proprietary software, where code remains hidden and controlled by a single entity.

The strength of Open Source lies in its community-driven development model. When thousands of developers worldwide can examine code, they can identify and fix bugs, add features, and optimize performance far more effectively than a limited team at a traditional software company. This "many eyes" principle has led to remarkable achievements in software quality and security.

Let's look at some concrete impacts of Open Source:

Linux, as a prime example, now powers approximately 96.3% of the world's top one million web servers. The Android operating system, built on Linux, runs on over 2.5 billion active devices. Nearly all of the world's supercomputers (99.6%) run on Linux, demonstrating its capability to handle the most demanding computing tasks.

The economic impact is equally impressive. Companies save an estimated $60 billion annually by using Open Source software. Major corporations like IBM, Google, and Microsoft have invested billions in Open Source projects, recognizing their strategic importance. The Linux Foundation reports that companies are increasingly prioritizing Open Source expertise when hiring, with over 87% of hiring managers indicating it's a priority.

The collaborative nature of Open Source has accelerated innovation in crucial ways. Take the example of Git, the version control system initially developed for Linux kernel development. It has revolutionized how software is developed, with platforms like GitHub hosting over 200 million repositories and connecting 65 million developers worldwide.

In terms of business adoption, Open Source has evolved from being viewed with skepticism to becoming a cornerstone of modern technology strategy. Companies like Red Hat (acquired by IBM for $34 billion) have built successful business models around Open Source software by providing enterprise-grade support and services. Even traditional proprietary software companies like Microsoft have embraced Open Source, with CEO Satya Nadella famously declaring "Microsoft loves Linux" - a dramatic shift from their previous stance.

The Open Source model has expanded beyond software into other domains like hardware design, scientific research, and educational resources. For instance, the Open Source hardware movement has led to projects like Arduino and Raspberry Pi, which have democratized access to computing and electronics education.

The success of Open Source has validated what academics and technical experts recognized decades ago: that openness and collaboration can drive innovation more effectively than closed, proprietary development. The Internet's growth has been particularly instrumental in demonstrating this, as much of the Internet's infrastructure runs on Open Source software like Apache, Nginx, and Linux.

In today's landscape, Open Source software has matured from its academic roots into a crucial part of the global technology infrastructure. Its influence continues to grow as more organizations recognize the benefits of transparent, collaborative development in creating robust, secure, and innovative solutions.


### Features of Linux


- Linux comes at no monetary cost. It is not only free but users have the freedom to modify, distribute, and study the source code under the GNU Public License (GPL). 
- This license ensures these freedoms remain protected, creating a self-sustaining ecosystem of open development.
- Linux demonstrates remarkable adaptability across computing platforms. 
- From tiny embedded systems to massive supercomputers, Linux can be optimized to run effectively on virtually any hardware architecture. 
- Linux was engineered with continuous operation in mind. The system allows for updates and modifications without requiring restarts, making it ideal for servers and critical systems that need constant uptime. This stability comes from its Unix heritage and careful architectural decisions in its design.
- The operating system offers robust security features comparable to enterprise-grade systems. Its open-source nature means vulnerabilities are quickly identified and patched by the community. 
- Linux can be customized for various purposes, from desktop computing to specialized server applications.
- One of Linux's strongest attributes is its ability to grow with your needs.
- The open development model leads to impressively quick bug resolution. When issues arise, the global community of developers can collaborate to identify and fix problems faster than traditional development cycles allow. This rapid iteration helps maintain system reliability and security.
- While Linux has made significant strides in user-friendliness, it can present a steeper learning curve for newcomers, especially those accustomed to other operating systems. 
- The initial complexity comes from its powerful flexibility - the same feature that makes Linux so versatile can also make it initially challenging to master. However, modern distributions have made great progress in improving the user experience, though some technical knowledge is still beneficial for optimal use.