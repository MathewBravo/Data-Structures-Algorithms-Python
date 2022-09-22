# Linked Lists Python

- Linked lists do not have indexes
- Linked lists have nodes that are spread all over the place.

![Screenshot from 2022-09-21 15-13-09](/home/mathew/Pictures/Screenshots/Screenshot from 2022-09-21 15-13-09.png)

- Each node points to the next node, the last node <strong> 7 </strong> points to "None".
- Because each node points to the next node you are able to find all the nodes without losing any data.

## Linked List Big 0

### Appending a new node to the end

- In order to append a new node we have to point our final node to the new object, and then point the new object to "
  None". <em> As seen below </em>
- ![Screenshot from 2022-09-21 15-18-45](/home/mathew/Pictures/Screenshots/Screenshot from 2022-09-21 15-18-45.png)

- This means it doesn't matter how long the list is, the number operations is always 0(1)

### Removing a node from the start

- In order to remove an object we need to switch the tail pointer equal to another pointer, the only thing that points
  to the final node is the pointer from the node previous to it
    - In the above example if we remove node 4, we then have to have the fail find the 7 by first having it find the
      pointer that the 23 node has pointing at the 7
- In order to get that node we have to start all the way at the start of the list and iterate through the list until we
  find the pointer.
- Then set the tail equal to the pointer.
- The requirement of iterating from head to pointer node makes the operation 0(n)

### Adding a node to the beginning

- To add a node to the beginning of the linked list it works similar to adding to the end of the linked list.
- All we need to do is take the head of the current list and set it equal to the pointer of the new item.
- Making all adding operation to the start of the list 0(1)

### Removing a node from the beginning

- To remove an item all we need to do is set the pointer of the Head to the pointer of the second item in the list.
    - For example in the above diagrams this would be the pointer from object 3 --> 23.
- This makes removing from the start of a list 0(1)

### Adding a node to the middle of the list

- To insert a node into the list we need to iterate through the list similar to how we did it when adding to the end of
  the list.
- We search the list for the pointer to the node we want to insert behind of. (<em>Above 23 is behind 7</em>) Then we
  set the pointer of our new node equal to the pointer going towards the node we want to be behind. Then we set the
  pointer we are replacing equal to our newly inserted item so that it points towards that.
- Because the list needs to be iterated through, this is 0(n)

### Removing a node from the middle of the list

- To remove an item from the list we need to do almost the exact same thing as the above operation. We need to iterate
  through the list, find the node pointing to the node we wish to remove and then set it equal to the pointer of the
  node we want to remove (<em> That node would point to the item following our removed node </em>).
- Against any non-logarithmic iteration operation is 0(n)

### Looking Up a nodes positions

- To find objects in a linked list by value OR by index you need to iterate either way, this is because the items are
  not stored in sequential memory and to find an items index you need to traverse the list until you arrive at it.
- This makes all look up operations iteration operations and causes them to be 0(n)

|                 | Linked List |  Lists   |
|-----------------|:-----------:|:--------:|
| Append          |  ~~0(1)~~   | **0(1)** |
| Pop             |  ~~0(n)~~   | **0(1)** |
| Prepend         |  **0(1)**   | ~~0(n)~~ |
| Pop First       |  **0(1)**   | ~~0(n)~~ |
| Insert          |    0(n)     |   0(n)   |
| Remove          |    0(n)     |   0(n)   |
| Lookup by Index |  ~~0(n)~~   | **0(1)** |

## Composition

### The node.

This includes both the reference pointers and the object. The particular pointer that is included in the node is the
pointer to the next object.

> 1 -> 2 -> 3 -> 4 -> 5
>
> [1 ->], [2->], [3->] .... are all nodes

You can think of it as a dictionary although that is not exactly how it works.

```json
{
  "value": 4,
  "next": 5
}
```

```json
{
  "value": 1,
  "next": {
    "value": 2,
    "next": {
      "value": 3,
      "next": {
        "value": 4,
        "next": {
          "value": 5,
          "next": None
        }
      }
    }
  }
}
```
*Value + Pointer*

