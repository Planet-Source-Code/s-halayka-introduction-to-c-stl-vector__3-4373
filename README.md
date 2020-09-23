<div align="center">

## Introduction to C\+\+ STL vector


</div>

### Description

Introduction to C++ STL vector - a C++ standard class that acts similarily to a C array. No 3rd party classes, this is all standard among every standards compliant C++ compiler!

The major benefit to the vector is that it is dynamic in size. You can add to it, remove from it, and not have to worry about handling the memory yourself. Very useful.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[S Halayka](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/s-halayka.md)
**Level**          |Beginner
**User Rating**    |5.0 (15 globes from 3 users)
**Compatibility**  |C\+\+ \(general\), Microsoft Visual C\+\+, Borland C\+\+, UNIX C\+\+
**Category**       |[Data Structures](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/data-structures__3-8.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/s-halayka-introduction-to-c-stl-vector__3-4373/archive/master.zip)





### Source Code

<pre><code><font color="#000000">
<font color="#008000">// on linux, compile with g++, or use the -lstdc++ switch on gcc</font>
<font color="#008000">#include <iostream> // for cout</font>
<font color="#008000">#include <vector> // for vector</font>
<font color="#0000ff">using namespace</font> std;
<font color="#0000ff">int</font> main(<font color="#0000ff">void</font>)
{
 <font color="#008000">// a vector is very similar to a standard C array</font>
 <font color="#008000">// one key difference is that a vector has dynamic size</font>
 <font color="#008000">// this means that you can add and delete items from it in a very simple fashion</font>
 <font color="#008000">// as you work with the vector, it handles all of the necessary memory management for you</font>
 <font color="#008000">// this allows you to focus on the more important parts of your programming task</font>
 <font color="#008000">//</font>
 <font color="#008000">//</font>
 <font color="#008000">// here are some of the various useful member functions of a vector:</font>
 <font color="#008000">//</font>
 <font color="#008000">// push_back() - adds an item to the end of the vector</font>
 <font color="#008000">// insert() - adds an item (or range of items) at a specified spot in the vector</font>
 <font color="#008000">// pop_back() - removes the item at the end of the vector</font>
 <font color="#008000">// erase() - removes the item (or range of items) at a specified spot in the vector</font>
 <font color="#008000">// size() - tells how many items are currently stored in the vector</font>
 <font color="#008000">// clear() - clears all items currently stored in the vector</font>
 <font color="#008000">// operator [] - the familiar brackets, used in the same manner as with standard C arrays, to access items</font>
 <font color="#008000">// create a vector container object - it will store ints in this example</font>
 <font color="#008000">// however, a vector can store almost any type of object</font>
 <font color="#008000">// from int and char, to string and custom classes, even other vectors (for a multi-dimensional vector)!</font>
 vector<<font color="#0000ff">int</font>> IntVector;
 <font color="#008000">// add an integer (value 24) to the end of the vector</font>
 IntVector.push_back(<font color="#0000ff">24</font>);
 <font color="#008000">// print out the current number of ints contained inside our vector</font>
 cout << <font color="#800000">"After push_backing one item, the vector's size is: "</font> << IntVector.size() << endl;
 <font color="#008000">// remove the element at the end of the vector</font>
 IntVector.pop_back();
 <font color="#008000">// print out the current number of ints contained inside our vector</font>
 cout << <font color="#800000">"After pop_backing one item, the vector's size is: "</font> << IntVector.size() << endl;
 cout << endl;
 <font color="#008000">// a variable we will use with our for loops</font>
 <font color="#0000ff">unsigned short</font> counter = <font color="#0000ff">0</font>;
 <font color="#008000">// let's add 10 items to the vector, inserting each at the beginning of the vector, instead of the end</font>
 <font color="#008000">// the first item we will add is 0, the final item we will add is 9</font>
 <font color="#0000ff">for</font>(counter = <font color="#0000ff">0</font> ; counter < <font color="#0000ff">10</font> ; counter++)
 {
  <font color="#008000">// the first parameter, IntVector.begin(), indicates to add the new item at the very beginning of the vector</font>
  <font color="#008000">// the second parameter, counter, indicates the variable (value) we wish to add to the vector</font>
  IntVector.insert( IntVector.begin(), counter);
 }
 <font color="#008000">// print out the current number of ints contained inside our vector</font>
 cout << <font color="#800000">"After inserting 10 items, the vector's size is: "</font> << IntVector.size() << endl;
 <font color="#008000">// print out the vector's current contents, item by item</font>
 <font color="#008000">// we will start with item 0 (like a standard C array)</font>
 <font color="#008000">// we will want to stop at item 9 (like a standard C array)</font>
 <font color="#008000">// notice the output starts at 9 and decreases from there</font>
 <font color="#008000">// this is because we added the items in our previous loop to the beginning of the vector, and not to the end</font>
 <font color="#0000ff">for</font>(counter = <font color="#0000ff">0</font> ; counter < IntVector.size() ; counter++)
 {
  <font color="#008000">// we use IntVector[counter] to access an item's value, just like a standard C array</font>
  cout << <font color="#800000">"Item "</font> << counter << <font color="#800000">" contains: "</font> << IntVector[counter] << endl;
 }
 cout << endl;
 <font color="#008000">// let's erase item 6</font>
 <font color="#008000">// we only pass one parameter to erase, since we are deleting only one item</font>
 <font color="#008000">// this parameter indicates which item to delete</font>
 IntVector.erase( IntVector.begin() + <font color="#0000ff">6</font> );
 <font color="#008000">// print out the current number of ints contained inside our vector</font>
 cout << <font color="#800000">"After erasing one item, the vector's size is: "</font> << IntVector.size() << endl;
 <font color="#008000">// let's erase items 0-3. note: that is 4 items to be deleted</font>
 <font color="#008000">// we pass two parameters this time, the first indicates the item position to begin erasing at</font>
 <font color="#008000">// the second parameter indicates the item position to stop deleting at (this item does not get erased)</font>
 IntVector.erase( IntVector.begin(), IntVector.begin() + <font color="#0000ff">4</font> );
 <font color="#008000">// print out the current number of ints contained inside our vector</font>
 cout << <font color="#800000">"After erasing four more items, the vector's size is: "</font> << IntVector.size() << endl;
 <font color="#008000">// print out the current vector contents</font>
 <font color="#0000ff">for</font>(counter = <font color="#0000ff">0</font> ; counter < IntVector.size() ; counter++)
 {
  <font color="#008000">// we use IntVector[counter] to access an item's value, just like a standard C array</font>
  cout << <font color="#800000">"Item "</font> << counter << <font color="#800000">" contains: "</font> << IntVector[counter] << endl;
 }
 <font color="#008000">// clear the vector</font>
 <font color="#008000">// note: it is not necessary to clear the vector when you are finished using it</font>
 <font color="#008000">// all memory deallocation is handled automatically</font>
 <font color="#008000">// </font>
 <font color="#008000">// it is only necessary when you want to erase everything inside of it and start out fresh</font>
 IntVector.clear();
 <font color="#008000">// print out the current number of ints contained inside our vector</font>
 cout << <font color="#800000">"After clearing the vector, the vector's size is: "</font> << IntVector.size() << endl;
 <font color="#0000ff">return 1</font>;
}
</font>
</code></pre>

