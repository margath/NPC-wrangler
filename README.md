# 👤 NPC & PC Tracker

A lightweight, serverless web application designed for Tabletop RPG Game Masters and players. This tool tracks Player Characters (PCs), Non-Player Characters (NPCs), initiative, and status conditions, utilizing a custom Google Sheet as a seamless, free cloud backend.

## ✨ Features

* **Real-time Cloud Sync:** Uses Google Apps Script to save and pull campaign data directly from a Google Sheet.
* **Role-Based Authentication:** Players log in using a PIN to edit their characters, while GMs can elevate their permissions to manage the entire database and view hidden secrets.
* **Combat & Initiative Tracking:** Toggle combat mode to instantly reveal initiative inputs and auto-sort the roster from highest to lowest.
* **5e Status Tracking & Automation:** Tracks standard 5th Edition conditions. The "Long Rest" button automatically clears temporary statuses and progresses custom death/revival mechanics (e.g., ticking `Revived -3` down to `-2`, `-1`, and clear).
* **Flexible Views:** Switch between a detailed Card Grid and a condensed Table Mode. The smart table display automatically omits unset or blank fields to keep your interface clean for displaying and printing.
* **Instant Session Sharing:** Generates a secure, dynamic QR code hidden in the setup menu. Players simply scan the code to instantly connect to the GM's active database without typing any URLs.
* **Session Log Export:** One-click copy of the active party, companions, and notable NPCs to your clipboard for easy session journaling.

## 🛠️ Setup Instructions (For Game Masters)

To use the cloud-sync features of this tracker, you need to set up a Google Sheet to act as your database.

### 1. Prepare the Google Sheet
1. Create a new Google Sheet.
2. Create two tabs (sheets) at the bottom named exactly: **NPCs** and **PCs**.
3. In the **PCs** sheet, type the following exact column headers in the first row: `PlayerName`, `CharacterName`, and `PIN`.
4. Fill out the rows with your players' real names, their character names, and a simple passcode (e.g., `1234`).

### 2. Deploy the Google Apps Script
1. In your Google Sheet, click **Extensions > Apps Script**.
2. Delete any code in the editor and paste the provided Google Apps Script (found within the app's Setup modal).
3. Click the **Save** icon.
4. In the top right corner, click **Deploy > New deployment**.
5. Click the gear icon ⚙️ next to "Select type" and choose **Web app**.
6. Set **Execute as** to **Me**.
7. Set **Who has access** to **Anyone**.
8. Click **Deploy** (You will need to authorize permissions on your Google account).
9. Copy the provided **Web app URL**.

### 3. Connect the Tracker
1. Open the `index.html` file in your browser.
2. Click **⚙️ Setup / Share** in the top navigation bar.
3. Paste your Google Web App URL into the connection box and click **Connect & Load Database**.
4. Your players can now scan the QR code in that same menu to join your session!

## 🎲 Player Guide

1. **Join the Session:** Scan the GM's QR code. Your browser will automatically link to the campaign database.
2. **Log In:** Click **Login**, select your name from the dropdown (pulled from the Google Sheet), and enter your PIN.
3. **Manage Your Character:** You can edit your PC's description, tagline, and statuses. 
4. **Disconnect:** At the end of the session, close the tab, or click **🔌 Disconnect** to securely wipe the database URL from your browser's session storage.

## 🔒 Privacy & Architecture

This application is entirely client-side (HTML/JS/CSS). It does not use central servers, telemetry, or analytics. 
* **Local Data:** Offline changes are saved to your browser's `localStorage`.
* **Session Data:** The database connection URL is stored in `sessionStorage` and is wiped immediately upon closing the tab.
* **Cloud Data:** All campaign data is transmitted directly between the user's browser and the GM's personal Google Sheet. 

For full details, please refer to the included `privacy.html` file.
