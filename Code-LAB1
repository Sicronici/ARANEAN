
#include <iostream>
#include <limits>

// LABORATORY WORK NO.1

void C()
{
std::cout << "Adjutant: Function C has been called by Function A \n";
}

void B()
{
std::cout << "Adjutant: Function B has been called by Function A \n";
}

void A()
{
std::cout << "Adjutant: Function A has been called along side the other Functions \n";
B();
C();
}

void doPrint()
{
std::cout << "In doPrint()\n";
}

int main()
{

	std::cout << "Adjutant: Stasis Offline \n";
	int x = 7;
	std::cout << "Adjutant: " << STATUS(x) << " \n";

	A();

	std::cout << "Adjutant: Please input a number that will be doubled and trippled... \n";

	int generic_number{ };
	//s td::cin >> generic_number;

	//generic_number *= 2;
	//std::cout << "Adjutant: the multiplied number now is " << generic_number << " \n";

	//int multipled_number{ generic_number * 2 };
	//std::cout << "Adjutant: the multiplied number now is " << multipled_number << "\n";

	//std::cout << "Adjutant: the doubled number now is... " << generic_number * 2 << " \n";
	//std::cout << "Adjutant: the trippled number now is... " << generic_number * 3 << " \n";

	std::cout << "The sum of 3 and 4 is " << add(3, 4) << " \n";



	std::cin.clear(); // reset any error flags
	std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n'); // ignore any characters in the input buffer until we find a newline
	std::cin.get(); // waits for the user to press enter

	return 0;
}
