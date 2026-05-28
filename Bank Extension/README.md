# 🏦 Bank Client Management System

A console-based C++ application for managing bank clients with full CRUD operations and file-based data persistence.

---

## 📖 Overview

Bank Client Management System is an interactive command-line application that allows bank staff to manage client records and perform financial transactions efficiently. All data is stored and retrieved from a text file, ensuring persistence across sessions.

---

## ✨ Features

- **List All Clients**: Display all registered clients in a formatted table
- **Add New Clients**: Register one or multiple new clients with duplicate account number protection
- **Delete Client**: Remove a client record with confirmation prompt
- **Update Client Info**: Modify existing client details with confirmation prompt
- **Find Client**: Search for a client by account number and display their full details
- **Deposit**: Add funds to a client's account with confirmation prompt
- **Withdraw**: Deduct funds from a client's account with balance validation
- **Total Balances**: Display all client balances with the overall total
- **File Persistence**: All data is saved to and loaded from `Clients.txt` automatically

---

## 🎮 How to Use

1. Run the program.
2. Choose an option from the Main Menu:
   - `1` Show Client List
   - `2` Add New Client
   - `3` Delete Client
   - `4` Update Client Info
   - `5` Find Client
   - `6` Transactions
   - `7` Exit
3. If you select **Transactions**, a sub-menu appears:
   - `1` Deposit
   - `2` Withdraw
   - `3` Total Balances
   - `4` Back to Main Menu
4. Follow the on-screen instructions for each operation.
5. Press any key to return to the previous menu after each action.

---

## 🗂️ Data Storage

Client records are stored in `Clients.txt` using a custom separator `#//#` between fields.

Each record follows this format:
```
AccountNumber#//#PinCode#//#Name#//#Phone#//#AccountBalance
```

Example:
```
A100#//#1234#//#John Doe#//#0501234567#//#5000.00
```

---

## 🧠 Concepts Used

- **Structs** — Modeling client data using `sClient` with all relevant fields
- **Enums** — Defining menu options via `enMainMenueOptions` and `enTransactionsMenueOptions` for readable control flow
- **Vectors** — Storing and manipulating client records dynamically in memory
- **File Handling** — Reading from and writing to text files using `fstream` for data persistence
- **String Manipulation** — Parsing delimited strings with a custom `SplitString()` function
- **Pass by Reference** — Modifying vectors and structs directly inside functions
- **Functions** — Clean separation of concerns with single-responsibility functions
- **Loops** — Iterating over client records for search, display, and update operations
- **Type Casting** — Converting user input (`short`) to enum types
- **Boolean Flags** — Using `MarkForDelete` to soft-delete records before saving

---

## 🔑 Key Components

| Component | Description |
|---|---|
| `sClient` | Struct holding all client data fields |
| `SplitString()` | Parses a delimited string into a vector of tokens |
| `ConvertLinetoRecord()` | Converts a file line into an `sClient` struct |
| `ConvertRecordToLine()` | Converts an `sClient` struct into a file line |
| `LoadCleintsDataFromFile()` | Loads all client records from file into a vector |
| `SaveCleintsDataToFile()` | Writes updated client records back to file |
| `FindClientByAccountNumber()` | Searches for a client by account number |
| `DeleteClientByAccountNumber()` | Marks a client for deletion and saves |
| `UpdateClientByAccountNumber()` | Updates a client's info and saves |
| `DepositBalanceToClientByAccountNumber()` | Handles both deposit and withdrawal transactions |
| `ShowTotalBalances()` | Displays all client balances and the overall total |
| `ShowTransactionsMenue()` | Renders the transactions sub-menu and handles navigation |
| `ShowMainMenue()` | Renders the main menu and handles navigation |

---

## 📄 License

This project is open source and free to use for educational purposes.

---

## 👤 Author

👤 **Mahmoud Abd El-Sattar**  
📧 mahmoud.abdelsattar.dev@gmail.com  
💼 [linkedin.com/in/mahmoud-abd-el-sattar](https://www.linkedin.com/in/mahmoud-abd-el-sattar-1b227522a)
