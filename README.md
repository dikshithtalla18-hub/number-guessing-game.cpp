#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

int main() {
    char playAgain;

    do {
        srand(time(0));
        int target = rand() % 100 + 1;
        int guess, attempts = 0;

        cout << "===== NUMBER GUESSING GAME =====" << endl;
        cout << "Guess a number between 1 and 100" << endl;

        do {
            cout << "Enter your guess: ";
            cin >> guess;
            attempts++;

            if (guess > target)
                cout << "Too High! Try Again." << endl;
            else if (guess < target)
                cout << "Too Low! Try Again." << endl;
            else
                cout << "Congratulations! You guessed the correct number." << endl;

        } while (guess != target);

        cout << "Attempts Taken: " << attempts << endl;

        if (attempts <= 5)
            cout << "Score: Excellent!" << endl;
        else if (attempts <= 10)
            cout << "Score: Good!" << endl;
        else
            cout << "Score: Keep Practicing!" << endl;

        cout << "Do you want to play again? (Y/N): ";
        cin >> playAgain;

    } while (playAgain == 'Y' || playAgain == 'y');

    cout << "Thank you for playing!" << endl;

    return 0;
}
