# LAVUE Finance Tracker

This is a web-based finance tracker for Lavueads' digital marketing team, hosted on GitHub Pages. It allows team members to log income and expenses, track who paid, calculate owes, and attach images, with data stored in a Google Sheet.

## Live Site
Visit the tracker at: [https://lavueads.github.io/Lavue-Teams-/](https://lavueads.github.io/Lavue-Teams-/)

## Features
- Add transactions (income/expense) with amount, description, category, user, who paid, and optional image attachment.
- View a summary of total income, expenses, and net balance per user.
- Track who paid expenses and calculate what each user owes.
- Data persists in a Google Sheet: [Lavue Teams Sheet](https://docs.google.com/spreadsheets/d/1mTI6kLZ7KJVejhrfQPRLIZ77kzDt4kYXCl0lnvm0QOc/edit?usp=sharing).
- Built with React, Tailwind CSS, and the Google Sheets API.

## Setup Instructions

### Prerequisites
- A Google account with access to the Lavue Teams Google Sheet.
- A GitHub account (optional for contributors).

### Google Sheets Setup
1. **Access the Google Sheet**:
   - Open: [https://docs.google.com/spreadsheets/d/1mTI6kLZ7KJVejhrfQPRLIZ77kzDt4kYXCl0lnvm0QOc/edit](https://docs.google.com/spreadsheets/d/1mTI6kLZ7KJVejhrfQPRLIZ77kzDt4kYXCl0lnvm0QOc/edit).
   - Ensure headers in `Sheet1` (row 1) are: `ID`, `Amount`, `Description`, `Category`, `Type`, `User`, `Paid By`, `Image`.

2. **Share the Sheet**:
   - Share with team members (e.g., set to "Editor" for specific emails like `team@lavueads.com`).

### Google Cloud Setup
1. **Verify Project**:
   - Go to [Google Cloud Console](https://console.cloud.google.com/).
   - Select the project using Client ID: `308700316236-2dr5vdlv1spptpoju5npimug17scct1b.apps.googleusercontent.com`.
2. **Enable Sheets API**:
   - Ensure "Google Sheets API" is enabled in "Library".
3. **Check OAuth Credentials**:
   - In "Credentials", verify the OAuth 2.0 Client ID has `https://lavueads.github.io` in "Authorized JavaScript origins".

### Deploy to GitHub Pages
1. Ensure `index.html` is uploaded to [Lavue-Teams-](https://github.com/Lavueads/Lavue-Teams-).
2. Go to "Settings" > "Pages".
3. Confirm "Source" is `main` branch and `/ (root)` folder.
4. Site is live at `https://lavueads.github.io/Lavue-Teams-/`.

## Usage
1. Visit [https://lavueads.github.io/Lavue-Teams-/](https://lavueads.github.io/Lavue-Teams-/).
2. Click "Sign in with Google" and authenticate with a Sheet-accessible account.
3. Select your name from the "Select User" dropdown.
4. Add a transaction:
   - Enter amount, description, category, type, who paid, and optionally attach an image.
   - Click "Add Transaction".
5. View summary, expense details (who paid, owes), and transactions.

## Troubleshooting
- **Sign-In Fails**: Ensure `https://lavueads.github.io` is in "Authorized JavaScript origins".
- **Data Not Saving/Retrieving**: Verify Spreadsheet ID (`1mTI6kLZ7KJVejhrfQPRLIZ77kzDt4kYXCl0lnvm0QOc`) and Sheet permissions.
- **Contact**: Email `team@lavueads.com` for help.

## Security Note
- The `client_id` is exposed in `index.html`. For production, use a backend to secure API calls.
- Image attachments are stored as base64 strings in the Sheet; displaying them requires additional setup.

## Contributing
- Update `users` array in `index.html` with team names (e.g., `['Alice', 'Bob', 'Charlie']`).
- Fork this repo, make changes, and submit a pull request.
