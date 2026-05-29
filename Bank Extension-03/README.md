# 🏧 ATM System

A console-based C++ ATM simulation that allows clients to perform banking transactions securely using their account number and PIN code.

---

## 📖 Overview

ATM System is an interactive command-line application that simulates a real ATM experience. Clients authenticate using their account number and PIN, then can perform quick withdrawals, normal withdrawals, deposits, and balance checks. All data is synced with a shared `Clients.txt` file.

---

## ✨ Features

- **Login System**: Secure authentication using account number and PIN code
- **Quick Withdraw**: Predefined withdrawal amounts (20, 50, 100, 200, 400, 600, 800, 1000)
- **Normal Withdraw**: Custom withdrawal amount (must be a multiple of 5)
- **Deposit**: Add a positive amount to the account balance
- **Check Balance**: Display the current account balance
- **Balance Validation**: Prevents withdrawal if amount exceeds available balance
- **Logout**: Return to the login screen without exiting the program
- **File Persistence**: All transactions are saved to `Clients.txt` automatically

---

## 🎮 How to Use

1. Run the program — a **Login Screen** appears first.
2. Enter your account number and PIN code to authenticate.
3. Choose an option from the ATM Main Menu:
   - `1` Quick Withdraw
   - `2` Normal Withdraw
   - `3` Deposit
   - `4` Check Balance
   - `5` Logout
4. If you select **Quick Withdraw**, choose a predefined amount:
   - `1` 20 &nbsp;&nbsp;&nbsp; `2` 50
   - `3` 100 &nbsp;&nbsp; `4` 200
   - `5` 400 &nbsp;&nbsp; `6` 600
   - `7` 800 &nbsp;&nbsp; `8` 1000
   - `9` Exit
5. If you select **Normal Withdraw**, enter any amount that is a multiple of 5.
6. Press any key to return to the main menu after each action.

---

## 🗂️ Data Storage

Client records are stored in `Clients.txt` using a custom separator `#//#` between fields.

**Client record format:**
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
- **Enums** — Defining ATM menu options via `enMainMenueOptions` for readable control flow
- **Global Variables** — Storing the current logged-in client in `CurrentClient` for session management
- **Vectors** — Loading and updating client records dynamically in memory
- **File Handling** — Reading from and writing to `Clients.txt` using `fstream`
- **String Manipulation** — Parsing delimited strings with a custom `SplitString()` function
- **Pass by Reference** — Modifying client vectors directly inside transaction functions
- **Functions** — Clean separation of concerns with single-responsibility functions
- **Loops** — Used for login retry and input validation
- **Type Casting** — Converting user input (`short`) to `enMainMenueOptions` enum
- **Boolean Flags** — Using `MarkForDelete` for safe file rewrite operations

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
| `FindClientByAccountNumberAndPinCode()` | Authenticates a client during login |
| `DepositBalanceToClientByAccountNumber()` | Handles deposit and withdrawal transactions |
| `getQuickWithDrawAmount()` | Maps a quick withdraw option to its amount |
| `PerfromQuickWithdrawOption()` | Executes a quick withdraw with balance validation |
| `PerfromNormalWithdrawOption()` | Executes a custom withdraw with balance validation |
| `PerfromDepositOption()` | Executes a deposit transaction |
| `Login()` | Entry point — handles authentication before showing the ATM menu |
| `ShowMainMenue()` | Renders the ATM main menu and handles navigation |

---

## 📄 License

This project is open source and free to use for educational purposes.

---

## 👤 Author

👤 **Mahmoud Abd El-Sattar**  
📧 mahmoud.abdelsattar.dev@gmail.com  
💼 [linkedin.com/in/mahmoud-abd-el-sattar](https://www.linkedin.com/in/mahmoud-abd-el-sattar-1b227522a)
