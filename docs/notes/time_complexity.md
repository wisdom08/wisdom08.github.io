---
title: notes
has_children: true
nav_order: 1
has_toc: false
permalink: docs/notes
---
#  Time Complexity
{: .no_toc }

![](../../_site/assets/images/time_complexity.png)

## priority_queue
If you have an array of size n and you want to build a heap from all items at once, Floyd's algorithm can do it with O(n) complexity. See Building a heap. This corresponds to the std::priority_queue constructors that accept a container parameter.
If you have an empty priority queue to which you want to add n items, one at a time, then the complexity is O(n * log(n)).
So if you have all of the items that will go into your queue before you build it, then the first method will be more efficient. You use the second method--adding items individually--when you need to maintain a queue: adding and removing elements over some time period.
Removing n items from the priority queue also is O(n * log(n)).
Documentation for std::priority_queue includes runtime complexity of all operations.

## set
std::set is commonly implemented as a red-black binary search tree. Insertion on this data structure has a worst-case of O(log(n)) complexity, as the tree is kept balanced.

## list
example problem: 
[146. LRU Cache](/docs/146)
std::list is a container that supports constant time insertion and removal of elements from anywhere in the container (as long as you know the iterator). Fast random access is not supported. It is usually implemented as a doubly-linked list. Compared to std::forward_list this container provides bidirectional iteration capability while being less space efficient.
Adding, removing and moving the elements within the list or across several lists does not invalidate the iterators or references. An iterator is invalidated only when the corresponding element is deleted.