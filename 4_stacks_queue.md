### Stacks And Queue
---------------------
* Stacks are data structure where last element added to the stack is removed first. 
* For example, if there is a stack of book, we can place place a new book on the top of the stack and remove the book which is at the top of the stack.
* Queues are data structures where first element added to the queue is removed first.
* For example, if people are waiting in a queue then the person who stands in the front of the queue would be served are relived first.
```cpp
stack<int> s;
s.push(1); // pushes elements to the top stack
s.push(2);
s.push(3);
while (!s.empty())
{
    cout << s.top() << endl; // returns the top(last pushed) element
    s.pop(); // removes the (last pushed) top element of stack
}

queue<string> q;
q.push("abc"); // pushes elements to the end of queue
q.push("def");
q.push("ghi");

while (!q.empty())
{
    cout << q.front() << endl; // returns the top(last pushed) element
    q.pop(); // removes the (last pushed) top element of stack
}
```
