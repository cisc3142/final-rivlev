   1. What is your name? <br> `Amr Abedo` 
   2. What is the output of this line? `std::cout << 3+2;`<br>  `5`
   3. Write a templated function that takes two iterators and prints out each element in that range. \(This is for practice writing code blocks in this interface. You can copy the code from http://www.sci.brooklyn.cuny.edu/~levitan/cisc3142/classcode/11-containers/iterators.cpp)

<br>

```#include <algorithm>
#include <iostream>
#include <list>
#include <set>
#include <vector>

template <class Iterator>
void print(Iterator begin, Iterator end) {
  for (Iterator it = begin; it != end; ++it) std::cout << *it << " ";
  std::cout << std::endl;
}

template <class I1, class I2>
bool checkIfReversed(I1 b1, I1 e1, I2 b2, I2 e2) {
  while (b1 != e1 && b2 != e2) {
    --e2;
    if (*b1 != *e2) return false;
    ++b1;
  }
  if (b1 != e1 || b2 != b2) return false;
  return true;
}

int main() {
  std::vector<int> v { 5, 3, 10, 2, 6 };
  std::list<int> lst { 14, 15, 5, 2, 7 };
  std::set<int> s { 1, 17, 3, 14, 11 };

  // vector for loop
  for (std::vector<int>::iterator it = v.begin(); it != v.end(); ++it) 
    std::cout << *it << " ";
  std::cout << std::endl;

  // general purpose for loop
  print(lst.begin(), lst.end());

  // iterators define ranges
  print(lst.begin(), lst.end());
  std::sort(v.begin()+2, v.end());
  print(v.begin(), v.end());
  print(v.begin()+2, v.end());
  std::list<int>::iterator it = std::find(lst.begin(), lst.end(), 5);
  print(s.begin(), s.end());
  s.insert(lst.begin(), it);
  print(s.begin(), s.end());
  lst.erase(it);
  print(lst.begin(), lst.end());

  // things you can do with iterators
  std::list<int>::iterator lit = lst.begin();
  ++lit;
  int x = *lit;		// rhs
  *lit = x+1;		// lhs
  print(lst.begin(), lst.end());
  --*(--lit);
  print(lst.begin(), lst.end());

  // things you can do with random access iterators
  print(v.begin(), v.end());
  std::vector<int>::iterator vit = v.begin() + 3, vitt = v.end() - 1;
  std::cout << *vit << std::endl;
  std::cout << *(vit-2) << std::endl;
  std::cout << vitt - vit << std::endl;
  std::cout << std::boolalpha << (vit < vitt) << std::endl;

  std::vector<int> vr(v);
  std::cout << std::boolalpha << checkIfReversed(v.begin(), v.end(), vr.begin(), vr.end()) << std::endl;
  std::reverse(vr.begin(), vr.end());
  std::cout << std::boolalpha << checkIfReversed(v.begin(), v.end(), vr.begin(), vr.end()) << std::endl;
  std::cout << std::boolalpha << checkIfReversed(v.begin(), v.end(), lst.begin(), lst.end()) << std::endl;

  // container iterators
  std::cout << *v.begin() << std::endl;
  std::cout << *(v.end()-1) << std::endl;
  std::cout << *v.rbegin() << std::endl;
  std::cout << *(v.rend()+1) << std::endl;

  // string iterators
  std::string str = "hello world";
  for (std::string::iterator it = str.begin(); it != str.end(); ++it) {
    std::cout << *it;
  }
  std::cout << std::endl;
  for (std::string::reverse_iterator it = str.rbegin(); it != str.rend(); ++it) {
    std::cout << *it;
  }	
  std::cout << std::endl;
}        
```
