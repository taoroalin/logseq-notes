---
title: TTL New Strategy
---

## Why do i need a new strategy? [[TTL Mistake]] 

## Basic idea: make lists of "colors", "places to put colors", "pseudo-selectors", ect, and combine them using [[LESS]] loops and functions. 

## Lets call these things, such as "places to put colors", [[TTL Aspects]]

## We could make a named function, like tw(aspect,aspect...) that takes in a list of aspects and produces css rules. This isn't as elegant as concatenated class strings like "aspect-aspect-aspect", so i'm not doing it.

## What I am doing is looping through combinations of aspects and generating mixins for each one.

## Many [[TTL Aspect]] templates, like {pseudo-selector:}{color-place}-{color} have optional aspects, (here it's pseudo-selector). The way I'm dealing with this is adding a `null` element to each list, and rendering that as an empty string.
### this results in some mixins where every aspect is null. They don't get shipped, and don't really interfere with anything, but could be elmininated in a [[TTL Improvements]]

### You need to add the punctuation between aspects, like - or :, only if the aspect is not null.

## 
