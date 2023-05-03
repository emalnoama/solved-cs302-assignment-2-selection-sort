Download Link: https://assignmentchef.com/product/solved-cs302-assignment-2-selection-sort
<br>
<h1>Description</h1>

For this assignment, you will read in a list of random numbers from a file and build a doubly-linked list and perform selection sort on the list, you will need to implement the following linked list class along with its iterator

template &lt;class Type&gt; class LL

{

struct node

{

Type item; node * next; node * prev;

};

public: class iterator

{ public:

friend class LL; iterator(); iterator(node*); Type operator*(); iterator operator++(int); iterator operator–(int); bool operator==(const iterator&amp;) const; bool operator!=(const iterator&amp;) const;

private:

node * current;

};

LL();

LL(const LL&amp;);

const LL&amp; operator=(const LL&amp;);

~LL(); iterator begin() const; iterator end() const; void headRemove(); void tailRemove(); bool isEmpty() const; void headInsert(const Type&amp;); void tailInsert(const Type&amp;); void update(const iterator&amp;, const Type&amp;);

private:

node * head; node * tail;

};

Each member of the LL class contains/performs the following

<ul>

 <li>struct node – will be each member of the linked list, it contains an item, a pointer to the right node, and a pointer to the left node</li>

 <li>node * head – is a pointer that points to the first node in the linked list</li>

 <li>node * tail – is a pointer that points to the last node in the linked list</li>

 <li>LL() – is the default constructor that sets an empty linked list</li>

 <li>LL(const LL&amp;) – is the copy constructor, performs a deep copy of the LL object passed in</li>

 <li>const LL&amp; operator=(const LL&amp;) – is the assignment operator, performs a deep copy of the LL object passed in (the object on the right hand side of the assignment operator)</li>

 <li>~LL() – is the destructor, deallocates the linked list</li>

 <li>iterator begin)_ const – returns an iterator object that points to the first node in the list</li>

 <li>iterator end() const – returns an iterator object that points to the last node in the list</li>

 <li>void headRemove() – removes the front node in the linked list</li>

 <li>void tailRemove() – removes the end node in the linked list</li>

 <li>bool isEmpty() const – returns true if the list is empty and false otherwise</li>

 <li>void headInsert(const Type&amp;) – inserts a new node to the front of the list, sets this node’s item field to the value passed into the function</li>

 <li>void tailInsert(const Type&amp;) – inserts a new node to the end of the list, sets this node’s item field to the value passed into the function</li>

 <li>void update(const iterator&amp;, const Type&amp;) – reassigns a value of the node that the iterator object points to with the value passed in (the second parameter)</li>

</ul>

Each member of the iterator class contains/performs the following

<ul>

 <li>node * current – is a pointer that points to a node in the linked list</li>

 <li>iterator() – default constructor that sets current to NULL</li>

 <li>iterator(node*) – a constructor that sets current to the pointer passed into the function</li>

 <li>Type operator*() – overloads a unary operator, returns the item field of the node object that cuurent points to</li>

 <li>iterator operator++(int) – overloads a unary operator, moves the current pointer over to the next node of the linked list</li>

 <li>iterator operator–(int) – overloads a unary operator, moves the current pointer over to the previous node of the linked list</li>

 <li>bool operator==(const iterator&amp;) const – overloads the binary equals operator, returns true if the iterator on the left side of the operator points to the same node as the iterator on the right side, and returns false otherwise</li>

 <li>bool operator!=(const iterator&amp;) const – overloads the binary equals operator, returns false if the iterator on the left side of the operator points to the same node as the iterator on the right side, and returns false otherwise</li>

</ul>

The iterator object will basically serves as a pointer, you will use it to navigate through the linked list, suppose you create a linked list object of type int, and you inserted content to the front or the back and wish to traverse and print out its contents, the following code can be used

LL&lt;int&gt; list;

LL&lt;int&gt;::iterator it;

//Assuming you inserted nodes into the list at some point

//this loop starts the iterator by setting it to the front of the linked list

//the loop will keep running as long as the iterator hasn’t reached the last node

//it will move to the next node each time for (it = list.begin(); it != list.end(); it++)

{

cout &lt;&lt; *it &lt;&lt; endl; //outputs the value in the node that it points to

}

//since the loop doesn’t output the last node since it stops right when it hits the

//last node, we output it here cout &lt;&lt; *it &lt;&lt; endl;

<h1>Contents of main</h1>

You will be given an input file with a set of integers, you will read through the file and insert each item into the linked list object using the head or tail insert functions. Then you will implement a known sorting algorithm, selection sort. The way this algorithm works is it first finds the max element in the list and then swaps the item with the last element in the list. Then you find the max element in the array (not including the last element), then you swap this max element to the second to last element, and so on until the list is finally sorted. This is not the most efficient sorting algorithm but it works, you would need to have several iterator objects, once to traverse the list, one to point to the current max element, and one at the end (to denote the element to be swapped with once the max is found)

<h1>Specifications</h1>

<ul>

 <li>Comment your code and your functions</li>

 <li>Do not add extra class members or remove class members and do not modify the member functions of the class</li>

 <li>Do not use global variables</li>

 <li>Make sure your program is memory leak free</li>

</ul>

<h1>Example Output</h1>

Once your compile and run, your program should output a sorted list, it would take too many pages of the pdf to output that but you know if your program works: if it outputs a sorted list, then it worked, if not then it didn’t work