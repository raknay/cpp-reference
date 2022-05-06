### Random
* Running code with the help of code runner:-
    * Go to `Code runner Setting -> executor map -> edit in json` then find the `cpp` key and replace the value with the following command
    `"cd $dir && g++ -std=c++17 $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt"`.  
* Calculation precedence from lower to higher
  `char -> int -> long int -> long long int -> float -> double`
* Overflow should be checked for data type.

### Pass By Value & Pass By Reference
```cpp
#include <iostream>
using namespace std;

int main(){
    int a = 5;
    int b = a; // copy value of a to b
    a++; // increasing a won't affect b
    cout << "a: "<< a << " b: "<< b << endl; // prints: a: 6 b: 5

    int& c = a; // c holds reference to a
    c++; // increasing c would increase the value of a
    cout << a << endl; // prints: 7
}
```
#### Implementing swap function with references
* If we don't use references then only copy of original would be passed to the function and it won't affect the variables outside the function.
```cpp
int main(){
    int a = 5;
    int b = 10;
    cout << "a: " << a << " b: " << b << endl; // a: 5 b: 10
    swap(a, b);
    cout << "a: " << a << " b: " << b << endl; // a: 10 b: 5
}

void swap(int& a, int& b){
    int temp = a;
    a = b;
    b = temp;
}
```
* Arrays are always passed by reference even if we don't explicitly use `&` notation. After passing an array to a function, if the contents of the array is modified inside the function, it will also reflect outside the function.