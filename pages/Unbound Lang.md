---
title: Unbound Lang
---

## Decisions:
### Hard scoped **variables**. Soft scoped constants?

### Data stored in Structures. These have **no** external contact

### Allow operators to work on lots of things, but using ordinary operators, not special ones like Haskell

### Apply
#### Use ... for positional apply list, and for keyword args, for example sort(l,{key:hello})

### Use "fake statements" like haskell. Any function can be written as block

### Reduce
#### Homogeneous reductions via Apply, fn(*args),fn(...args)

#### Heterogeneous reductions same? (apply assoc-in)?
##### no, that's too complicated. We can abstract that out

#### x=1
for i in list:
  x+=i

### List comprehensions
#### Why? because 
##### appearance of code should match appearance of result

### What is an Object?
#### Context object
##### Acts over time

##### Starts and ends relationships with db, user, others

#### Primitive object
##### Stores information in a way that can't be reduced to maps, lists. Union-Find

##### 
