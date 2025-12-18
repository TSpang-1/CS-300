#include <iostream>
#include <fstream>
#include <sstream>
#include <vector>
#include <string>
#include <algorithm>
#include <cctype>

using namespace std;

// Course structure to hold course information
struct Course
{
    string courseNumber;
    string courseTitle;
    vector<string> prerequisites;
};


// Comparison function for sorting courses by courseNumber
bool compareCourses(const Course &a, const Course &b)
{
    return a.courseNumber < b.courseNumber;
}

// Print all courses in alphanumeric order
void printCourseList(HashTable &courseTable)
{
    vector<Course> courses;
    courseTable.getAllCourses(courses);

    if (courses.empty())
    {
        cout << "No courses to display." << endl
             << endl;
        return;
    }

    sort(courses.begin(), courses.end(), compareCourses);

    cout << "Here is a sample schedule:" << endl
         << endl;

    for (size_t i = 0; i < courses.size(); ++i)
    {
        cout << courses[i].courseNumber << ", " << courses[i].courseTitle << endl;
    }

    cout << endl;
}


// In my full program, the vector 'courses' is populated by retrieving all 
// Course objects from the hash table after loading the input file. 
// Assume that 'courses' already has Course objects.
