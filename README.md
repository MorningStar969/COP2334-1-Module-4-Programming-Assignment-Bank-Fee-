# COP2334-1-Module-4-Programming-Assignment-Bank-Fee
This is a GitHub repository link for the Programming Assignment from Module 4.
// This program is used to determine a bank's service fees for the month.

// Incorporate the header file.
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
  // Declare variables.
  double beginning_balance;
  int numChecks;
  double totalFees;
  double checkFee;
  const int Monthly_Fee = 10.00;
  const double Check20 = .10;
  const double Check39 = .08;
  const double Check59 = .06;
  const double Check60 = .04;

  // Get the beginning balance.
  cout << "Enter the beginning balance: $";
  cin >> beginning_balance;
  // Determine if the account is overdrawn.
  cout << "Enter the number of checks written: ";
  cin >> numChecks;
  // Determine the service fees.
  if (beginning_balance < 0) {
    cout << "Alert! Your account is overdrawn." << endl;
    // Calculate the total fees.
  } else if (numChecks < 0) {
    cout << "Warning: Number of checks must be zero or more." << endl;
  } else {
    // if the number of checks is less than 20, the fee will add to the number of checks multiplied by .10.
    if (beginning_balance < 400) {
      totalFees = Monthly_Fee + 15;
    }
    // if the number of checks is between 20 and 39, the fee will add to the number of checks multiplied by .08
    if (numChecks < 20) {
      checkFee = numChecks * Check20;
      // if the number of checks is between 40 and 59, the fee will add to the number of checks multiplied by .06
    } else if (numChecks >= 20 && numChecks <= 39) {
      checkFee = numChecks * Check39;
      // if the number of checks is 60 or more, the fee will add to the number of checks multiplied by .
    } else if (numChecks >= 40 && numChecks <= 59) {
      checkFee = numChecks * Check59;
      // if the number of checks is 60 or more, the fee will add to the number of checks multiplied by the number of checks.
    } else {
      checkFee = numChecks * Check60;
    }
    // Display the total fees.
    totalFees = Monthly_Fee + checkFee;
    cout << fixed << setprecision(2);
    cout << "The bank's service fees for the month are: $" << totalFees << endl;
    return 0;
  }
}
