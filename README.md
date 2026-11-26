# Telegram Financial Tracker Bot

## Overview

Telegram Financial Tracker Bot is a personal finance management application built using Python and Telegram Bot API.

The bot allows users to record daily income and expenses directly through Telegram messages. Transaction data is automatically categorized and stored in Google Sheets, making financial tracking more accessible and organized.

The application also provides financial summaries, including total income, total expenses, and current balance.

## Key Features

- **Automatic Transaction Recording:** Record income and expenses through simple text messages.
- **Transaction Categorization:** Automatically classify transactions based on keywords.
- **Income Tracking:** Calculate total recorded income.
- **Expense Tracking:** Calculate total recorded expenses.
- **Balance Calculation:** Display the remaining balance based on recorded transactions.
- **Google Sheets Integration:** Store financial records automatically.
- **Individual User Worksheets:** Maintain separate worksheets for each Telegram user.
- **Transaction Management:** Delete the latest transaction or clear transaction history.
- **Interactive Confirmation:** Use inline keyboard buttons to confirm deletion actions.

## Technology Stack

| Technology | Purpose |
|---|---|
| Python | Main programming language |
| Telegram Bot API | Bot communication interface |
| python-telegram-bot | Telegram bot development framework |
| Google Sheets API | Financial data storage |
| gspread | Google Sheets integration |
| JSON | User worksheet mapping and configuration |
| Regular Expressions | Transaction message parsing |

## How It Works

The application follows this workflow:

1. Users send financial transaction messages through Telegram.
2. The bot analyzes the message using keyword matching and regular expressions.
3. The bot extracts the transaction amount and description.
4. The system determines whether the transaction represents income or an expense.
5. The bot automatically assigns a transaction category.
6. The transaction is saved to the user's worksheet in Google Sheets.
7. Users can retrieve financial summaries using Telegram commands.

## Transaction Examples

Users can record transactions using natural text messages.

| Telegram Message | Transaction Type |
|---|---|
| `beli cilok 5000` | Expense |
| `gaji 2jt` | Income |
| `Indomaret 10 ribu` | Expense |
| `bensin 50rb` | Expense |
| `bonus 500k` | Income |

### Supported Transaction Categories

**Income Categories**
- Salary
- Investment
- Bonus
- Other Income

**Expense Categories**
- Food & Beverages
- Transportation
- Shopping
- Communication
- Bills & Utilities
- Entertainment
- Other Expenses

## Telegram Bot Commands

| Command | Description |
|---|---|
| `/start` | Start the bot and display instructions |
| `/sisa_saldo` | Display current balance and financial summaries |
| `/total_saldo` | Display current balance |
| `/total_income` | Calculate total income |
| `/total_pengeluaran` | Calculate total expenses |
| `/delete_last` | Delete the latest transaction |
| `/clear_history` | Clear all recorded transactions |

The bot also supports regular text messages for recording transactions.

## Google Sheets Integration

The application uses Google Sheets as its financial database.

Each Telegram user receives an individual worksheet based on their Telegram user ID.

The worksheet contains the following columns:

| Column | Description |
|---|---|
| Tanggal | Transaction date |
| Deskripsi | Transaction description |
| Kategori | Transaction category |
| Income | Recorded income |
| Expense | Recorded expense |

This structure allows the application to maintain separate transaction records for individual users.

## Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/alsbbl/Bot-Telegram-Pencatat-Keuangan.git
```

### 2. Navigate to the Project Directory

```bash
cd Bot-Telegram-Pencatat-Keuangan
```

### 3. Install Dependencies

```bash
pip install python-telegram-bot gspread google-auth
```

Alternatively:

```bash
pip install -r requirements.txt
```

### 4. Configure Telegram Bot

1. Open Telegram.
2. Search for BotFather.
3. Create a new bot using `/newbot`.
4. Obtain your Telegram Bot Token.
5. Store the token in an environment variable.

For Windows PowerShell:

```powershell
$env:BOT_TOKEN="YOUR_TELEGRAM_BOT_TOKEN"
```

For Linux or macOS:

```bash
export BOT_TOKEN="YOUR_TELEGRAM_BOT_TOKEN"
```

### 5. Configure Google Sheets API

1. Create a project in Google Cloud Console.
2. Enable Google Sheets API.
3. Create a Google Cloud Service Account.
4. Generate service account credentials.
5. Share your Google Spreadsheet with the service account email.
6. Configure the credentials using the `GOOGLE_CREDENTIALS_JSON` environment variable.

The application expects a Google Spreadsheet named:

`Catatan Keuangan Bot`

### 6. Run the Application

```bash
python bot_tele.py
```

The bot will start polling for incoming Telegram messages.

## Project Structure

```text
Bot-Telegram-Pencatat-Keuangan/
│
├── .github/
│   └── workflows/
│
├── bot_tele.py
│
├── requirements.txt
│
├── user_sheets.json
│
├── README.md
│
└── .gitignore
```

Google service account credentials should be configured separately and must not be committed to the repository.

## Security Considerations

- Store Telegram Bot Tokens in environment variables.
- Never upload Google service account credentials to GitHub.
- Restrict Google Sheets access to authorized service accounts.
- Exclude sensitive configuration files using `.gitignore`.
- Avoid exposing private user transaction records.

## Future Improvements

Potential improvements include:

- Monthly and yearly financial reports.
- Interactive expense category selection.
- Transaction editing functionality.
- Financial visualization and spending analytics.
- Budget planning and spending limits.
- Export financial reports to CSV or Excel.
- Improved natural language processing for transaction recognition.
- Deployment using cloud hosting for continuous availability.

## Project Information

| Information | Details |
|---|---|
| Project Name | Telegram Financial Tracker Bot |
| Author | Safira Khoirulanisa Salsabila |
| Programming Language | Python |
| Application Type | Telegram Bot |
| Integration | Google Sheets API |
| Domain | Financial Technology |
| Repository | GitHub |

## Conclusion

Telegram Financial Tracker Bot demonstrates the integration of Python, Telegram Bot API, and Google Sheets to develop a lightweight personal finance management system.

By combining automated transaction parsing, expense categorization, and financial summaries, the application provides a practical approach to recording and monitoring daily financial activities.

---

**Keywords:** Python, Telegram Bot, Financial Management, Expense Tracker, Income Tracking, Google Sheets API, Automation, Personal Finance.
