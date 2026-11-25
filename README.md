# Online Complaint Management System (front-end prototype)

Complaint portal with three roles: **User**, **Admin** and **Officer**.

## Run it
Open `index.html` in a browser. Or serve the folder:

    python3 -m http.server 8000     # then visit http://localhost:8000

No install or build step. Data is kept in memory and resets on refresh.

## Tech stack
- HTML5, CSS3 (custom properties, grid, flexbox), vanilla JavaScript
- Fonts: Sora and DM Sans (Google Fonts, needs internet; system fonts are the fallback)
- Planned production stack: React.js, REST APIs, Node.js + Express (JWT), PostgreSQL

## Demo accounts (password: `demo`)
| Role | Email |
|---|---|
| User | user@demo.in |
| Admin | admin@demo.in |
| Officer | officer@demo.in, officer2@demo.in, officer3@demo.in, officer4@demo.in |

One-time code for registration and forgot password: `123456`.

## Complaint assignment
A new complaint starts as Submitted with no officer. Only an admin assigns the officer, either from the
All complaints list or the complaint details page (Approve button).

## Structure
    index.html      page shell
    css/styles.css  theme and responsive layout
    js/app.js       state, screens, workflows (in-memory data)
    assets/bg.png   background image

## Connecting a backend
The `DB` object in `js/app.js` stands in for the database tables (Users, Employees, Complaint,
Document, Status_History, Notification, Escalation, Feedback, OTP_Verification). Replace reads and
writes with calls to your Express API and store passwords as hashes.
