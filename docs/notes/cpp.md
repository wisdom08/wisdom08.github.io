---
title: cpp
permalink: /docs/note_1
parent: notes
has_children: false
nav_order: 0
---
# C++ handing built in functions and usage

## set, unordered_set with pair
[929](/docs/929) 

## unordered_map in C++ 11
example from [594](/docs/594)
```c++
        unordered_map<int,int> m;
        for (auto [k,v] : m){
            ...
        }
        return res;
    }
};
```

## handy functions
1. 
```c++
   int toupper(char c);
   int tolower(char c);
```

return val and be cast to (char) 

2. 
```c++
   *max_element(begin(A), end(A));
   *min_element(begin(A), end(A));
```

3. upper_bound, lower_bound
- `upper_bound`
[link]( http://www.cplusplus.com/reference/algorithm/upper_bound/ )

> Returns an iterator pointing to the first element in the range [first,last) which compares greater than val.
> Unlike lower_bound, the value pointed by the iterator returned by this function cannot be equivalent to val, only greater.

- `lower_bound`
[link]( http://www.cplusplus.com/reference/algorithm/lower_bound/ )

> Returns an iterator pointing to the first element in the range [first,last) which does not compare less than val.
> Unlike upper_bound, the value pointed by the iterator returned by this function may also be equivalent to val, and not only greater.


## operator override
[638. Shopping Offers](/docs/638)

## vector insert

`vector_name.insert (position, val)`

The vector is extended by inserting new elements **before** the element at the pecified position, effectively increasing the container size by the number of lements inserted.

See [link](https://www.geeksforgeeks.org/vector-insert-function-in-c-stl/) for example

## upper_bound
- [981. Time Based Key-Value Store](/docs/981) customized compare function for upper bound