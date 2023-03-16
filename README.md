#include <iostream>
#include <time.h>
#include <stdlib.h>
using namespace std;

int num;

void printStatement (int a, int b) {
    if (b != a) num--;
    if (b < a) cout<<"Your number is smaller! Try again!";
    else if (b > a) cout<<"Your number is bigger! Try again!";
    else {
        cout<<"You are correct!\n";
        cout<<"Your score: "<<num;
    }
    cout<<endl;
}

int main() {
    ios_base::sync_with_stdio(false);
    cin.tie(0);
    srand(time(0));
    string s;
    do {
        int secret = rand()%100+1, number;
        cout<<"Guess my number, please?"<<endl;
        num = 100;
        do {
            cin>>number;
            printStatement(secret, number);
        } while (number != secret);
        cout<<"Do you want to play again? Press Yes to continue!"<<endl;
        cin>>s;
    } while (s == "Yes");
}
