---
title: Unbound
---

## Incremental names are good. point free requires more "floating weight" that requires effort to keep up. Python is good at this

## `[a+1 for a in [1,2,3]]
map ((+)1) [1,2,3]
[1,2,3].map((a)=>a+1)`

## scan: `[result+=x for x in [1,2,3]]`

## I'm not alone!
### #Codeq for Clojure and #Unison have the same "content oriented programming" approach

## What is my actual plan?
### Parse with rewrite-clj

### Put the comment/whitespace information I care about into form metadata

### Run forms through tools.analyzer

### DSL for transforming and checking code that compiles to datalog (for either tools.analyzer directly, datascript, or datomic) and a "pass" that can enact transformations

### ide interface for searching datalog / transforming

## Supported / not supported
### multiple newlines only between top-level forms

### Vertical list with blocks of either 1 or 2 forms

### 

## Core Ideas
### Code is defined primarily by its content, not by its name

## Value Propositions of Content Orientation
### Distributed Computing that automatically sets itself up and can easily think about multiple versions in code simultaneously #Unison

### Handling Dependency Collisions #Unison

### Version Control #Codeq

### Code Completion / Search

### Code Refactoring

## Categorizing parameters
### **Homogeneous operation:** combine 2 or more elements of a group, or whatever. Order of operands has quantitative meaning, and no "qualitative" meaning. All of same "type". Examples:
#### Arithmetic

#### Concatenation

#### Merging

#### Cartesian product

### **Transformation:** Takes 1 arg, transforms "all" of it
#### flatten, vec, set

#### **Bijection:** Takes 1 argument, and has an inverse: Example
##### str (when used with 1 arg), reverse, 

### **Application:** Takes both function(s) and data(s) and applies the functions, in some way, to the data.
#### map, reduce, 

### **Combinator:** takes only functions, produces function that "in theory could call all input functions"

### **Extraction:** takes input that is in some sense compound, and selects some subset of that. Examples:
#### filter, get, mod, first, rest

### **Accretor:** takes something and a "subset ish thing" of that something and adds the small one onto the big one
#### assoc, cons

### **Aggregator:** turns lots of similar small things into a big thing. Examples
#### vector, list, coll literals

### **Importer:** Gets something from outside

### **Exporter:** Puts something Outside

## Equivelence DSL
### ?[name] is a var

### I don't need to support lists of lists of params, only lists of fixed size tuples of params

## Editing scope for unknowns: default: lowest named form

## Names: Roam IDE, Context Free Programming, Content Oriented Programming, Content Driven Programming, structure programming?, strucjure

## Write queries over structure of programs you've written / in database as you're writing.

## Functional (possibly also logical) using only point-free functions

## All expressions indexed

## Different Sorts of Unbound
### Nested Clojure Function Literals
#### Every form is instantiated as it's own function 

#### Threaded arguments like %%1 read as "the first argument of the function literal outside this one, and the whatevereth argument of the inner function (automatically placed in order they appear in inner form, or outer form, or something)

### Code structure search
#### Automatically search for structure of form you're writing as you're writing it, in your code or loaded libraries

## Abstract functions by linking to content, not 

## Call everything by its name in the last parameter position

## How do you pass values down through nested functions?
### Everything that "comes in" to a form is implicitly treated as a parameter
#### listed in the order they first appear

### **Keep a record of the aliases that a certain value is used under thruoghout composition, like "this is now the coll in map, but before it was the coll in omnimap, and before that it was the coll in deep-map**

## Point Free Lisp
### Composition operation: . or >

### (> sq abs)

### (map (> sq abs))

## borrowing:
### Auto-currying. All functions take 1 param

## Syntax:
### $tag aliases an expression

### %param aliases a parameter

### All plain words are references, eg __rat__ goes to __$rat__

## examples
### 1
#### ($map if (empty? %2) %2 (cons (%1 (first %2)) (map %1 (rest %2)))))

#### $map cons
##### 

#### ($probs map (comp sq abs))

### 2
#### map fn [] = []

#### map fn x:xs = cons . fn x xs

## rendering
### render unknowns as default names of enclosing fn

### carry names through calls

## Implementation
### Storage: 
#### '#:unbound{a {:code (reduce unbound/b {} _)}

#### b (assoc-in _1 (unbound/c _2) true)

#### c (conj (unbound/d _) :word)

#### d (vec _)

#### e (if (not false) (e _) false)}

### Cache: 

## _ or % for args?

## Name 1:1 function [input]->[output]?
### no, this only works for distincly type a -> type b, which isn't a huge majority

### lots of clojure fns are many to one

## Why is clojure map destructuring backwards?!?!

## param count is different than number of arguments to a function. [_] has 1 param, no funciton

## wtf is a function? how about lang doesn't make functions at all?

## proposition: everything created in this lang is possibly recursive replacement scheme. instead of function application, there is replacement
### templating with primitive evaluation left to right is the same thing as fns?

### No functions that take 0 arguments allowed

## Do I want (possibly infinite) #[[functional list]] code structure, or traced code structure?

## Examples
### max depth parentheses

### $max-depth-parentheses(max (fold-keep + (map $(case $1 "(" 1 ")" -1 :else 0) string)))

### (max-depth-parentheses 1)
