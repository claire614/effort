# effort

// proj.cpp: 定义控制台应用程序的入口点。
//

#include "stdafx.h"
#include <iostream>
#include <typeinfo>

using namespace std;


double fun(char *s)
{
	char *r = s, *p = s;
	double sum_d1 = 0.0 + *r - '0'; //初试值是第一位的值,用来计算整数部分值
	double sum_d2 = 0.0; //从后往前，用来计算小数点后的值
	r += 1;//指针往后移一个
	while (*r != '.')
	{
		sum_d1 = sum_d1 * 10.0 + *r - '0';
		r++;
	}
	cout << sum_d1 << endl;

	while (*p != '\0')
		p++; //找到字符串末尾指针
	p -= 1;
	sum_d2 = 0.0; //初始值是最后一位的值,从后往前，用来计算小数点后的值
	while (*p != '.')
	{
		sum_d2 = sum_d2 * 0.10 + *p - '0';
		--p;
	}
	sum_d2 *= 0.1;
	cout << sum_d2 << endl;
	/*
	cout << *r << endl; 
	r -= 1;
	cout << *r << endl;
	cout << typeid(*r).name() << endl;
	cout << *r - '0' + 0.0 << endl;
	cout << typeid( 0.0 + *r - '0' ).name() << endl;
	*/
	return sum_d1 + sum_d2;
}


int main()
{
	char *s = NULL;
	s = (char *)malloc(sizeof(char) * 100);//分配内存空间
	cin >> s;

	fun(s);
	

	int i; cin >> i;
    return 0;
}
// int m; cin >> m;
/*
char *r = s;
cout << *r << endl;
cout << typeid(*r).name() << endl;
cout << *r - '0' << endl;
cout << typeid(*r - '0').name() << endl;
//cout << fun(s) << endl;
*/
