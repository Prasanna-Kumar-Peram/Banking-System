#include<stdio.h>
#include<conio.h>
#include<iostream>
using namespace std;
class bank
{
	char name[100],add[100],y;
	int balance;
	public:
		void open_account();
		void deposit_money();
		void withdraw_money();
		void display_account();
};


void bank::open_account()
{
	cout<<"Enter your full name::";
	cin.ignore();
	cin.getline(name,100);
	cout<<"Enter your address::";
	cin.ignore();
	cin.getline(add,100);
	cout<<"What type of account Saving(s)or current(c)::";
	cin>>y;
	cout<<"Enter Deposite amount::";
	cin>>balance;
	cout<<"............YOUR ACCOUNT IS CREATED.................\n";
	}
	void bank::deposit_money()
	{
		int a;
		cout<<"Enter amout to deposit::";
		cin>>a;
		balance+=a;
		cout<<".......Balance in account.......\n"<<"......."<<balance<<".......";
		
	}
	void bank::display_account()
	{
		cout<<"FullName::"<<name;
		cout<<"\nAddess::"<<add;
		cout<<"\nType of account::"<<y;
		cout<<"\nBalnce in acoount::"<<balance<<"\n";
	}
	void bank::withdraw_money()
	{
		float b;
		cout<<".....WITHDRAW.....\n";
		cout<<"Enter amount to with draw::";
		cin>>b;
		if (b<=balance){
			balance-=b;
			cout<<"...b......"<<"\n.....Withdrawn successfully......\n";
		}
		else{
			cout<<"\n.........Insufficient funds........\n";
		}
		
		cout<<".......Balance in your account.......\n"<<"......."<<balance<<".......\n";
	}
	

int main( )
{
	int ch,x;
	bank obj;
	do
	{	
		cout<<"1)Open accout\n";
		cout<<"2)Deposit money\n";
		cout<<"3)Withdraw Money\n";
		cout<<"4)Display Account\n";
		cout<<"5)Exit\n\n"; 
		cout<<"Select option from above>>>>>";
		cin>>ch;
		switch(ch)
		{
			case 1:
				obj.open_account();
				break;
			
			case 2:
				obj.deposit_money();
				break;
			
			case 3:
				obj.withdraw_money();
				break;
			
			case 4:;
				obj.display_account();
				break;
				
			case 5:
				exit(1);
				
			default:
				cout<< "Not exist TRY AGAIN\n";
				
		}
			cout<<"\nif you want to do another transaction then press Y or press N for exit\n";
			x=getch();
			if (x=='n'||x=='N'){
				exit(0);
			}
	}while(x=='y'||x=='Y');	
		
	getch();
	return 0;
}
