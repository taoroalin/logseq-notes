---
title: TTL Strategy
---

## Tailwind is written in JS, but it compiles to css. Could just include the compiled css as LESS, but that would add 4M file size, because css isn't tree-shakeable. [[TTL Tailwind Compiled CSS]]

## Therefore one solution is to make tailwind's compiled css tree-shakable by LESS.

## There are also few other ways we can get the tailwind styles in structured form
### docs

### JS source

### [[TTL Scrape Computed Styles]] from rendered classes

## I looked at the [[TTL Tailwind Compiled CSS]], and it wasn't immediately obvious how to make everything tree-shakeable in LESS. 

## Instead, I started by giving tailwind classes to divs, and reading their computed styles. Then I can make one tailwind mixin for each class, including any style that class has (when applied to a div without any parents with tailwind classes).

## It has worked somewhat so far. next step is to test it, see what it's missing

## There may be multiple options for organizing the [[LESS]] util library
### 1 mixin per class (for example, .bg-red-400, .bg-red-600 are totally seperate mixins)
:PROPERTIES:
:ID:8866b57d-f13d-434a-8868-05b20a6f0826
:END:

### Generate repetitive mixins somehow, either with features in LESS for combining class names (which it seems don't exist)
#### 10:42 **exactly what I want to do** but SO says it won't work https://stackoverflow.com/questions/19602812/less-mixin-a-variable-class-name

### Copy the structure of compiled tailwind exactly to less

### Copy structure of tailwind source to less
#### less isn't expressive enough

## I chose ((8866b57d-f13d-434a-8868-05b20a6f0826)) because it's easy :)
