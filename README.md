# Lavue Teams Finance Tracker

This is a web-based finance tracker for Lavueads' digital marketing team, hosted on GitHub Pages. It allows team members to log income and expenses, storing data in a centralized Google Sheet for multi-user access.

## Live Site
Visit the tracker at: [https://lavueads.github.io/Lavue-Teams-/](https://lavueads.github.io/Lavue-Teams-/)

## Features
- Add transactions (income or expense) with amount, description, category, and user.
- View a summary of total income, expenses, and net balance per user.
- Data is saved to a Google Sheet, accessible to all authorized team members.
- Built with React, Tailwind CSS, and the Google Sheets API.

## Setup Instructions

### Prerequisites
- A Google account with access to the Lavue Teams Google Sheet.
- A GitHub account (optional for contributors).

### Google Sheets Setup
1. **Create or Use the Google Sheet**:
   - Open the team’s Google Sheet or create a new one at [Google Sheets](https://sheets.google.com).
   - Set headers in `Sheet1` (row 1): `ID`, `Amount`, `Description`, `Category`, `Type`, `User`.
   - Copy the Spreadsheet ID from the URL: `https://docs.google.com/spreadsheets/d/SPREADSHEET_ID/edit`.

2. **Share the Sheet**:
   - Share with Lavueads team members (e.g., set to "Editor" for specific emails like `team@lavueads.com`).

### Google Cloud Setup
1. **Create a Project**:
   - Go to [Google Cloud Console](https://console.cloud.google.com/).
   - Create a new project (e.g., "Lavue Finance Tracker").
2. **Enable Sheets API**:
   - Navigate to "APIs & Services" > "Library" > Enable "Google Sheets API".
3. **Create OAuth Credentials**:
   - Go to "Credentials" > "Create Credentials" > "OAuth 2.0 Client IDs".
   - Select "Web application".
   - Add `https://lavueads.github.io/Lavue-Teams-` to "Authorized JavaScript origins".
   - Copy the `client_id` (e.g., `1234567890-abcde.apps.googleusercontent.com`).

### Update the Code
- Open `index.html` in the repository and replace:
  - `YOUR_CLIENT_ID_HERE` with your OAuth `client_id`.
  - `YOUR_SPREADSHEET_ID_HERE` with the Spreadsheet ID from the Google Sheet.

### Deploy to GitHub Pages
1. Ensure `index.html` is uploaded to this repository (`Lavue-Teams-`).
2. Go to "Settings" > "Pages".
3. Confirm "Source" is set to `main` branch and `/ (root)` folder.
4. The site is live at `https://lavueads.github.io/Lavue-Teams-/`.

## Usage
1. Visit [https://lavueads.github.io/Lavue-Teams-/](https://lavueads.github.io/Lavue-Teams-/).
2. Click "Sign in with Google" and authenticate with a Google account that has Sheet access.
3. Select your name from the user dropdown (e.g., "User1" or update with team names).
4. Add transactions; they’ll save to the Google Sheet and display in the app.

## Troubleshooting
- **Sign-In Fails**: Verify `https://lavueads.github.io/Lavue-Teams-` is in Google Cloud’s "Authorized JavaScript origins".
- **Data Not Saving**: Check the Spreadsheet ID and ensure your Google account has edit permissions.
- **Contact**: Email `support@lavueads.com` (or your preferred contact) for assistance.

## Security Note
- The `client_id` is exposed in `index.html`. This is fine for team use, but for a public app, secure API calls with a backend.

## Contributing
- To update the user list, edit `const users = ['User1', 'User2', 'User3']` in `index.html`.
- Fork this repo, make changes, and submit a pull request.

## License
[MIT License](LICENSE) (optional; add a `LICENSE` file if desired)
