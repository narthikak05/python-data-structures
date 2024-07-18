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
          <li><a href="#dict-Constructor">dict() Constructor</a></li>
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
      <li><a href="#Stack">Stack</a>
        <ul>
          <li><a href="#queue.LifoQueue">queue.LifoQueue</a></li>
        </ul>
      </li>
      <li><a href="#Queue">Queue</a>
        <ul>
          <li><a href="#queue.Queue">queue.Queue</a></li>
          <li><a href="#collections.deque">collections.deque</a></li>
          <li><a href="#Priority-queue">Priority queue</a>
            <ul>
              <li><a href="#heapq">heapq</a></li>
            </ul>
          </li>
        </ul>
      </li>
    </ul>
  </li>
  <li><a href="#Records,Structs, and Data Transfer Objects">Records,Structs, and Data Transfer Objects</a>
    <ul>
      <li><a href="#dict: Simple Data Objects">dict: Simple Data Objects</a></li>
      <li><a href="#tuple: Immutable Groups of Objects">tuple: Immutable Groups of Objects</a></li>
      <li><a href="#Write a Custom Class: More Work, More Control">Write a Custom Class: More Work, More Control</a></li>
      <li><a href="#collections.namedtuple: Convenient Data Objects">collections.namedtuple: Convenient Data Objects</a></li>
      <li><a href="#typing.NamedTuple: Improved Namedtuples">typing.NamedTuple: Improved Namedtuples</a></li>
      <li><a href="#struct.Struct: Serialized C Structs">struct.Struct: Serialized C Structs</a></li>
      <li><a href="#types.SimpleNamespace: Fancy Attribute Access">types.SimpleNamespace: Fancy Attribute Access</a></li>
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
`Lists` are a versatile and widely-used data structure that can store a collection of items in an ordered and mutable sequence.
Example:
```
my_list = [1, 2, 3, 'a', 'b', 'c']
print(my_list[0])
```
## Tuple:
`Tuple` objects are immutable. This means elements can’t be added or removed dynamically—all elements in a tuple must be defined at creation time.
Example:
```
my_tuple = (1, 2, 3, 'a', 'b', 'c')
print(my_tuple[0])  
print(my_tuple[3])
```
## Set:
A `set` is an unordered collection of unique elements. Sets are useful to store a collection of items and there should be no duplicates.
Example:
```
my_set = {1, 2, 3, 'a', 'b', 'c'}
print(my_set)
```
### frozenset: 
The `frozenset` class implements an immutable version of set that can’t be changed after it’s been constructed.
Example:
```
my_frozenset = frozenset([1,2,3,4,'a','b'])
print(my_frozenset)
```
### collections.Counter(Multisets):
The `collections.Counter` class in the Python standard library implements a multiset, or bag, type that allows elements in the set to have more than one occurrence.
Example:
```
from collections import Counter
my_list = ['a', 'b', 'c', 'a', 'b', 'a']
counter = Counter(my_list)
print(counter)
```
## Dictionary:
`Dictionaries` are also often called maps, hashmaps, lookup tables, or associative arrays.They are ordered and key are immutable but values are mutable and don't allow duplicates.Dictionaries are used to store data values in key:value pairs.Values in dictionary items can be of any data type.
### dict() Constructor:
Standard dictionary in Python, which stores key-value pairs.
Example:
```
a = dict(name = "John", age = 36, country = "Norway")
print(a)
```
### collections.OrderedDict:
Python includes a specialized dict subclass that remembers the insertion order of keys added to it: `collections.OrderedDict`.
Example:
```
from collections import OrderedDict
ordered_dict = OrderedDict()
ordered_dict['first'] = 1
ordered_dict['second'] = 2
ordered_dict['third'] = 3
print(ordered_dict)
```
### collections.defaultdict:
The `defaultdict` class is another dictionary subclass that accepts a callable in its constructor whose return value will be used if a requested key cannot be found.
Example:
```
from collections import defaultdict
default_dict = defaultdict(int)
default_dict['a'] += 1
default_dict['b'] += 2
default_dict['a'] += 3
print(default_dict)
```
### collections.ChainMap:
The `collections.ChainMap` data structure groups multiple dictionaries into a single mapping.
Example:
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
`Arrays` consist of fixed-size data records that allow each element to be efficiently located based on its index.
### array.array:
Arrays created with the `array.array` class are mutable and behave similarly to lists except for one important difference: they’re typed arrays constrained to a single data type.
Example:
```
import array
int_array = array.array('i', [1, 2, 3, 4, 5])
print(int_array)
```
### str: 
Python uses `str` objects to store textual data as immutable sequences of Unicode characters. str is an immutable array of characters.
Example:
```
my_list = ['apple', 'banana', 'cherry', 'date']
print(my_list[2])
```
### byte:
`bytes` objects are immutable sequences of single bytes, or integers in the range 0 ≤ x ≤ 255.byte objects are immutable.
Example:
```
bytes_data = b'Hello'
print(bytes_data)  
print(bytes_data[0])
```
### bytearray:
The `bytearray` type is a mutable sequence of integers in the range 0 ≤ x ≤ 255.The main difference being that a bytearray can be modified freely—you can overwrite elements, remove existing elements, or add new ones.
Example:
```
bytes_data = b'Hello'
byte_array = bytearray(bytes_data)
print(byte_array[0])
```
## Stack:
A `stack` is a collection of objects that supports fast Last-In/First-Out (LIFO)  for insertion and deletion.The insert and delete operations are also often called push and pop.
Example:
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
### queue.LifoQueue:
The `LifoQueue` stack implementation in the Python standard library is synchronized and provides locking semantics to support multiple concurrent producers and consumers.
Example:
```
from queue import LifoQueue
s = LifoQueue()
s.put("read")
s.put("write")
s.put("code")
s.get()
```
## Queue:
A `queue` is a collection of objects that supports fast FIFO  for insertion and deletion. The insert and delete operations are sometimes called enqueue and dequeue. With a queue, you remove the item least recently added (FIFO) but with a stack, you remove the item most recently added (LIFO).
### queue.Queue
The `queue.Queue` implementation in the Python standard library is synchronized and provides locking semantics to support multiple concurrent producers and consumers.
Example:
```
from queue import Queue
q = Queue()
q.put("eat")
q.put("sleep")
q.get()
```
### collections.deque:
The `collections.deque` class in Python is a double-ended queue that allows you to append and pop elements from both ends with O(1) performance. 
Example:
```
from collections import deque
q = deque()
q.append("eat")
q.append("sleep")
q.popleft()
```
### multiprocessing.Queue: 
`multiprocessing.Queue` is a shared job queue implementation that allows queued items to be processed in parallel by multiple concurrent workers. 
Example:
```
from multiprocessing import Queue
q = Queue()
q.put("write")
q.put("code")
q.get()
```
### Priority queue:
A `priority queue` is a container data structure that manages a set of records with totally-ordered keys to provide quick access to the record with the smallest or largest key in the set.
### heapq
`heapq` is a binary heap implementation usually backed by a plain list, and it supports insertion and extraction of the smallest element in O(log n) time.
Example:
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
## Records,Structs, and Data Transfer Objects:
Compared to arrays, `record` data structures provide a fixed number of fields, each with a name and possibly a different type. Python offers several data types to implement records, structs, and data transfer objects
### dict: Simple Data Objects
Dictionaries in Python allow easy creation with concise syntax using literals. They support mutable data objects, but lack robust protection against misspelled field names, potentially leading to unexpected bugs
Example:
```
car1 = {
    "color": "red",
    "mileage": 3812.4,
    "automatic": True,
}
car2 = {
    "color": "blue",
    "mileage": 40231,
    "automatic": False,
}
print(car2)  # {'color': 'blue', 'mileage': 40231, 'automatic': False}
print(car2["mileage"])  
car2["mileage"] = 12000
car2["windshield"] = "broken"
print(car2)  
car3 = {
    "colr": "green",  # Typo in key name
    "automatic": True,
}
print(car3) 
```
### tuple: Immutable Groups of Objects
Python `tuples` are immutable data structures used for grouping arbitrary objects. They take up slightly less memory and are faster to construct than lists.
Example:
```
c = (10, 20)
print(c[0])  
```
### Write a Custom Class: More Work, More Control
Creating a `custom class` provides more control over the data structure and behavior, allowing encapsulation and additional methods.
Example:
```
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    def introduce(self):
        return f"My name is {self.name} and I am {self.age} years old."
person = Person("Alice", 30)
print(person.introduce())  
```
### collections.namedtuple: Convenient Data Objects
The `namedtuple` class in Python  extends the functionality of the built-in tuple data type by providing named fields for accessing elements.
Example:
```
from collections import namedtuple
Car = namedtuple("Car", ["color", "mileage", "automatic"])
car1 = Car("red", 3812.4, True)
car2 = Car("blue", 40231, False)
print(car1)  
print(car1.mileage) 
# Namedtuples are immutable, attempting to modify a field will raise an error:
try:
    car1.mileage = 12  # Raises AttributeError
except AttributeError as e:
    print(e)  # "can't set attribute"
# Adding new fields is not allowed in namedtuples:
try:
    car1.windshield = "broken"  # Raises AttributeError
except AttributeError as e:
    print(e)  
```
### typing.NamedTuple: Improved Namedtuples
`typing.NamedTuple` provides an enhanced syntax for defining named tuples with added support for type annotations.
Example:
```
from typing import NamedTuple
class Car(NamedTuple):
    color: str
    mileage: float
    automatic: bool
car1 = Car("red", 3812.4, True)
print(car1)  
print(car1.mileage)  
try:
    car1.mileage = 12  # Raises AttributeError
except AttributeError as e:
    print(e)
try:
    car1.windshield = "broken"  # Raises AttributeError
except AttributeError as e:
    print(e)
print(Car("red", "NOT_A_FLOAT", 99))  # Car(color='red', mileage='NOT_A_FLOAT', automatic=99)
```
### struct.Struct: Serialized C Structs
The `struct.Struct` class in Python facilitates the conversion between Python values and C structs serialized into bytes objects. It is commonly used for handling binary data from files or network connections.
Example:
```
from struct import Struct
MyStruct = Struct("i?f")
data = MyStruct.pack(23, False, 42.0)
print(data)  
print(MyStruct.unpack(data))  # (23, False, 42.0)
```
### types.SimpleNamespace: Fancy Attribute Access
`types.SimpleNamespace` in Python provides a simple way to create objects that act like namespaces with attribute access, similar to dictionaries but with the convenience of attribute-style access syntax.
Example:
```
from types import SimpleNamespace
car1 = SimpleNamespace(color="red", mileage=3812.4, automatic=True)
print(car1)  
car1.mileage = 12
car1.windshield = "broken"
del car1.automatic
print(car1)
``` 
