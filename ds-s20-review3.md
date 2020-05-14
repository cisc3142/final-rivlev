# Vectors

   1. What do you need to include in order to use a vector?

```
std::vector<char> v1,
	v2(5, 'a'),
	v3{'h','e','l','l','o'},
	v4(v2.begin(), v2.end()-1);
```

   2. What are the contents of `v1`, `v2`, `v3`, and `v4`?

   3. Write code to create `int` vectors with the following specifications:

      a) an empty vector 

      b) a vector containing 8 copies of the element `3` (using the fill constructor)

      c) a vector containing the elements `{7, 1, 8, 9, 5, 1, 5, 0, 0, 0}` (using the initializer list constructor)

      d) a vector containing the first three elements of another vector called `v3` (using the range constructor)

   4. What is the output of the following statements?

      a) `std::cout << v3.at(2);`

      b) `std::cout << v3[1];`

      c) `std::cout << v3.front();`

      d) `std::cout << v3.back();`

   5. Write code using vector methods (not iterators) to produce the following outputs:

      a) print the first element of `v3`

      b) print the last element of `v3`

      c) print the fourth element of `v3`

      d) print the second element of `v3`

   6. Write code to fill `v1` with the elements `{2, 4, 6, 8, 10}`.

   7. Write code to print out each element of `v1`.

   8. What are the contents of `v1` after each of the following statements?

      a) `v1.push_back(11);`

      b) `v1.insert(v1.begin()+2, 5);`

      c) `v1.pop_back();`

      d) `v1.erase(v1.end()-2);`

   9. Write code to

      a) add `9` to the end of `v1`

      b) add `3` as the second element of `v1`

      c) remove the last element of `v1`

      d) remove `3` from `v1`

   10. Which vector methods should you avoid using?


# Lists

   11. What two access methods does vector have that list does not? Why?

   12. What two modifier methods does list have that vector does not? Why?

   13. Most questions that were asked for `vector` can also be asked for `list`.

# Stacks, Queues, Priority Queues

   14. Create an empty `{stack, queue, priority queue}` of `ints`.

   15. Fill the `{stack, queue, priority queue}` with the elements `{1, 2, 3, 4, 5}`.

   16. Print each element of the `{stack, queue, priority queue}`. What is the output?


# Algorithms

   17. What do you need to include in order to use algorithms from the standard library?

   18. Write code using methods from `std::algorithm` to

      a) reverse the second half of a vector 

      b) sort a vector

      c) reverse sort a vector

      d) find the element `5` in a list and replace it with the value `4`

# Iterators

   19. Write a templated function `print` to print out each element in a range.

   20. Write a templated function `reverse` to reverse a range.

   21. Write a for loop using iterators to print each element in a vector `v`.

   22. Use an iterator to print out the third element in a vector `v`.

   23. Use an iterator to increment the first element in a vector `v`.

   24. Use iterators and `std::find` to print out how many elements apart `d` and `e` are in vector `v`.

   25. Use iterators and `std::find` to print out whether element `d` comes before element `e` in vector `v`.

   26. Review `iterators.cpp` carefully.

# Maps

   27. What do you need to include in order to use a map?

   28. What is the Java equivalent of `std::map`?

   29. What is the Java equivalent of `std::unordered_map`?

   30. Declare a map `m` with a key type of `int` and a value type of `string`.

   31. `auto p = *(m.begin());`   What is the type of `p`?

   32. Use `p` to print out `m`\'s first key and value.

   33. Suppose `m` has the following contents: 

```
{ { 1, "cat" }, { 2, "book" }, { 3, "cello" }, { 4, "green" } }
```
   What is the value of each of the following expressions?

      a) `m[1]`

      b) `m.at(3)`

      c) `m[6]`

   34. Write code to insert `5` into the map with a value of `twelve`.

   35. Write code to erase `3` from the map.

   36. Write code to determine if `8` is in the map, and, if it is, update its value to `Stuart`. If it is not yet in the map, insert it with a value of `Brenda`.

   37. Review `maps.cpp` very carefully.

# File I/O

   38. Write a short program to open a file called `example.txt`, read its contents into memory, and write them back out to the end of `example.txt` (so it now contains two copies of its original contents.)

# Exceptions

   39. Write a short program that reads in two integers from the console, tries to divide the first int by the second, throws an exception if the second int is equal to 0, and handles the exception by printing out: `Error: the denominator is 0.`

# Smart pointers

   40. Write code to 

      a) include the header file necessary for smart pointers

      a) declare a `shared_ptr` called `p1` pointing to a new `string` "hello"

      c) declare a `shared_ptr` called `p2` pointing to the same `string`

      d) print `p1`'s string to the console

      e) print the length of `p1`'s string to the console

      f) empty `p1`

      g) declare a `weak_ptr` called `w1` pointing to the same `string` as `p2`

      h) declare a `unique_ptr` called `u1` pointing to a new string "goodbye"

   41. When will "hello"'s memory be freed?

   42. What is `p2`'s reference count after statement 40.c? after 40.f? after 40.g?

   43. What error will you get from the statement `auto u2 = u1`? How can you assign `u1`'s pointer to `u2`?
