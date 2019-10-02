# diskretka
#include <iostream>
using namespace std;

int main()
{
	setlocale(LC_CTYPE, "ukr");
	for (double x = 0.6283;x <= 3.1415;x += 0.25132)
	{
		long double i = cos(x);
		long double r = cos(x);
		for (int n = 2; n <= 10; n++)
		{	
			i += pow((2*n - 1) / (2*n + 1), 2) * cos(2*n + 1) / cos(2*n - 1);
		}
		for (int n = 2; n <= 10; n++)
		{
			double e = pow(2 * n - 1, 2) / cos(2 * n - 1) / x;
			if (e > 0.0001)
			{
				e = pow(2 * n - 1, 2) / cos(2 * n - 1) / x;
	            r += pow((2 * n - 1) / (2 * n + 1), 2) * cos(2 * n + 1) / cos(2 * n - 1);
			}
		}
		double b = pow(3.1415, 2) / 8 - 3.1415 * x / 4;

		cout << "а) для заданого n: " << i << endl <<"б) для заданої точностi e (e=0.0001): " <<r << endl <<"точне значення функцiї: " << b << endl;
	}
	return 0;
}
