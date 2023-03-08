// Cplusplus header
#include <iostream>
#include<string>
using namespace std;
class Student
{
private:
		string name;
		double TotalGrade;
public:
	Student(string);
	string getName();
	double getTotalGrade();
	string getLetterGrade();
	void AddGrade(double);
	double CalcAverage();
};// .cpp second part

#include "Student.h"
#include <iostream>
#include<string>
using namespace std;

Student::Student(string n)
{
	this->name = n;
	this->TotalGrade = 0;
}
string Student::getName()
{
	return this->name;
}
double Student::getTotalGrade()
{
	return this->TotalGrade;
}
void Student::AddGrade(double g)
{
	this->TotalGrade += g;
}
double Student::CalcAverage()
{
    this->TotalGrade = this->TotalGrade / 10;
    return this->TotalGrade;
}
string Student::getLetterGrade() 
{
	string letterGrade;
	double g = this->TotalGrade;
    if (g >= 100)
        letterGrade = "A+";
    else if (g >= 93)
        letterGrade = "A";
    else if (g >= 90 && g < 93)
        letterGrade = "A-";
    else if (g >= 87 && g < 90)
        letterGrade = "B+";
    else if (g >= 83 && g < 87)
        letterGrade = "B";
    else if (g >= 80 && g < 83)
        letterGrade = "B-";
    else if (g >= 77 && g < 80)
        letterGrade = "C+";
    else if (g >= 73 && g < 77)
        letterGrade = "C";
    else if (g >= 70 && g < 73)
        letterGrade = "C-";
    else if (g >= 67 && g < 70)
        letterGrade = "D+";
    else if (g >= 63 && g < 67)
        letterGrade = "D";
    else if (g >= 60)
        letterGrade = "D-";

    else
        letterGrade = "F";

    return letterGrade;
}
// initialization
#include "Student.h"
#include <iostream>
using namespace std;
int main()
{
	string name;
	double grade;
	string letter;
	int i = 1;
	cout << " =======================   Grade Book   ======================" << endl;
	cout << endl;
	cout << " Enter student's name: ";
	getline(cin, name);
	cout << endl;
	Student s1(name);
	while (i <= 10)
	{
		cout << " Enter # " << i<< "  " << s1.getName() << "'s grade : ";
		cin >> grade;
		s1.AddGrade(grade);
		cout << " ============================================================= "<< endl;
		cout << " Student's current grade is : " << s1.getTotalGrade() << endl;
		i++;
	}
	cout << " Student's total grade is : " << s1.getTotalGrade()<< endl;
	cout << " Student's average grade is : " << s1.CalcAverage() << endl;
	cout << " *************************************************************" << endl;
	cout << " >>>>> "<<s1.getName() << "'s FINAL LETTER GRADE is : " << s1.getLetterGrade() <<" <<<<< " << endl;
	cout << " *************************************************************" << endl;

   
}
