# SACCO Member Account Management System

## 1. Project Overview

The SACCO Member Account Management System is a C++ console-based application designed to manage SACCO members and their account transactions.

The system allows users to register members, search for accounts, update member details, deposit and withdraw money, transfer money between accounts, and generate account reports.

It uses a custom Hash Table and a balanced search tree (`std::set`) to organise and retrieve member records efficiently.

## 2. Main Features

The application supports the following operations:

- **Add Member:** Register a new member with an account number, name, phone number, and opening balance.
- **Search Member:** Find a member using their account number.
- **Update Member:** Change a member's name and phone number.
- **Delete Member:** Remove a member's account.
- **Deposit:** Add money to a member's account.
- **Withdraw:** Remove money from an account, provided there are sufficient funds.
- **Transfer:** Move money between two different member accounts.
- **Apply Interest:** Apply an interest rate to all registered members.
- **Account Range Report:** Display members within a specified account number range.
- **Top Savers Report:** Display members with the highest account balances.
- **List Members:** Display all registered members.
- **Show Hash Buckets:** Display how account numbers are organised in the hash table.
- **Save Data:** Save member records to a file.

## 3. Data Structures and Algorithms

The project uses two main data structures:

**Hash Table**

A custom hash table with 101 buckets is used to store member records. It uses separate chaining to handle collisions when different account numbers produce the same hash value.

**Balanced Search Tree**

The C++ `std::set` is used to maintain account numbers in sorted order. This supports ordered listing, account range reports, and other operations that require sorted account numbers.

## 4. Data Storage

Member information is stored in a text file named `members.txt`.

Each member is stored on a separate line using this format:

`accountNo,name,phone,balance`

Example:

`1001,Salim Ategeka,0740496006,220000.00`

The application loads existing records when it starts and saves changes when the user selects Save or exits the program.

## 5. Input Validation

The system includes basic validation to protect account records and transactions.

- Account numbers must be positive and unique.
- Member names cannot be empty.
- Phone numbers must contain exactly 10 digits.
- Opening balances cannot be negative.
- Deposit and withdrawal amounts must be positive.
- Withdrawals and transfers cannot exceed the available balance.
- Transfers cannot be made to the same account.
- Interest rates must be above 0% and not exceed 100%.

## 6. Project Files

| File | Description |
|---|---|
| `Main.cpp` | Contains the main program and user menu. |
| `Sacco.h` | Contains SACCO operations and member management logic. |
| `HashTable.h` | Implements the custom hash table and member record structure. |
| `Test.cpp` | Contains automated tests for the system. |
| `members.txt` | Stores member account records. |

## 7. How to Compile and Run

A C++ compiler such as GCC is required.

**Compile the main application:**

```bash
g++ -std=c++11 Main.cpp -o Main
```

**Run the application:**

```bash
./Main
```

On Windows, run:

```bash
Main.exe
```

Run the application from the project directory so that it can access `members.txt`.

## 8. Running the Tests

The project includes a separate test program that checks the hash table, member operations, reports, and file handling.

Compile the tests:

```bash
g++ -std=c++11 Test.cpp -o Test
```

Run the tests:

```bash
./Test
```

On Windows:

```bash
Test.exe
```

The test program displays which tests pass or fail and provides a final test count.

## 9. Conclusion

This project demonstrates how C++ data structures can be applied to a practical SACCO account management problem. It combines a custom hash table, a balanced search tree, file handling, input validation, and account transaction operations in one application.
