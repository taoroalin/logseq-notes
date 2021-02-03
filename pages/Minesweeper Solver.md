---
title: Minesweeper Solver
---

## It should be possible to completely solve minesweeper.

## Algorithm:
### Loop
#### Brute force enumerate the possibilities for edge tiles

#### Group by bomb count

#### Weight by number of number of possibilities for insides by bomb count

#### Assign each edge tile weight

#### Pick lowest

## The Math
### The Setup: Board starts with b0 bombs, t0 tiles.

### At any time the edge tiles number e, hidden tiles h, current bomb left b

### When choosing among a distribution, 

### **Proof**
#### **Always take guaranteeds first**

#### 

### Proving order of guaranteeds is irrelevent:
#### 

## What's the distribution of adjacency numbers near the middle?

## Efficiency Tricks
### Check what just changed first

### Factor regions that don't touch and solve seperately

### Check for numbers that are exactly matched first

## When choosing from a distribution, you must take into account expected information value from each choice (if the game is easier in one branch than the other, we want to lean towards the easier one)
