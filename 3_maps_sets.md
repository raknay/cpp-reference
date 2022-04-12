### Map
----------
* Maps are type of data structure which stores data in key value format.
* Maps store key-value in a sorted order and sorting is done with respect to keys. As order matters so time complexity for insertion,
deletion or finding a key value pair is O(log(n))
* There is another kind of map called Unordered maps which also store key-value but doesn't follow any order.
* Each element of a map is represented as a `pair` and elements in map don't get stored in continuous memory blocks like `vector`.
```cpp
#include <iostream>
#include <utility>
#include <map> // to define map
using namespace std;

map<int, string> m;
m[1] = "a";
m.insert({2, "b"});
m.insert(make_pair(3, "c"));
cout<< m.size() << endl; // prints size of the map

map<int, string>::iterator it; // iterator for map
for(it = m.begin(); it != m.end(); ++it){
    cout << "Key: " << (*it).first << " Value: " << (*it).second << endl;
}
// range based loop can be used too as follow
for(auto& p : m){
    cout << "Key: " << p.first << " Value: " << p.second << endl;
}
```
**output:**
```
Key: 1 Value: a // prints in sorted order with respect to key
Key: 2 Value: b
Key: 3 Value: c
```
* All the keys are unique(duplicate keys are not allowed). If we try to assign value to an existing key, then new value will replace the old value of the key.
* There are may functions provided for to manipulate maps. `map_name.find(key)` returns an iterator and if the key isn't present then returns `map_name.end()`
* `map_name.erase(key/iterator)` function takes a key or iterator as input and removes the corresponding key-value pair from a map.
```cpp
map<int, string> m;
m[1] = "a";
m[2] = "b";
m[3] = "c";
m[4] = "d";

auto it = m.find(8);
if (it == m.end()){
    cout << "Pair Not Present" << endl;
} else {
    cout << "Key: " << (*it).first << " Value: " << (*it).second << endl;
    m.erase(it); // remove the key-value iterator points to
}
// m.erase(1) removes key 1 and it's associated value
```
#### Unordered Map
* Unordered maps doesn't store key-value pair in sorted order so the time complexity for insertion, find or deletion has time 
complexity of O(1).
* Unordered maps doesn't support few data types as keys such as `pair`, `vector`, `set` etc.
* If order doesn't matter and data type is a valid key for unordered map, then unordered maps are suitable as it's operations takes less time than general maps.
* Syntax to define a unordered map where key is int and value is string is `unordered_map<int, string> m;`.

### Set
-------------
* Set is the collection of unique elements and are stored in sorted order. We can keep complex data types such as `pair`,`vector`, `set` etc.
```cpp
set<string> s;
s.insert("a"); // log(n)
s.insert("d");
s.insert("b");
s.insert("a");
s.insert("c");

for(auto ele : s){ // prints a b c d in order and a is printed once even though it is inserted once
    cout << "Value: " << ele << endl;
}

auto it = s.find("a"); // log(n)
if (it == s.end()){
    cout << "Value Not Present" << endl;
} else {
    cout << "Value: " << (*it)<< endl;
}
```
* We can use `set_name.erase(value/iterator)` to erase a value from a set. We have to pass the value or iterator (which points to a value).
#### Unordered Set
* Unordered set is similar to sets but here order doesn't matters and the time complexity is O(1) for operations for unordered sets.
* We can not keep complex data types such as `pair`, `set` etc in unordered set.
* Syntax to define an unordered set of strings is `unordered_set<string>`.
* Unordered set provide only forward iterators as there is no order is maintained, so only `++` operand can be used on the iterators. 
#### Multiset
* Multiset stores values in sorted order and allows duplicate values in the set.
* While removing a value from a multiset if we pass the value directly to `erase()` function, it will remove all the occurrences of the value and if we pass iterator, it will only remove the value that the iterator points to.
* The syntax for declaring a multiset for string is `multiset<string> s;`.


