# `Containers`

A container is a holder object that stores a collection of other objects (its elements). They are implemented as class templates, which allows great flexibility in the types supported as elements.  <br>

- Sequence Containers: <br>
  implement data structures that can be accessed in a sequential manner.
  - vector
  - list
  - deque
  - arrays
  - forward_list( Introduced in C++11)
  - list (Doubly-linked list) 

- Container Adaptors: <br>
  provide a different interface for sequential containers.
  - queue
  - priority_queue
  - stack
    
- Associative Containers: <br>
  implement sorted data structures that can be quickly searched (O(log n) complexity).
  - set
  - multiset
  - map
  - multimap
    
- Unordered Associative Containers: <br>
  implement unordered data structures that can be quickly searched
  - unordered_set (Introduced in C++11)
  - unordered_multiset (Introduced in C++11)
  - unordered_map (Introduced in C++11)
  - unordered_multimap (Introduced in C++11)
