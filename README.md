# LAVUE Finance Tracker

This is a web-based finance tracker for Lavueads' digital marketing team, hosted on GitHub Pages. It allows team members to log income and expenses, track who paid, calculate owes, and attach images, with data stored and managed via a Google Apps Script web app.

## Live Site
Visit the tracker at: [[invalid url, do not cite])

## Features
- Add transactions (income/expense) with amount, description, category, user, who paid, and optional image attachment.
- View a summary of total income, expenses, and net balance per user.
- Track who paid expenses and calculate what each user owes.
- Data is saved to and retrieved from a Google Sheet via Google Apps Script.
- Currency: Indian Rupees (₹).
- Users: Chris, Karun, Vinayak.

## Setup Instructions

### Google Sheets Setup
1. **Access the Google Sheet**:
   - Open: [[invalid url, do not cite]).
   - Ensure headers in `Sheet1` (row 1) are: `ID`, `Amount`, `Description`, `Category`, `Type`, `User`, `Paid By`, `Image`.

2. **Set Up Google Apps Script**:
   - In the Google Sheet, go to `Extensions` > `Apps Script`.
   - Replace the default code with the provided script:
     ```javascript
     function doPost(e) {
       var sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName('Sheet1');
       var data = JSON.parse(e.postData.contents);
       sheet.appendRow([data.id, data.amount, data.description, data.category, data.type, data.user, data.paidBy, data.image]);
       return ContentService.createTextOutput('Success').setMimeType(ContentService.MimeType.TEXT);
     }

     function doGet() {
       var sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName('Sheet1');
       var data = sheet.getDataRange().getValues();
       var jsonData = data.slice(1).map(row => ({
         id: row[0],
         amount: row[1],
         description: row[2],
         category: row[3],
         type: row[4],
         user: row[5],
         paidBy: row[6],
         image: row[7]
       }));
       return ContentService.createTextOutput(JSON.stringify(jsonData)).setMimeType(ContentService.MimeType.JSON);
     }
     ```
   - Save and deploy as a web app:
     - Click `Deploy` > `New deployment`.
     - Select `Web app`.
     - Set `Execute as` to `Me`.
     - Set `Who has access` to `Anyone` (for testing; restrict later if needed).
     - Deploy and copy the web app URL (e.g., `[invalid url, do not cite]).

### Update the Code
- Open `index.html` in the repository and replace `YOUR_WEB_APP_ID` in `const WEB_APP_URL = '[invalid url, do not cite] with your actual web app URL.

### Deploy to GitHub Pages
1. Ensure `index.html` is uploaded to [Lavue-Teams-](https://github.com/Lavueads/Lavue-Teams-).
2. Go to "Settings" > "Pages".
3. Confirm "Source" is `main` branch and `/ (root)` folder.
4. Site is live at `[invalid url, do not cite].

## Usage
1. Visit [[invalid url, do not cite]).
2. Select your name from the "Select User" dropdown (options: Chris, Karun, Vinayak).
3. Add a transaction:
   - Enter amount, description, category, type, who paid, and optionally attach an image.
   - Click "Add Transaction".
4. View summary, expense details (who paid, owes), and transactions.

## Security Notes
- The Google Apps Script web app is set to "Anyone" can access, meaning anyone with the URL can read/write data.
- For enhanced security, consider adding authentication or restricting access to specific users.
- The Google Sheet can remain private; only the web app needs access.

## Troubleshooting
- **Data Not Saving/Retrieving**: Ensure the web app URL is correctly set in `index.html` and that the Apps Script is deployed properly.
- **CORS Issues**: If cross-origin errors occur, check the web app's deployment settings.
- **Contact**: Email `lavueadvertisements@gmail.com` for assistance.

## Contributing
- To update the user list, edit `const users = ['Chris', 'Karun', 'Vinayak']` in `index.html`.
- Fork this repo, make changes, and submit a pull request.

## License
[MIT License](LICENSE) (optional; add a `LICENSE` file if desired)
