Design a [Dynamic Array](https://neetcode.io/courses/dsa-for-beginners/3) (aka a resizable array) class, such as an `ArrayList` in Java or a `vector` in C++.

Your `DynamicArray` class should support the following operations:

- `DynamicArray(int capacity)` will initialize an empty array with a capacity of `capacity`, where `capacity > 0`.
- `int get(int i)` will return the element at index `i`. Assume that index `i` is valid.
- `void set(int i, int n)` will set the element at index `i` to `n`. Assume that index `i` is valid.
- `void pushback(int n)` will push the element `n` to the end of the array.
- `int popback()` will pop and return the element at the end of the array. Assume that the array is non-empty.
- `void resize()` will _double_ the capacity of the array.
- `int getSize()` will return the number of elements in the array.
- `int getCapacity()` will return the capacity of the array.

If we call `void pushback(int n)` but the array is full, we should resize the array first.


`class DynamicArray:

    # O(n) n is the capacity, it has to allocate n times to make the arr
    def __init__(self, capacity: int):
	 # capacity would be the max size of the array
	 # length would be the number of elements
        self.capacity = capacity
        self.length = 0
        self.arr = [0] * capacity

    # O(1) array accesses are always constant time
    def get(self, i: int) -> int:
        return self.arr[i]

    # O(1)
    def set(self, i: int, n: int) -> None:
        self.arr[i] = n

    # O(n) since resize is the effectively the same as the constructor
    # O(1) avg case since resize will not be called that often (Ammortized)
    def pushback(self, n: int) -> None:
        if self.length == self.capacity:
            self.resize()

         # insert at next empty position
        self.arr[self.length] = n
        self.length += 1

    # O(1)
    def popback(self) -> int:
        # soft deletion, the value is still there but
        # the length variable means it will get over written
        self.length -= 1
        return self.arr[self.length]

    # O(n) its the same as the constructor
    def resize(self) -> None:
        self.capacity *= 2
        new_arr = [0] * self.capacity

        for i in range(self.length):
            new_arr[i] = self.arr[i]
        self.arr = new_arr

    # O(1)
    def getSize(self) -> int:
        return self.length

    # O(1)
    def getCapacity(self) -> int:
        return self.capacity
`

