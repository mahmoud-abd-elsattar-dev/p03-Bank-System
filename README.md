# 🏦 Bank Client Management System

A console-based C++ application for managing bank clients with full CRUD operations and file-based data persistence.

---

## 📖 Overview

Bank Client Management System is an interactive command-line application that allows bank staff to manage client records and perform financial transactions securely. The system features a login screen with a role-based permissions system, ensuring each user only accesses what they're authorized for. All data is stored and retrieved from text files, ensuring persistence across sessions.

---

## ✨ Features

- **Login System**: Secure login screen with username and password authentication
- **Role-Based Permissions**: Each user has specific permissions controlling what they can access
- **List All Clients**: Display all registered clients in a formatted table
- **Add New Clients**: Register one or multiple new clients with duplicate account number protection
- **Delete Client**: Remove a client record with confirmation prompt
- **Update Client Info**: Modify existing client details with confirmation prompt
- **Find Client**: Search for a client by account number and display their full details
- **Deposit**: Add funds to a client's account with confirmation prompt
- **Withdraw**: Deduct funds from a client's account with balance validation
- **Total Balances**: Display all client balances with the overall total
- **Manage Users**: Full CRUD operations for system users with permission management
- **Logout**: Return to the login screen without exiting the program
- **File Persistence**: All data is saved to and loaded from `Clients.txt` and `Users.txt` automatically

---

## 🎮 How to Use

1. Run the program — a **Login Screen** appears first.
2. Enter your username and password to authenticate.
3. Choose an option from the Main Menu (based on your permissions):
   - `1` Show Client List
   - `2` Add New Client
   - `3` Delete Client
   - `4` Update Client Info
   - `5` Find Client
   - `6` Transactions
   - `7` Manage Users
   - `8` Logout
4. If you select **Transactions**, a sub-menu appears:
   - `1` Deposit
   - `2` Withdraw
   - `3` Total Balances
   - `4` Back to Main Menu
5. If you select **Manage Users**, a sub-menu appears:
   - `1` List Users
   - `2` Add New User
   - `3` Delete User
   - `4` Update User
   - `5` Find User
   - `6` Back to Main Menu
6. Follow the on-screen instructions for each operation.
7. Press any key to return to the previous menu after each action.

---

## 🗂️ Data Storage

Client records are stored in `Clients.txt` and user records in `Users.txt`, both using a custom separator `#//#` between fields.

**Client record format:**
```
AccountNumber#//#PinCode#//#Name#//#Phone#//#AccountBalance
```
Example:
```
A100#//#1234#//#John Doe#//#0501234567#//#5000.00
```

**User record format:**
```
Username#//#Password#//#Permissions
```
Example:
```
Admin#//#admin123#//#-1
```

> Permissions are stored as an integer calculated using bitwise OR of the assigned permission flags.

---

## 🧠 Concepts Used

- **Structs** — Modeling client and user data using `sClient` and `stUser`
- **Enums** — Defining menu options and permissions via multiple enums for readable control flow
- **Bitwise Operations** — Using bitwise OR and AND to assign and check user permissions efficiently
- **Global Variables** — Storing the current logged-in user in `CurrentUser` for permission checks
- **Vectors** — Storing and manipulating client and user records dynamically in memory
- **File Handling** — Reading from and writing to text files using `fstream` for data persistence
- **String Manipulation** — Parsing delimited strings with a custom `SplitString()` function
- **Pass by Reference** — Modifying vectors and structs directly inside functions
- **Functions** — Clean separation of concerns with single-responsibility functions
- **Loops** — Iterating over records for search, display, and update operations
- **Type Casting** — Converting user input (`short`) to enum types
- **Boolean Flags** — Using `MarkForDelete` to soft-delete records before saving

---

## 🔑 Key Components

| Component | Description |
|---|---|
| `sClient` | Struct holding all client data fields |
| `stUser` | Struct holding user credentials and permissions |
| `SplitString()` | Parses a delimited string into a vector of tokens |
| `ConvertLinetoRecord()` | Converts a file line into an `sClient` struct |
| `ConvertUserLinetoRecord()` | Converts a file line into an `stUser` struct |
| `ConvertRecordToLine()` | Converts an `sClient` struct into a file line |
| `ConvertUserRecordToLine()` | Converts an `stUser` struct into a file line |
| `LoadCleintsDataFromFile()` | Loads all client records from file into a vector |
| `LoadUsersDataFromFile()` | Loads all user records from file into a vector |
| `SaveCleintsDataToFile()` | Writes updated client records back to file |
| `SaveUsersDataToFile()` | Writes updated user records back to file |
| `FindClientByAccountNumber()` | Searches for a client by account number |
| `FindUserByUsernameAndPassword()` | Authenticates a user during login |
| `CheckAccessPermission()` | Validates the current user's permission for an action |
| `DeleteClientByAccountNumber()` | Marks a client for deletion and saves |
| `UpdateClientByAccountNumber()` | Updates a client's info and saves |
| `DepositBalanceToClientByAccountNumber()` | Handles both deposit and withdrawal transactions |
| `ShowTotalBalances()` | Displays all client balances and the overall total |
| `Login()` | Entry point — handles authentication before showing the main menu |
| `ShowTransactionsMenue()` | Renders the transactions sub-menu and handles navigation |
| `ShowManageUsersMenue()` | Renders the manage users sub-menu and handles navigation |
| `ShowMainMenue()` | Renders the main menu and handles navigation |

---

## 📄 License

This project is open source and free to use for educational purposes.

---

## 👤 Author

👤 **Mahmoud Abd El-Sattar**  
📧 mahmoud.abdelsattar.dev@gmail.com  
💼 [linkedin.com/in/mahmoud-abd-el-sattar](https://www.linkedin.com/in/mahmoud-abd-el-sattar-1b227522a)
