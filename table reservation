#include <iostream>
#include <vector>
#include <string>

using namespace std;

class HotelTableReservation {
private:
    vector<string> tableAvailability;
    vector<string> reservedNames;

public:
    HotelTableReservation(int numTables) {
        tableAvailability.resize(numTables, "Available");
        reservedNames.resize(numTables, "");
    }

    void displayTableStatus() const {
        cout << "---------------------------\n";
        cout << "  Table Availability:\n";
        cout << "---------------------------\n";
        for (size_t i = 0; i < tableAvailability.size(); ++i) {
            cout << "Table " << (i + 1) << ": " << tableAvailability[i];
            if (tableAvailability[i] == "Reserved") {
                cout << " (Reserved by: " << reservedNames[i] << ")";
            }
            cout << "\n";
        }
        cout << "---------------------------\n";
    }

    void reserveTable(int tableNumber, const string& name) {
        if (tableNumber >= 1 && tableNumber <= static_cast<int>(tableAvailability.size())) {
            if (tableAvailability[tableNumber - 1] == "Available") {
                tableAvailability[tableNumber - 1] = "Reserved";
                reservedNames[tableNumber - 1] = name;
                cout << "Table " << tableNumber << " reserved successfully by " << name << ".\n";
            } else {
                cout << "Table " << tableNumber << " is already reserved.\n";
            }
        } else {
            cout << "Invalid table number.\n";
        }
    }

    void checkTableAvailability(int tableNumber) const {
        if (tableNumber >= 1 && tableNumber <= static_cast<int>(tableAvailability.size())) {
            cout << "Table " << tableNumber << ": " << tableAvailability[tableNumber - 1] << "\n";
        } else {
            cout << "Invalid table number.\n";
        }
    }

    void cancelReservation(int tableNumber) {
        if (tableNumber >= 1 && tableNumber <= static_cast<int>(tableAvailability.size())) {
            if (tableAvailability[tableNumber - 1] == "Reserved") {
                tableAvailability[tableNumber - 1] = "Available";
                reservedNames[tableNumber - 1] = "";
                cout << "Reservation for Table " << tableNumber << " canceled successfully.\n";
            } else {
                cout << "Table " << tableNumber << " is not reserved.\n";
            }
        } else {
            cout << "Invalid table number.\n";
        }
    }

    void displayReservedNames() const {
        cout << "---------------------------\n";
        cout << "  Reserved Table Names:\n";
        cout << "---------------------------\n";
        for (size_t i = 0; i < reservedNames.size(); ++i) {
            if (!reservedNames[i].empty()) {
                cout << "Table " << (i + 1) << ": " << reservedNames[i] << "\n";
            }
        }
        cout << "---------------------------\n";
    }
};

int main() {
    int numTables;

    cout << "Enter the number of tables in the hotel: ";
    cin >> numTables;

    HotelTableReservation hotel(numTables);

    int choice;
    int tableNumber;
    string name;

    do {
        cout << "\n----------------------------------\n";
        cout << "  Hotel Table Reservation System\n";
        cout << "----------------------------------\n";
        cout << "1. Display Table Availability\n";
        cout << "2. Reserve a Table\n";
        cout << "3. Check Table Availability\n";
        cout << "4. Cancel Reservation\n";
        cout << "5. Display Reserved Table Names\n";
        cout << "6. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                hotel.displayTableStatus();
                break;

            case 2:
                cout << "Enter your name: ";
                cin.ignore(); // Clear input buffer
                getline(cin, name);
                cout << "Enter the table number to reserve: ";
                cin >> tableNumber;
                hotel.reserveTable(tableNumber, name);
                break;

            case 3:
                cout << "Enter the table number to check availability: ";
                cin >> tableNumber;
                hotel.checkTableAvailability(tableNumber);
                break;

            case 4:
                cout << "Enter the table number to cancel reservation: ";
                cin >> tableNumber;
                hotel.cancelReservation(tableNumber);
                break;

            case 5:
                hotel.displayReservedNames();
                break;

            case 6:
                cout << "Exiting the program.\n";
                break;

            default:
                cout << "Invalid choice. Please enter a valid option.\n";
        }

    } while (choice != 6);

    return 0;
}
