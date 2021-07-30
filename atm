#include <iostream>
#include <string>
#include <fstream>
#include <vector>
using namespace std;


int pinCheck;
int pin;
string name;
int balance;
bool run = true;
bool userLoggedIn = false;
char login;
char newUser;
char transaction;
int depositAmount;
int withdrawlAmount;
char logout;
vector<string> names;
vector<int> pins;
vector<int> balances;
int userIndex;
string nameCheck;


void loginScreen();
void loggedIn();
void saveUser(string user, int password);
void saveBalance(int balance);
void deposit();
void withdrawl();
void createUser();
void checkPin();



int main() {
	loginScreen();
}
					 




void loginScreen() {
	system("cls");
	cout << "\n\n\t\t========Welcome to C++ Bank ATM========";
	cout << "\n\t\tPress Enter to get started.. ";
	cin.get();

	//Prints out usernames and passwords and balances
	//cout << "\n";
	//for (int i = 0; i < names.size(); ++i) {
		//cout << names[i] << ", " << pins[i] << ", " << balances[i] << endl;
	//}

	cout << "\n\t\tDo you already have an account? Y/N ";
	checkPin();
}	

void loggedIn() {
	system("cls");
	cout << "\n\n\t\t========Welcome " << names[userIndex] << "========";
	cout << "\n\t\tYour balance is : $" << balances[userIndex];
	cout << "\n\n\t\tEnter \"D\" for deposit or \"W\" for withdrawl or \"L\" to Logout: ";
	cin >> transaction;
	if(transaction == 'D' || transaction == 'd') {
		deposit();
		loggedIn();
	} else if(transaction == 'W' || transaction == 'w') {
		withdrawl();
		loggedIn();
	} else if(transaction == 'L' || transaction == 'l') {
		userLoggedIn = false;
		loginScreen();
		cin.ignore();
	} else {
		loggedIn();
	}
}

void saveUser(string user, int password) {
	names.insert(names.begin(), name);
	pins.insert(pins.begin(), pin);
	balances.insert(balances.begin(), 0);
}

void deposit() {
	cout << "\n\n\t\tEnter the amount you would like to deposit(whole numbers only) : $";
	cin >> depositAmount;
	balances[userIndex] += depositAmount;
	cout << "\n\n\t\tYour new balance is : $" << balances[userIndex];
	cout << "\n\n\t\tPress Enter to continue...";
	cin.ignore();
	cin.get();
	loggedIn();
}

void withdrawl() {
	cout << "\n\n\t\tEnter the amount you would like to withdrawl(whole numbers only) : $";
	cin >> withdrawlAmount;
	if(withdrawlAmount > balances[userIndex]) {
		cout << "\n\t\tInsufficient Balance! Press enter to try again..";
		cin.ignore();
		cin.get();
		withdrawl();
	}
	balances[userIndex] -= withdrawlAmount;
	cout << "\n\n\t\tYour new balance is : $" << balances[userIndex];
	cout << "\n\n\t\tPress Enter to continue...";
	cin.ignore();
	cin.get();
	loggedIn();
}

void createUser() {
	cout << "\n\t\tPlease enter a Username(case sensitive) : ";
	cin >> name;
	for(int i = 0; i < names.size(); ++i) {
		if(name == names[i]){
			cout << "\n\t\tUsername taken, Press enter to try again..";
			cin.ignore();
			cin.get();
			name = "";
			createUser();
		}
	}
	cout << "\n\t\tPlease enter a 4-6 digit Pin : ";
	cin >> pin;
	cout << "\n\t\tThank you for joining C++ Bank!";
	cout << "\n\t\tPress Enter to continue...";
	saveUser(name, pin);
	cin.ignore();
	cin.get();
	loginScreen();
}


void checkPin() {
	cin >> newUser;
	if(newUser == 'Y' || newUser == 'y') {
		cout << "\n\t\tEnter your Username : ";
		cin >> nameCheck;
		cout << "\t\tEnter your Pin # :";
		cin >> pinCheck;

		for(int i = 0; i < pins.size(); ++i) {
			if(pinCheck == pins[i] && nameCheck == names[i]) {
				userIndex = i;
				loggedIn();
			}
		}
		cout << "\n\n\t\tIncorrect Pin!";
		cout << "\n\t\tPress Enter to continue...";
		cin.ignore();
		cin.get();
		loginScreen();
	} else if(newUser == 'N' || newUser == 'n') {
		createUser();
	} else {
		loginScreen();
	}
}
