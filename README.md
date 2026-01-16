#include <iostream>
using namespace std;

int main()
{
    int n;
    cout << "Press any following key" << endl;
    cout << "Enter Total Students : ";
    cin >> n;

    string names[n];
    int marks[n][3];   // English, Math, Computer
    int total[n];

    // Input student data
    for (int i = 0; i < n; i++)
    {
        cout << "Enter Student Name : ";
        cin >> names[i];

        cout << "Enter English Marks (Out Of 100) : ";
        cin >> marks[i][0];

        cout << "Enter Math Marks (Out Of 100) : ";
        cin >> marks[i][1];

        cout << "Enter Computer Marks (Out Of 100) : ";
        cin >> marks[i][2];

        total[i] = marks[i][0] + marks[i][1] + marks[i][2];
        cout << "*********************************************" << endl;
    }

    // Sort students by total marks (descending)
    for (int i = 0; i < n - 1; i++)
    {
        for (int j = i + 1; j < n; j++)
        {
            if (total[i] < total[j])
            {
                swap(total[i], total[j]);
                swap(names[i], names[j]);
                for (int k = 0; k < 3; k++)
                {
                    swap(marks[i][k], marks[j][k]);
                }
            }
        }
    }

    // Display report card
    cout << "****************Report Card*******************" << endl;
    for (int i = 0; i < n; i++)
    {
        cout << "****************************************" << endl;
        cout << "Student Name: " << names[i]
             << ", Position: " << i + 1
             << ", Total: " << total[i] << "/300" << endl;
    }
    cout << "****************************************" << endl;

    return 0;
}
