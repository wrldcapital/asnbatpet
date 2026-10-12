# PETMalou

The online version of the AHI Inventory Monitoring app. GitHub Pages hosts the page, Firebase Authentication handles sign-in, and a Firebase Realtime Database (Singapore) holds the shared data.

Live link: https://wrldcapital.github.io/petmalou/

| File | What it is |
|---|---|
| `index.html` | Sign-in screen and cloud sync. It holds no inventory or client data. |
| `firebase-config.js` | Firebase project settings (project `petmalou`). They identify the project; they are not a password. |
| `database.rules.json` | Database security rules, already published in Firebase. |

## Access

- Open the link and click **Create an account**. The first account ever created becomes the Admin; everyone after waits for approval.
- The Admin approves requests under **User Accounts** and sets a role: **Admin** (everything), **Editor** (view and edit, no Settings) or **Viewer** (view only).
- Forgot password: the sign-in screen emails a reset link.

## Data

- On first sign-in the Admin chooses the offline file (for example `AHI_Inventory_Monitoring_4.html`). PETMalou copies the app, the workbook data and the Strategic Plan data into the database. None of it is stored in this repo.
- Edits are saved to the database as people work. Simultaneous edits are merged; if two people change the same field, the later save wins. Change history shows who made each change.
- Only approved, signed-in accounts can read the data. Only Admins and Editors can change it.

## Monthly update

Build the new offline file as usual, then in PETMalou go to **User Accounts › Workbook data › Replace workbook data…** and choose it. Edits, monitoring items and settings stay.

## Bringing over edits from the offline file

Offline file: **Settings / Data › Backup JSON**. PETMalou (Admin): **Settings / Data › Restore JSON**.
