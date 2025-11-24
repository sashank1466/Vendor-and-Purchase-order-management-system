📘 Vendor & Purchase Order Management System (C Program)

A simple terminal-based system written in C that manages vendors and their purchase orders.
The program allows adding vendors, listing them, creating purchase orders linked to vendors, and viewing all orders.

⭐ Functional Requirements

The system must allow users to:

1. Add Vendor

Each vendor contains:

Vendor ID (auto-generated)

Vendor Name

Vendor Phone

Prevent exceeding the vendor limit (max 50)

2. List Vendors

Displays all stored vendors in a clean tabular format:

ID

Name

Phone

3. Add Purchase Order

Each purchase order includes:

Order ID (auto-generated)

Vendor ID (must exist)

Item name

Quantity

Price

Validation performed:

Vendor ID must be valid

Prevent exceeding order limit (max 100)

4. List Purchase Orders

Displays all orders with:

Order ID

Vendor Name

Item

Quantity

Price

If a vendor no longer exists, display:
“Unknown Vendor”

5. Exit

Closes the application safely.

⭐ Features

Menu-driven interface

Vendor ID auto-generation

Purchase Order ID auto-generation

Prevents invalid vendor selection

Supports up to 50 vendors and 100 orders

Clean separation of structures

Clear input handling (scanf + fgets compatible)

📌 How to Run the Project
1. Install GCC (if not installed)

Check using:

gcc --version

2. Save the Source Code

Save the program as:

vendor_po_system.c

3. Compile the Program

Open CMD/Terminal in the folder containing the file:

gcc vendor_po_system.c -o vendor_po_system

4. Run the Program

Windows

vendor_po_system.exe


Linux / macOS

./vendor_po_system

📷 Screenshots (Sample Outputs)
Main Menu
=== Vendor & Purchase Order Management System ===
1. Add Vendor
2. List Vendors
3. Add Purchase Order
4. List Purchase Orders
5. Exit
Enter your choice:

Sample Vendor Entry
Enter vendor name: ABC Supplies
Enter vendor phone: 555-9012
Vendor added successfully! ID = 1

Sample Purchase Order Entry
Enter Vendor ID: 1
Enter item name: Printer Paper
Enter quantity: 20
Enter price: 150.50
Purchase order created successfully! Order ID = 1

Sample Listing

Vendor List

ID: 1 | Name: ABC Supplies | Phone: 555-9012


Purchase Orders

Order ID: 1 | Vendor: ABC Supplies | Item: Printer Paper | Qty: 20 | Price: 150.50
