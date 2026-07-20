# 🤖 OJT Attendance Automator

A Discord bot and Power Automate integration designed to seamlessly automate daily On-the-Job Training (OJT) time-in and time-out logging.

If you are a student using the bot hosted on our class Discord server, **you do not need to install or run any code.** You only need to import the Power Automate workflow and register your email with the bot.

---

## 🚀 Classmate Setup Guide (End Users)

### Step 1: Outlook Prep (Folder & Rule)
To keep your inbox clean and ensure the automation works perfectly, the flow is designed to look for emails in a specific folder.
1. Open your CIT-U Outlook email.
2. Create a new folder named exactly: **`OJT_Logs`**
3. Create an Outlook Inbox Rule:
   **Condition:** If the subject includes `OJT_`
   **Action:** Move to the `OJT_Logs` folder
4. *(Optional but Recommended):* Once you receive your first bot email, check your Junk/Quarantine folder and mark it as "Not Junk" to whitelist it.

### Step 2: Import the Power Automate Workflow
This workflow catches the bot's data payloads and updates your specific records on the master SharePoint list.
1. Download the `OJT_Workflow_Template.zip` file from this repository.
2. Log into [Power Automate](https://make.powerautomate.com/) using your CIT-U Microsoft account.
3. Go to **My flows** > **Import** > **Import Package (Legacy)**.
4. Upload the `.zip` file.
5. During the import process, you will be prompted to resolve the connections (Outlook and SharePoint). Click on each one and sign in with your institutional account.
6. Once imported, simply **Turn On** the flow. You do not need to edit any of the blocks!

### Step 3: Register in Discord
Go to our Discord server and use the register command to link your email, role, and optional default location:
**It is recommended to run the `!help` command first upon entering the server**
`!register your.email@cit.edu QA "Fuente Osmeña Circle, Cebu City"`

---

---

## 📖 Quick Command Guide

Use these commands in the Discord server to manage your shifts:

| Command | Description |
| :--- | :--- |
| `!register <email> <role> [location]` | Links your Discord to the system. |
| `!status` | Shows your current login state, queued logs, and leaves. |
| `!timein <HH:MMAM/PM>` | Manually clocks you in for the current day. |
| `!timeout <HH:MMAM/PM> [log]` | Manually clocks you out. Uses a random log if `[log]` is empty. |
| `!addlog <text>` | Adds a phrase to your randomized log pool. |
| `!listlogs` | Views your saved random logs. |
| `!removelog <number>` | Removes an entry from your randomized log pool by its number (see `!listlogs`). |
| `!setloc <location>` | Updates your default Clock-In location. |
| `!setlog <text>` | Queues a specific, one-time log for your next automated timeout. |
| `!leave add <YYYY-MM-DD>` | Tells the bot to skip your automated shifts for a specific date. |

*(For corrections, use the Fix commands: `!fixrecord`, `!fixlog`, `!fixloc`, and `!fixhrs`. Type `!help` in Discord for full syntax).*

---

## 👨‍💻 For Developers: Self-Hosting the Bot

*(If you are just using the bot in the class server, ignore this section!)*

 If you wish to fork this project and host your own instance of the Discord bot, please open a GitHub Issue or Discussion in this repository.
    

**Author:** Brent Micheal S. Tolentino | _Cebu Institute of Technology - University (CIT-U)_
