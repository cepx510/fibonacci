
/*
This short code prints Fibonacci sequence based on user controlled index.
By Sergey Dusheyko
*/

/*
In the programming language of your choice, write a program 
generating the first n Fibonacci numbers F(n), printing ...
- ... "Buzz" when F(n) is divisible by 3.
- ... "Fizz" when F(n) is divisible by 5.
- ... "BuzzFizz" when F(n) is prime.
- ... the value F(n) otherwise.
*/


#include <iostream>
#include <string>

using namespace std;
void fibonacci();



void main( )
{

	fibonacci();


}

/*
This function asks the user to input number to increment Fibonacci sequence to.
*/
void fibonacci()
{

	int numIndex; //holds index
	int fibNum; //value at current sequence
	int fibNum1=0; // number at F(n-2) initialized to 0
	int fibNum2=1; //number at F(n-1) initialized to 1
	int ans; //holds user response to question

	//user prompt and answer 
	cout << "For Fibonacci sequence F(n), enter index n you would like to increment to: (max 43)" << endl;

	cin >> numIndex;

	if(numIndex>=44) 
	{
		cout<<endl<<"Too big a sequence, 43 max, try again"<<endl;
		fibonacci();
		cout<<endl<<endl;

	}
		

	//outputs first two in sequence
	cout <<endl<<fibNum1<<endl<<endl<<fibNum2<<endl;

	//increment through sequence until limit is reached
	for(int i=0; i<=numIndex; i++)
	{


		fibNum= fibNum1+fibNum2;

		fibNum1 = fibNum2;
		fibNum2 = fibNum;

		/*
		- ... "Buzz" when F(n) is divisible by 3.
		- ... "Fizz" when F(n) is divisible by 5.
		- ... "BuzzFizz" when F(n) is prime.
		- ... the value F(n) otherwise.
		*/

		if(fibNum%3==0) cout<<endl<<"Buzz"<<endl;
		else if(fibNum%5==0) cout<<endl<<"Fizz"<<endl;

		//first primes in sequence are 2, 3, 5, 13, 89, 233, 1597, 28657, 514229, 433494437, 2971215073,
		else if(fibNum == 2|| fibNum == 3 || fibNum == 5 
			|| fibNum ==13 || fibNum == 89
			||fibNum ==233 || fibNum == 1597 ||fibNum == 28657
			||fibNum == 514229||fibNum == 433494437||fibNum == 2971215073)

				cout<<endl<<"BuzzFizz"<<endl;
			
		else	cout <<endl<<fibNum<<endl;

		if(fibNum<0) cout<<endl<<endl<<i<<endl<<endl;



	}



}












