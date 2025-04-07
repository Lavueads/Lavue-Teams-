# LAVUE Finance Tracker

This is a web-based finance tracker for Lavueads' team, hosted on GitHub Pages, integrating with Google Sheets for transaction tracking.

## Live Site
[https://lavueads.github.io/Lavue-Teams-/](https://lavueads.github.io/Lavue-Teams-/)

## Features
- Add transactions with amount, description, category, type, user, who paid, and image attachment.
- View summary, who paid expenses, and owes list per user.
- Data stored in Google Sheet: [Lavue Teams Sheet](https://docs.google.com/spreadsheets/d/1mTI6kLZ7KJVejhrfQPRLIZ77kzDt4kYXCl0lnvm0QOc/edit?usp=sharing).
- Direct access: No sign-in required; anyone with the link can add transactions.

## Setup Instructions
### Google Sheets
- Sheet: [https://docs.google.com/spreadsheets/d/1mTI6kLZ7KJVejhrfQPRLIZ77kzDt4kYXCl0lnvm0QOc/edit](https://docs.google.com/spreadsheets/d/1mTI6kLZ7KJVejhrfQPRLIZ77kzDt4kYXCl0lnvm0QOc/edit).
- `Sheet1` headers: `ID | Amount | Description | Category | Type | User | Paid By | Image`.
- Share settings: Set to "Anyone with the link" > "Editor" (required for direct writes).

### Google Cloud
- API Key: `AIzaSyC1Y8p66Vm0oVxyLpmdnnBARXkk7o5Iya8` (included in `index.html`).
- **Security Note**: The API key is exposed in client-side code. In Google Cloud, restrict it to the Sheets API and specific referrers (e.g., `lavueads.github.io/*`).

## Usage
1. Visit [https://lavueads.github.io/Lavue-Teams-/](https://lavueads.github.io/Lavue-Teams-/).
2. Select your name from the "Select User" dropdown (options: Chris, Karun, Vinayak).
3. Add a transaction:
   - Enter amount, description, category, type, who paid (Chris, Karun, or Vinayak), and optionally attach an image.
   - Click "Add Transaction".
4. View summary, expense details (who paid, owes), and transactions.

## Security Warning
- The Google Sheet is publicly editable ("Anyone with the link can edit"). Anyone with the Sheet link can modify or delete data.
- The API key is exposed in `index.html`. For a secure app, add authentication and a backend to control access.

## Troubleshooting
- **Data Not Saving/Retrieving**: Verify Spreadsheet ID (`1mTI6kLZ7KJVejhrfQPRLIZ77kzDt4kYXCl0lnvm0QOc`) and Sheet permissions.
- **API Key Errors**: Ensure the key is restricted to the Sheets API in Google Cloud.
- **Contact**: Email `lavueadvertisements@gmail.com` for help.

## Contributing
- The `users` array in `index.html` is set to `['Chris', 'Karun', 'Vinayak']`. Update it with additional team names if needed.
- Fork this repo, make changes, and submit a pull request.
