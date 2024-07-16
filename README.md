# Data Structures in Python:
<ul>
  <li><a href="#Built-in DS">Built-in DS</a>
      <ul>
          <li><a href="#List">List</a></li>
          <li><a href="#Tuple">Tuple</a></li>
          <li><a href="#Set">Set</a>
            <ul>
              <li><a href="#frozenset">frozenset</a></li>
              <li><a href="#collections.Counter">collections.Counter</a></li>
            </ul>    
          </li>
          <li><a href="#Dictionary">Dictionary</a>
            <ul>
              <li><a href="#dict() Constructor">dict() Constructor</a></li>
              <li><a href="#collections.OrderedDict">collections.OrderedDict</a></li>
              <li><a href="#collections.defaultdict">collections.defaultdict</a></li>
              <li><a href="#collections.ChainMap">collections.ChainMap</a></li>
            </ul>    
          </li>
      </ul>
  </li>
  <li><a href="#User-defined DS">User-defined DS</a>
    <ul>
      <li><a href="#Arrays">Arrays</a>      
        <ul>
         <li><a href="#array.array">array.array</a></li>
         <li><a href="#str">str</a></li>
         <li><a href="#byte">byte</a></li>
         <li><a href="#bytearray">bytearray</a></li>
        </ul>
      </li>
      <li><a href="#Stack">Stack</a></li>
      <li><a href="#Queue">Queue</a>
        <ul>
          <li><a href="#queue.Queue">queue.Queue</a></li>
          <li><a href="#collections.deque">collections.deque</a></li>
          <li><a href="#Priority queue">Priority queue</a>
            <ul>
              <li><a href="#heapq">heapq</a></li>
            </ul>
          </li>
        </ul>
      </li>  
    </ul>
  </li>
</ul>
## Bulit-in DS:
<li>List</li>
<li>Tuple</li>
<li>Set</li>
<li>Dictionary</li>

## User-defined DS:
<li>Arrays</li>
<li>Stack</li>
<li>Queue</li>

## Built-in DS:
## List:
Lists are a versatile and widely-used data structure that can store a collection of items in an ordered and mutable sequence.
```
my_list = [1, 2, 3, 'a', 'b', 'c']
print(my_list[0])
```
## Tuple:
Tuple objects are immutable. This means elements can’t be added or removed dynamically—all elements in a tuple must be defined at creation time.
```
my_tuple = (1, 2, 3, 'a', 'b', 'c')
print(my_tuple[0])  
print(my_tuple[3])
```
## Set:
A set is an unordered collection of unique elements. Sets are useful to store a collection of items and there should be no duplicates.
```
my_set = {1, 2, 3, 'a', 'b', 'c'}
print(my_set)
```
### frozenset: 
The frozenset class implements an immutable version of set that can’t be changed after it’s been constructed.
```
my_frozenset = frozenset([1,2,3,4,'a','b'])
print(my_frozenset)
```
### collections.Counter(Multisets):
The collections.Counter class in the Python standard library implements a multiset, or bag, type that allows elements in the set to have more than one occurrence.
```
from collections import Counter
my_list = ['a', 'b', 'c', 'a', 'b', 'a']
counter = Counter(my_list)
print(counter)
```
## Dictionary:
Dictionaries are also often called maps, hashmaps, lookup tables, or associative arrays.They are ordered and key are immutable but values are mutable and don't allow duplicates.Dictionaries are used to store data values in key:value pairs.Values in dictionary items can be of any data type.
### dict() Constructor:
```
a = dict(name = "John", age = 36, country = "Norway")
print(a)
```
### collections.OrderedDict:
Python includes a specialized dict subclass that remembers the insertion order of keys added to it: collections.OrderedDict.
```
from collections import OrderedDict
ordered_dict = OrderedDict()
ordered_dict['first'] = 1
ordered_dict['second'] = 2
ordered_dict['third'] = 3
print(ordered_dict)
```
### collections.defaultdict:
The defaultdict class is another dictionary subclass that accepts a callable in its constructor whose return value will be used if a requested key cannot be found.
```
from collections import defaultdict
default_dict = defaultdict(int)
default_dict['a'] += 1
default_dict['b'] += 2
default_dict['a'] += 3
print(default_dict)
```
### collections.ChainMap:
The collections.ChainMap data structure groups multiple dictionaries into a single mapping.
```
from collections import ChainMap
dict1 = {'a': 1, 'b': 2}
dict2 = {'b': 3, 'c': 4}
chain_map = ChainMap(dict1, dict2)
print(chain_map)
print(chain_map['a'])  
print(chain_map['b'])  
```
## User-defeined DS:
## Arrays:
Arrays consist of fixed-size data records that allow each element to be efficiently located based on its index.
### array.array:
Arrays created with the array.array class are mutable and behave similarly to lists except for one important difference: they’re typed arrays constrained to a single data type.
```
import array
int_array = array.array('i', [1, 2, 3, 4, 5])
print(int_array)
```
### str: 
Python uses str objects to store textual data as immutable sequences of Unicode characters. str is an immutable array of characters.
```
my_list = ['apple', 'banana', 'cherry', 'date']
print(my_list[2])
```
### byte:
bytes objects are immutable sequences of single bytes, or integers in the range 0 ≤ x ≤ 255.byte objects are immutable.
```
bytes_data = b'Hello'
print(bytes_data)  
print(bytes_data[0])
```
### bytearray:
The bytearray type is a mutable sequence of integers in the range 0 ≤ x ≤ 255.The main difference being that a bytearray can be modified freely—you can overwrite elements, remove existing elements, or add new ones.
```
bytes_data = b'Hello'
byte_array = bytearray(bytes_data)
print(byte_array[0])
```
## Stack:
A stack is a collection of objects that supports fast Last-In/First-Out (LIFO)  for insertion and deletion.The insert and delete operations are also often called push and pop.
```
stack = []
stack.append(1)
stack.append(2)
stack.append(3)
print(stack)  
top = stack.pop()
print(top)    
print(stack)  
```
## Queue:
A queue is a collection of objects that supports fast FIFO  for insertion and deletion. The insert and delete operations are sometimes called enqueue and dequeue. With a queue, you remove the item least recently added (FIFO) but with a stack, you remove the item most recently added (LIFO).
### queue.Queue
The queue.Queue implementation in the Python standard library is synchronized and provides locking semantics to support multiple concurrent producers and consumers.
```
from queue import Queue
q = Queue()
q.put("eat")
q.put("sleep")
q.get()
```
### collections.deque:
The collections.deque class in Python is a double-ended queue that allows you to append and pop elements from both ends with O(1) performance. 
```
from collections import deque
q = deque()
q.append("eat")
q.append("sleep")
q.popleft()
```
### Priority queue:
A priority queue is a container data structure that manages a set of records with totally-ordered keys to provide quick access to the record with the smallest or largest key in the set.
### heapq
heapq is a binary heap implementation usually backed by a plain list, and it supports insertion and extraction of the smallest element in O(log n) time.
```
import heapq
q = []
heapq.heappush(q, (2, "code"))
heapq.heappush(q, (1, "eat"))
heapq.heappush(q, (3, "sleep"))
while q:
  next_item = heapq.heappop(q)
  print(next_item)
```


