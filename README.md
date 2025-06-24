# 🕶️ Hosting a Hidden Website on the Dark Web using Tor & XAMPP (Windows)

**By:** Soorya A P (Callsign: SunGod)  
**Role:** Cybersecurity Student & Ethical Hacking Enthusiast

---

## 🔍 Introduction

As someone studying cybersecurity and actively exploring ethical hacking, I’ve always been curious about how websites are hosted on the dark web — not from a *“what’s there”* angle, but more of a *“how does this technically work?”* curiosity.

So I decided to set up my own `.onion` website completely from scratch — hosted locally using **XAMPP**, routed through **Tor**, and accessed only via **Tor Browser** — all on a regular Windows machine.

---

## 💡 What I Built

The result is a clean, minimal, and private landing page that reflects who I am. Functionality wasn’t the focus — understanding the underlying infrastructure was.

The site uses a dark-themed CSS layout with glowing text and displays a simple hacker-style message:

> **I am SunGod**  
> Hacker. Student of Cybersecurity.  
> I walk in shadows, but I master the light.  
> Knowledge is my weapon. Privacy is my shield.  
> The dark is not where I hide — it’s where I shine.

---

## ⚙️ Tools & Stack Used

- **XAMPP (Apache Server)** – Local web server
- **Tor Expert Bundle** – Hidden service host
- **Tor Browser** – Testing the `.onion` site
- **HTML + CSS** – Frontend design
- **Windows 10** – Full setup on local machine

---

## 🧪 Setup Process

### 🔸 Step 1: Localhost Setup (XAMPP)
- Installed XAMPP
- Started Apache server
- Placed `index.html` in `C:\xampp\htdocs`
- Verified that `http://localhost` loads the page

### 🔸 Step 2: Tor Configuration
- Downloaded the **Tor Expert Bundle**
- Created a file named `torrc` inside the Tor folder with the following lines:

HiddenServiceDir E:\tor\Tor\hidden_service
HiddenServicePort 80 127.0.0.1:80


### 🔸 Step 3: Launching Tor Hidden Service
- Ran Tor with:
tor.exe -f torrc
- Tor generated a `.onion` address inside the `hidden_service` directory
- Accessed the site via **Tor Browser** using the new `.onion` URL

---

## 🧱 Problems I Faced & What I Learned

### 1. Apache and Tor Colliding on Port Usage
**Issue:** Apache and Tor had port binding issues which caused delays.  
**Fix:** Reconfigured Apache to bind only to IPv4 and ensured no other applications (like Skype) were using port 80.

---

### 2. Inconsistent Load Times in Tor Browser
**Observation:** The site sometimes took 20–30 seconds to load.  
**Lesson:** Tor circuits involve multiple relays — so latency is expected, even for local servers.

---

### 3. Tried Enabling HTTPS (Unnecessarily)
**Mistake:** Tried to apply HTTPS over the `.onion` domain.  
**Insight:** Tor already handles end-to-end encryption internally. HTTPS is optional and unnecessary for local `.onion` sites.

---

### 4. Boring First Design
**Problem:** My initial design looked too plain.  
**Solution:** Redesigned the UI with a dark theme, `text-shadow` glow, and hacker-style minimalism inspired by real dark web UIs.

---

## 🔐 Is It Public?

Technically yes — anyone with the `.onion` link can access it via Tor Browser.  
But practically no — the address is nearly impossible to guess, and Tor doesn’t index `.onion` sites. So it's effectively private unless shared.

---

## 🧠 Key Takeaways

- How `.onion` services are hosted through Tor
- Practical use of the `torrc` configuration file
- Challenges of routing, privacy, and localhost servers
- Hosting web content completely off the clearnet
- Debugging and resolving realistic technical issues without external help

---

## 🌱 Future Improvements

- Add password-protected access
- Build a backend (PHP or Flask)
- Create a personal journal or log system
- Turn it into a mini tool drop for private scripts

---

## 👨‍💻 Author

**Soorya A P**  
Cybersecurity Student | Hacker in Training  
Callsign: `SunGod`

---

> ⚠️ This project is for educational purposes only. I do not endorse or encourage the misuse of Tor or dark web infrastructure for illegal activity.

![image](https://github.com/user-attachments/assets/6a145a37-68bd-477d-808a-6880b052f8d6)


