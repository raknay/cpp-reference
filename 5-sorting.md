### Sorting
------------
* C++ has inbuilt sorting function to sort arrays, vectors etc.
* Sorting function takes the  pointer to the element from which we want the sorting to start and pointer to the next element of the end element up to which we want to sort(i.e pointer to the 4th element if we want to sort up to including 3rd element).
```cpp
#include <iostream>
#include <vector>
using namespace std;

int main(){
    int arr[5] = {8, 12, 9, 5, 11};
    vector<int> vec {8, 12, 9, 5, 11};

    sort(arr, arr + sizeof(arr)/sizeof(arr[0])); // sort array
    sort(vec.begin(), vec.end()); // sort vector
    
    cout << "Array: ";
    for(int i = 0; i < 5; i++){
        cout << arr[i] << " ";
    }
    cout << endl;

    cout << "Vector: ";
    for(int i = 0; i < 5; i++){
        cout << vec[i] << " ";
    }
    cout << endl;
}
```
**output:**
```
Array: 5 8 9 11 12 
Vector: 5 8 9 11 12 
```
* We can pass comparator functions do define custom sorting behavior.
```cpp
#include <iostream>
#include <vector>
using namespace std;

bool incr(int a, int b){
    if(b > a) return false; // return false if want to swap
    return true;
}

int main(){
    vector<int> vec {8, 12, 9, 5, 11};

    sort(vec.begin(), vec.end(), incr); // sort vector

    for(int i = 0; i < 5; i++){
        cout << vec[i] << " ";
    }
    cout << endl;
}
```