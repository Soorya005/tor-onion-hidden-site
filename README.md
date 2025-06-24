Hosting a Hidden Website on the Dark Web Using Tor and XAMPP (Windows)
By: Soorya A P (Callsign: SunGod)

Introduction
As someone studying cybersecurity and actively exploring ethical hacking, I’ve always been curious about how websites are hosted on the dark web — not from a “what’s there” perspective, but from a “how does this work” perspective. So, I decided to take it up as a personal project.

The goal was simple:
Set up a .onion website from scratch, hosted locally using XAMPP, routed through Tor, and accessed only via Tor Browser — all on a regular Windows machine.

What I Built
The final result is a simple, clean, and private landing page that reflects who I am. It doesn’t do much in terms of functionality, but that was intentional. The idea was to understand the tech stack behind Tor hidden services and to host a .onion domain entirely on my own system — no third-party servers, no domains, no DNS.

The site is styled with dark-themed CSS and glowing text and displays a short message introducing me:

I am SunGod
Hacker. Student of Cybersecurity.
I walk in shadows, but I master the light.
Knowledge is my weapon. Privacy is my shield.
The dark is not where I hide — it’s where I shine.

Tools & Stack Used
XAMPP (Apache Server) – for local hosting

Tor Expert Bundle – to create the hidden service

Tor Browser – to access and test the .onion site

HTML + CSS – for designing the landing page

Windows 10 – the entire setup ran locally on my laptop

Setup Process
Step 1: Localhost Setup
I installed XAMPP and started Apache. Any file placed in htdocs could now be accessed at http://localhost. I tested this with a basic HTML file and confirmed that my local server was working.

Step 2: Tor Configuration
I downloaded and extracted the Tor Expert Bundle, which doesn’t have a GUI. Inside the Tor folder, I created a torrc file to define my hidden service settings:

nginx
Copy
Edit
HiddenServiceDir E:\tor\Tor\hidden_service
HiddenServicePort 80 127.0.0.1:80
Step 3: Launching Tor
I launched Tor using:

Copy
Edit
tor.exe -f torrc
Tor started successfully and generated a .onion address, which I used to access the site via Tor Browser.

Problems I Faced and How I Solved Them
This project wasn’t just about following steps — I ran into a few interesting roadblocks that helped me learn more than I expected.

1. Apache and Tor Colliding on Port Usage
When I ran Apache and Tor together, I noticed delays and inconsistencies in loading the .onion site. After some digging, I realized Tor and Apache were both using similar ports (80 and 9050), and sometimes they didn’t sync well.

Solution:
I reconfigured Apache to listen only on IPv4 (instead of IPv6 fallback), and made sure no other service (like Skype or Windows services) was competing for port 80. Once isolated, everything worked smoothly.

2. Loading Time Was Inconsistent in Tor Browser
The site sometimes took up to 30 seconds to load, even though it was hosted locally. It felt like something was wrong with my setup — but it wasn’t.

What I Learned:
This is just how Tor hidden services behave. Due to the way circuits are built through multiple relays, there's inherent latency. I confirmed this by testing other .onion sites — they had the same lag. So it wasn’t a bug — it was just part of the experience.

3. I Tried Using HTTPS but It Didn’t Work
I originally tried to configure SSL for the site, thinking I should serve over HTTPS even on Tor.

What I Learned:
Tor hidden services already encrypt traffic end-to-end within the network. You don’t need HTTPS for .onion sites. In fact, setting up SSL for localhost usually causes more trouble than it’s worth. This was a good reminder that not everything from the clearnet applies to the dark web.

4. Web Design Felt Too Basic at First
The default HTML page I built looked flat and boring. I didn’t want it to feel like a high school assignment.

Solution:
I researched how some dark web UIs look — and redesigned the page using dark backgrounds, glowing text (text-shadow), and a minimal layout that aligned with cyber themes. The end result looks more like a terminal-styled hacker intro than a personal blog.

Is It Public?
Technically yes — but practically no.

The .onion site is accessible to anyone who has the exact address, but that address is nearly impossible to guess. Unless I share it publicly or post it somewhere, it’s essentially invisible. Tor doesn’t index .onion domains like normal DNS does, so it remains hidden by design.

What I Learned
How to set up and host a .onion website locally from Windows

How Tor hidden services work at a config level

Why privacy-focused tech is so different from clearnet practices

How self-hosting brings total control (but also more responsibility)

That broken configurations usually teach more than working ones

Final Thoughts
This wasn’t a big project in terms of code, but it taught me a lot about infrastructure, privacy, and web hosting from a cybersecurity angle. I now understand how hidden services work and how ethical hackers or researchers can build on top of them safely and privately.

Going forward, I’d love to experiment more with:

Adding password protection

Hosting small tools privately

Building a backend with Python or PHP

Creating a minimal blog or journal through a .onion site

For now, this is my private corner of the internet — powered by Tor, styled in shadows, and built by a hacker in training.

— Soorya A P (SunGod)
Cybersecurity Student & Ethical Hacking Enthusiast
