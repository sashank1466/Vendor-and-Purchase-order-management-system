#include <stdio.h>
#include <string.h>

#define MAX_VENDORS 50
#define MAX_ORDERS 100

// ---------------------------
// STRUCTURES
// ---------------------------

typedef struct {
    int id;
    char name[50];
    char phone[20];
} Vendor;

typedef struct {
    int id;
    int vendorId;
    char item[50];
    int quantity;
    float price;
} PurchaseOrder;

// ---------------------------
// GLOBAL DATA
// ---------------------------

Vendor vendors[MAX_VENDORS];
PurchaseOrder orders[MAX_ORDERS];

int vendorCount = 0;
int orderCount = 0;

// ---------------------------
// FUNCTION DECLARATIONS
// ---------------------------

void addVendor();
void listVendors();
void addPurchaseOrder();
void listPurchaseOrders();
int findVendorById(int id);

// ---------------------------
// MAIN MENU
// ---------------------------

int main() {
    int choice;

    while (1) {
        printf("\n=== Vendor & Purchase Order Management System ===\n");
        printf("1. Add Vendor\n");
        printf("2. List Vendors\n");
        printf("3. Add Purchase Order\n");
        printf("4. List Purchase Orders\n");
        printf("5. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1: addVendor(); break;
            case 2: listVendors(); break;
            case 3: addPurchaseOrder(); break;
            case 4: listPurchaseOrders(); break;
            case 5: return 0;
            default: printf("Invalid choice!\n");
        }
    }
}

// ---------------------------
// FUNCTION DEFINITIONS
// ---------------------------

void addVendor() {
    if (vendorCount >= MAX_VENDORS) {
        printf("Vendor limit reached!\n");
        return;
    }

    Vendor v;
    v.id = vendorCount + 1;

    printf("Enter vendor name: ");
    getchar(); // clear buffer
    fgets(v.name, sizeof(v.name), stdin);
    v.name[strcspn(v.name, "\n")] = '\0';

    printf("Enter vendor phone: ");
    fgets(v.phone, sizeof(v.phone), stdin);
    v.phone[strcspn(v.phone, "\n")] = '\0';

    vendors[vendorCount++] = v;

    printf("Vendor added successfully! ID = %d\n", v.id);
}

void listVendors() {
    printf("\n--- Vendor List ---\n");
    for (int i = 0; i < vendorCount; i++) {
        printf("ID: %d | Name: %s | Phone: %s\n",
               vendors[i].id, vendors[i].name, vendors[i].phone);
    }
}

int findVendorById(int id) {
    for (int i = 0; i < vendorCount; i++) {
        if (vendors[i].id == id)
            return i;
    }
    return -1;
}

void addPurchaseOrder() {
    if (orderCount >= MAX_ORDERS) {
        printf("Order limit reached!\n");
        return;
    }

    PurchaseOrder o;
    o.id = orderCount + 1;

    printf("Enter Vendor ID: ");
    scanf("%d", &o.vendorId);

    if (findVendorById(o.vendorId) == -1) {
        printf("Invalid vendor ID!\n");
        return;
    }

    printf("Enter item name: ");
    getchar(); // clear buffer
    fgets(o.item, sizeof(o.item), stdin);
    o.item[strcspn(o.item, "\n")] = '\0';

    printf("Enter quantity: ");
    scanf("%d", &o.quantity);

    printf("Enter price: ");
    scanf("%f", &o.price);

    orders[orderCount++] = o;

    printf("Purchase order created! Order ID = %d\n", o.id);
}

void listPurchaseOrders() {
    printf("\n--- Purchase Order List ---\n");
    for (int i = 0; i < orderCount; i++) {
        int idx = findVendorById(orders[i].vendorId);
        printf("Order ID: %d | Vendor: %s | Item: %s | Qty: %d | Price: %.2f\n",
               orders[i].id,
               vendors[idx].name,
               orders[i].item,
               orders[i].quantity,
               orders[i].price);
    }
}
