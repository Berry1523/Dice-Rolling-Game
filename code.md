# Dice-Rolling-Game

#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

int main() {
    int numDice, rollCount = 0;
    char rollAgain;

    srand(static_cast<unsigned int>(time(0)));

    do {
        cout << "Enter the number of dice you want to roll (1-6): ";
        cin >> numDice;

        if (numDice < 1 || numDice > 6) {
            cout << "Please enter a valid number of dice." << endl;
            continue;
        }

        cout << "Rolling " << numDice << " dice..." << endl;

        for (int i = 0; i < numDice; ++i) {
            int roll = rand() % 6 + 1;
            cout << "Dice " << (i + 1) << ": " << roll << endl;
        }

        rollCount++;
        cout << "Total rolls this session: " << rollCount << endl;

        cout << "Would you like to roll again? (y/n): ";
        cin >> rollAgain;

    } while (rollAgain == 'y' || rollAgain == 'Y');

    return 0;
}
