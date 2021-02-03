---
title: Reagent
---

## https://boiling-peak-00646.herokuapp.com/

## https://github.com/taoroalin/seven-guis

## Remind people to hard refresh heroku!

## How do you make it ignore cache when reloading if there's a new version out

## Is state stack or change stack better for Circles? probably change stack

## tried but failed
### auto routing based on vars

### auto inverse function c->f f->c ? 

## timer can go slightly over

## temp turned off timer

## Should I?
### avoid double deref renders?

## Supporting box sums
### keep links from in-box to box, and box to uses-box, so you don't have to recompute range sum every time

## [[Conaw]] said someone went from 0 clojure to finishing 7 GUIs in 7 hours. I can confidently say I've never met someone that good at programming.

## Connor advice
### cells
#### left righ arrow move

#### range sum

#### save text on parse fail {{Done null}}

#### copy paste in lots of data

#### stress test

#### copy appearance of sheets

#### Good propagation
##### bfs, add all descendents idx to "dirty" set

##### new bfs: set que to [input-node]

##### evaluate que head, remove from dirty. check all its backlinks

##### for each backlink, if none of that link's forward links are dirty, add to que

##### if que is empty and dirty is not, there is recursion. quit.

### circle
#### "leaves a lot to be desired"

### crud
#### say that search is for last names {{Done null}}

#### make search performant with 100,000 entries {{Done null}}
##### Store in sorted set

##### Whenever set or filter changes, get lazy rsubseq

##### Only render what fits on screen

##### Realize lazy subseq on scroll

##### Need to lazily get filtered people, but be able to query by index later

##### FUCK do I need to handle inserts into filtered in constant time?

## Figwheel stopped 
