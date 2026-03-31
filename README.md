#include <iostream>
using namespace std;

int main() {
    int option;

    cout << "OPTIONS MENU:\n";
    cout << "1. Convert from Decimal to Binary\n";
    cout << "2. Convert from Binary to Decimal\n";
    cout << "Choose your option!! (1 / 2): ";
    cin >> option;

    if (option == 1) {
        int decimalnum;
        cout << "Write a decimal number: ";
        cin >> decimalnum;
        long binary_num = 0;
        int base = 1;
        while (decimalnum > 0) {
            int remainder = decimalnum % 2;
            binary_num += remainder * base;
            decimalnum /= 2;
            base *= 10;
        }
        cout << "Your binary number is: " << binary_num << endl;
    } else if (option == 2) {
        int binary_num;
        cout << "Write a binary number: ";
        cin >> binary_num;
        long decimalnum = 0;
        int base = 1;
        while (binary_num > 0) {
            int lastnum = binary_num % 10;
            binary_num /= 10;
            decimalnum += lastnum * base;
            base *= 2;
        }
        cout << "Your decimal number is: " << decimalnum << endl;
    } else {
        cout << "Invalid option!" << endl;
    }

    return 0;
}
