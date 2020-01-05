# Lists
{id: python-lists}

## Anything can be a lists
{id: any-lists}

* Comma separated values
* In square brackets
* Can be any value, and a mix of values: Integer, Float, Boolean, None, String, List, Dictionary, ...
* But usually they are of the same type:
* Distances of astronomical objects
* Chemical Formulas
* Filenames
* Names of devices
* Objects describing attributes of a network device.
* Actions to do on your data.

![](examples/lists/any_list.py)
![](examples/lists/any_list.out)


## Any layout
{id: any-lists2}

* Layout is flexible
* Trailing comma is optional. It does not disturb us. Nor Python.

![](examples/lists/any_list2.py)
![](examples/lists/any_list2.out)


## Lists
{id: lists}
{i: []}
{i: len}

* Access single element: **[index]**
* Access a sublist: **[start:end]**
* Creates a copy of that sublist

![](examples/lists/simple.py)


## List slice with steps
{id: list-slice}

* List slice with step: **[start:end:step]**

![](examples/lists/slice.py)


## Change a List
{id: list-change}
{i: :}
![](examples/lists/change.py)

* Unlike strings, lists are mutable. You can change the content of a list by assigning values to its elements.
* You can use the slice notation to change several elements at once.
* You can even have different number of elements in the slice and in the replacement. This will also change the length of the array.



## Change with steps
{id: list-change-steps}
![](examples/lists/change_steps.py)


## List assignment and list copy
{id: list-copy}
{i: copy}
{i: [:]}
![](examples/lists/not_copy.py)

* There is one list in the memory and two pointers to it.
* If you really want to make a copy the pythonic way is to use the slice syntax.
* It creates a shallow copy.

![](examples/lists/real_copy.py)

Deep copy

![](examples/lists/deep_copy.py)


## join
{id: join}
{i: join}
![](examples/lists/join.py)


## join list of numbers
{id: join-mixed-list}
![](examples/lists/joining_integers.py)


## split
{id: split}
{i: split}
{i: list}

* Special case: To split a string to its characters: Use the **list()** function.
* Split using more than one splitter: use **re.split**

![](examples/lists/split.py)


## for loop on lists
{id: for-loop-on-list}
{i: for}
{i: in}
![](examples/lists/for.py)

```
abc
def
xyz
42
```


## in list
{id: in-syntax-on-list}
{i: in}

Check if the value is in the list?

![](examples/lists/in.py)


## Where is the element in the list
{id: where-is-the-element-in-the-list}
{i: index}
![](examples/lists/index.py)
![](examples/lists/index.py.out)


## Index improved
{id: index-improved}
{i: index}
![](examples/lists/index_improved.py)


## [].insert
{id: list-insert}
{i: insert}
{i: unshift}
![](examples/lists/insert.py)


## [].append
{id: list-append}
{i: append}
![](examples/lists/append.py)



## [].remove
{id: list-remove}
{i: remove}
![](examples/lists/remove.py)

{aside}

Remove **first** element from a list given by its value.
Throws an exception if there is no such element in the list.
{/aside}


## Remove element by index [].pop
{id: list-pop}
{i: pop}
![](examples/lists/pop.py)

{aside}
Remove and return the last element of a list. Throws an exception if the list was empty.
{/aside}



## Remove first element of list
{id: list-shift}
{i: pop}
{i: shift}

{aside}
To remove an element by its index, use the slice syntax:
{/aside}

![](examples/lists/remove_first_element.py)


## Remove several elements of list by index
{id: list-remove-by-index}
{i: slice}

{aside}
To remove an element by its index, use the slice syntax:
{/aside}

![](examples/lists/remove_by_slice.py)



## Use list as a queue
{id: list-as-a-queue}
![](examples/lists/list_as_a_queue.py)
![](examples/lists/list_as_a_queue.out)


## Queue using deque from collections
{id: dequeue}
{i: collections}
{i: deque}
{i: append}
{i: popleft}
![](examples/lists/queue.py)

* .append
* .popleft
* len()  number of elements
* if q:  to see if it has elements or if it is empty
* [dequeue](https://docs.python.org/3/library/collections.html#collections.deque)



## Fixed size queue
{id: fixed-size-dequeue}
{i: maxlen}
![](examples/lists/fixed_size_queue.py)


## List as a stack
{id: list-as-a-stack}
![](examples/lists/stack.py)


## stack with deque
{id: stack-with-deque}
![](examples/lists/stack_with_deque.py)



## Exercies: Queue
{id: exercise-queue}


The application should manage a queue of people.



* It will prompt the user for a new name by printing **:**, the user can type in a name and press ENTER. The app will add the name to the queue.
* If the user types in "n" then the application will remove the first name from the queue and print it.
* If the user types in "x" then the application will print the list of users who were left in the queue and it will exit.
* If the user types in "s" then the application will show the current number of elements in the queue.


```
: Foo
: Bar
: Moo
: n
  next is Foo
: n
  next is Bar
: Peter
: n
  next is Moo
: n
  next is Peter
: n
  the queue is empty
```


## Exercise: Stack
{id: exercise-stack}


Implement a Reverse Polish Calculator



```
2
3
4
+
*
=
14
```


## Solution: Queue
{id: solution-queue}
![](examples/lists/queue_people.py)


## Debugging Queue
{id: debugging-queue}


The following implementation has a bug. (Even though the n was supposed to remove the element
and the code seems to mean that it does, we still see two items after we removed the first.)

The question is how to debug this?



![](examples/lists/queue_with_bug.py)

```
your name: Foo
your name: Bar
your name: n
Foo
your name: s
2
```



## sort
{id: sort}
{i: sort}
![](examples/lists/sort.py)


## sort numbers
{id: sort-numbers}
{i: sort}
{i: key}
{i: abs}
![](examples/lists/sort_numbers.py)


## sort mixed
{id: sort-mixed}
![](examples/lists/sort_mixed.py)

In Python 2 puts the numbers first in numerical order and then the strings in ASCII order.


```
[100, 'foo', 42, 'bar']
[42, 100, 'bar', 'foo']
```

In Python 3 it throws an exception.


```
[100, 'foo', 42, 'bar']
Traceback (most recent call last):
  File "examples/lists/sort_mixed.py", line 5, in <module>
    mixed.sort()
TypeError: unorderable types: str() < int()
```


## key sort
{id: key-sort}
{i: key}
{i: len}

* Another example to using a **key**.
* To sort the list according to length

![](examples/lists/sort_key.py)
![](examples/lists/sort_key.out)

## Sort tuples
{id: sort-tuples}

Sorting tuples or list, or other complex structures

![](examples/lists/sort_tuples.py)

## Sort dictionary by value
{id: sort-dictionary-by-value}
![](examples/lists/sort_dictionary.py)


## DSU: Decorate Sort Undecorate
{id: sort-decorate-sort-undecorate}

In Perl it is called Schwartzian transform

![](examples/lists/sort_dsu.py)

## sort with sorted
{id: sorted}
{i: sorted}
![](examples/lists/sorted.py)


## sort vs. sorted
{id: sort-vs-sorted}

The sort() method will sort a list in-place and return None.
The built-in sorted() function will return the sorted list and leave the original list intact.




## key sort with sorted
{id: key-sorted}

To sort the list according to length using sorted

![](examples/lists/sorted_key.py)
![](examples/lists/sorted_key.out)


## Sorting characters of a string
{id: sorting-characters}
![](examples/lists/sorting-characters.py)


## range
{id: range}
{i: range}
![](examples/lists/range.py)


## Looping over index
{id: looping-over-index}
![](examples/lists/loop.py)
![](examples/lists/loop_index.py)


## Enumerate lists
{id: enumerate-lists}
{i: enumerate}
![](examples/lists/enumerate.py)
![](examples/lists/enumerate.out)


## List operators
{id: list-operators}
![](examples/lists/operators.py)


## List of lists
{id: list-of-lists}
![](examples/lists/list_of_lists.py)


## List assignment
{id: list-assignment}

{aside}

List assignment works in "parallel" in Python.
{/aside}
![](examples/lists/list_assignment.py)

```
x,y = f()  # works if f returns a list of 2 elements
```


It will throw a run-time ValueError exception if the number
of values in the returned list is not 2. (Both for fewer and for more return values).




## List documentation
{id: list-documentation}

* [datastructures](http://docs.python.org/tutorial/datastructures.html)



## tuple
{id: tuple}
{i: tuple}
{i: ()}

Tuple


* A tuple is a fixed-length immutable list. It cannot change its size or content.
* A tuple is denoted with parentheses: (1,2,3)

![](examples/lists/tuple.py)

List


* Elements of a list can be changed via their index or via the list slice notation.
* A list can grow and shrink using **append** and **pop** methods or using the **slice** notation.
* A list is denoted with square brackets:   [1, 2, 3]

![](examples/lists/totuple.py)


Tuples are rarely used. There are certain places where Python or some module require tuple (instead of list) or return a tuple (instead of a list)
and in each place it will be explained. Otherwise you don't need to use tuples.

e.g. keys of dictinoaries can be tuple (but not lists).




## Exercise: color selector menu
{id: exercise-menu}

* In a script have a list of colors. Write a script that will display a menu (a list of numbers and the corresponding color) and prompts the user for a number. The user needs to type in one of the numbers. That's the selected color.


1. blue
1. green
1. yellow
1. white


* For extra credit make sure the system is user-proof and it won't blow up on various incorrect input values. (e.g Floating point number. Number that is out of range, non-number)
* For more credit allow the user to supply the number of the color on the command line. **python color.py 3**. If that is available, don't prompt.
* For further credit allow the user to provide the name of the color on the command line: **python color.py yellow** Can you handle color names that are not in the expected case (e.g. YelloW)?
* Any more ideas for improvement?



## Exercise: count digits
{id: exercise-count-digits}

Given a list of numbers <command>numbers = [1203, 1256, 312456, 98]</command>,
count how many times each digit appears? The output will look like this:



```
0  1
1  3
2  3
3  2
4  1
5  2
6  2
7  0
8  1
9  1
```


## Exercise: Create list
{id: exercise-create-list}

```
Given a list of strings with words separated by spaces,
create a single list of all the words.

input = [
  'ab cde',
  'x yz qwerty',
  'abc x cde abc d er'
]

output = ['ab', 'cde','x', 'yz', 'qwerty', 'abc', 'x', 'cde', 'abc', 'd', 'er']
```


Then create a list of unique values:



```
output = ['ab', 'cde','x', 'yz', 'qwerty', 'x', 'd', 'er']
```


## Exercise: Count words
{id: exercise-count-words-in-list}
![](examples/lists/count_words_skeleton.py)

Expected output:


```
Moon        2
Gas         1
Asteroid    3
Dwarf       1
```


## Exercise: Check if number is prime
{id: exercise-is-prime}

Write a program that gets a number on the commnad line a prints "True" if the number is a prime
number or "False" if it isn't.



```
python is_prime.py 42
False
python is_prime.py 19
True
```


## Exercise: DNA sequencing
{id: exercise-dna-sequencing}

* A, C, T, G are called bases or nucleotides
* Given a sequence like **'ACCGXXCXXGTTACTGGGCXTTGT'** (nucleoids mixed up with other elements) return the sequences containing only ACTG orderd by length.
* Expected result: **['GTTACTGGGC', 'ACCG', 'TTGT', 'C']**



## Solution: menu
{id: solution-menu}
![](examples/lists/colors.py)


## Solution: count digits
{id: solution-count-digits}

TypeError: 'int' object is not iterable

![](examples/lists/count_digits.py)


## Solution: Count words
{id: solution-count-words-in-list}
![](examples/lists/count_words_two_lists.py)


## Solution: Check if number is prime
{id: solution-is-prime}
![](examples/lists/is_prime.py)


## Solution: DNA sequencing
{id: solution-dna-sequencing}
![](examples/lists/dna_sequencing.py)


## Solution: DNA sequencing with filter
{id: solution-dna-sequencing-filter}
![](examples/lists/dna_sequencing_filter.py)


## Solution: DNA sequencing with filter and lambda
{id: solution-dna-sequencing-filter-lambda}
![](examples/lists/dna_sequencing_filter_lambda.py)


## [].extend
{id: list-extend}
{i: extend}
![](examples/lists/extend.py)


## append vs. extend
{id: list-append-vs-extend}

{aside}

What is the difference between [].append and [].extend ?
The method **append** adds its parameter as a single element to the list, while **extend** gets a list and adds its content.
{/aside}
![](examples/lists/append_extend.py)


## split and extend
{id: split-extend}

{aside}
When collecting data which is received from a string via splitting,
we would like to add the new elements to the existing list:
{/aside}
![](examples/lists/split_extend.py)


