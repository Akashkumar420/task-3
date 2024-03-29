#include <iostream>
#include <cstdlib> // For rand() and srand()
#include <ctime>   // For time()

using namespace std;

int main() {
    // Seed the random number generator
    srand(static_cast<unsigned int>(time(0)));

    // Generate a random number between 1 and 100
    int secretNumber = rand() % 100 + 1;

    int guess;
    int attempts = 0;

    cout << "Welcome to the Number Guessing Game!" << endl;
    cout << "Try to guess the number between 1 and 100." << endl;

    do {
        // Get the player's guess
        cout << "Enter your guess: ";
        cin >> guess;

        // Check the guess
        if (guess < 1 || guess > 100) {
            cout << "Please enter a number between 1 and 100." << endl;
        } else {
            attempts++;

            if (guess < secretNumber) {
                cout << "Too low! Try again." << endl;
            } else if (guess > secretNumber) {
                cout << "Too high! Try again." << endl;
            } else {
                cout << "Congratulations! You guessed the correct number in " << attempts << " attempts." << endl;
            }
        }
    } while (guess != secretNumber);

    return 0;
}
