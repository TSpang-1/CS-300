A vector is pretty simple to work with and can load data quickly because inserting items at the end is constant time. This makes it easier to store and display the course information. However, searching for a specific course in a vector is slower since it does require scanning through the entire list, and the vector does not stay sorted automatically. A separate sorting step would be needed every time the program needs to print the course list alphabetically. 

A hash table and a binary search tree offer much faster ways to search for courses, but each one comes with disadvantages. A hash table provides the fastest lookup time on average, making it the best for pulling up course information quickly, although it does not keep the alphabetical order and does use more memory. A binary search tree, or BST, naturally keeps the courses sorted and allows for more efficiency with searching when the tree is balanced, but inserting courses is slower than a vector or hash tables, and the performance can drop significantly if the tree is not balanced properly. 

For the ABCU advising program, the hash table is the best choice overall. The advisors need to be able to quickly look up individual courses by courseNumber and generate a list of all the courses. A hash table provides O(n) loading time on average and O(1) average lookup time for certain courses, which makes the searching much more efficient. Although it does not store the courses in sorted order automatically, we can still make an alphanumeric list by collecting all of the course numbers and sorting them which runs in O(n log n) time. This combination of fast lookup and a reasonable sorting performance makes a hash table the best fit for the program’s requirements. 

| Step | Operation                       | Cost per Execution | # of Executions |
|------|----------------------------------|---------------------|------------------|
| 1    | Open the file                    | 1                   | 1                |
| 2    | Read line from file              | 1                   | n                |
| 3    | Check if line is empty           | 1                   | n                |
| 4    | Split line into tokens           | 1                   | n                |
| 5    | Loop through prerequisites       | 1                   | n * p            |
| 6    | Create a Course object           | 1                   | n                |
| 7    | Load into Vector                 | 1                   | n                |
| 8    | Load into Hash Table             | 1(hash) + 1(insert) | n                |
| 9    | Load into BST                    | log n               | n                |

