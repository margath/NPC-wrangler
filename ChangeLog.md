Gemini said
NPC & PC Tracker Changelog
v1.6: The Security & UI Update (Latest)

Role Elevation: Replaced the "DM Override" button with a secure "Elevate DM" workflow requiring PIN verification.

Table View: Added a "Toggle View" button to switch between the classic card grid and a condensed table mode for managing large rosters.

Data Deletion: Added a universal "Delete" button for all entities.

Privacy Compliance: Integrated a sleek, fixed red "Privacy" ribbon linking to a dedicated privacy.html policy page.

Session Management: Added "Logout" and "Disconnect" buttons. The Disconnect feature includes a 1-second safety delay and confirmation state to prevent accidental database drops.

Bug Fix: Mapped the frontend to properly ingest CharacterName from the Google Sheet if the lowercase name property is missing, fixing the PC loading issue.

v1.5: The Shareability Update

Dynamic Joining: The app now parses a ?gas= parameter from the URL to automatically connect players to the correct database.

Anti-Shoulder Surfing: Moved the dynamic QR code generation into the "Setup / Share" modal to hide the database URL from wandering eyes at the table.

Ephemeral Security: Transitioned the database URL storage from permanent localStorage to sessionStorage so the connection is wiped the moment the browser tab closes.

Validation Check: Implemented a mismatch detection system that throws a warning modal if the loaded database lacks the exact NPC Database and 1.0 version signatures.

v1.4: The Backend Integration Update

Google Apps Script (GAS): Fully integrated the GM's provided Apps Script to serve as the JSON backend.

Bi-directional Sync: Added a "Pull Data" button to manually overwrite local storage with fresh spreadsheet data, complementing the "Save to Cloud" feature.

In-App Documentation: Embedded the required Apps Script code directly into the Setup Modal, complete with a "Copy Script" button for easy DM onboarding.

v1.3: The D&D Mechanics Update

Initiative Tracking: Added a "Toggle Combat" mode that reveals initiative input fields and instantly re-sorts the active grid highest-to-lowest.

Condition Tracking: Implemented a 5e-standard status checkbox grid (Incapacitated, Paralyzed, Poisoned, etc.).

Long Rest Automation: Added a "Long Rest" button that clears temporary statuses and sequentially progresses the custom Revived -3 > -2 > -1 chain.

Taglines & Secrets: Added player-editable taglines (displayed in italics) and DM/Owner-only secret fields.

Unified Database: Merged PCs and NPCs into a single version-controlled data array (v1.0).

v1.2: The Logging & UX Update

Clipboard Export: Refactored the "Export Session Log" to format Active Party and Notable NPCs directly to the device clipboard instead of downloading a text file.

UI Polish: Matched button heights, padding, and styling across the entire header control bar.

Static Branding: Re-introduced the static QR code linking to the Game Portal.

v1.1: The NPC Refactor

Core Pivot: Refactored the base "Campaign and Item Tracker" framework entirely into an NPC tracker.

Hometown Sorting: Added a dropdown filter that dynamically promotes selected hometowns to the penultimate sorting spot.

Party Integration: Added a "Currently travelling with party?" toggle that promotes entities to the ultimate top sorting spot.

v1.0: Base Framework

Initial HTML/CSS grid layout, basic local storage mechanics, and card-based UI foundation.
