---
title: TTL Time Tracking + Stream of Consciousness
---

## my total time is in [[session time]]

## Starting at 10:00 EST [[December 2nd, 2020]]

## 10:16 installed, ran LESS

## Next step is get a working demo of all tailwind features in order to compare with less version [[TTL Strategy]]

## 10:23 For now, just using tailwind's demo https://play.tailwindcss.com/ as an example instead of building example local

## 10:25 Using https://nerdcave.com/tailwind-cheat-sheet as reference on tailwind classes [[TTL Class List]]

## 10:28 looking for source of tailwind builtin classes. perhaps make a transpiler for that to LESS?

## 10:28 cloning tailwindcss source

## 10:32 the source code for tailwindcss looks very different than what I would write in LESS. __don't think I'm transpiling the js source__. [[TTL Strategy]]

## 10:34 First step: get [[combinable prefixes/suffixes in LESS]]

## 10:37 [[TTL Combinatorial Names]] heading in http://lesscss.org/features/ might be useful if I can read off what the &s refer to in each case [[LESS]]

## 10:42 **exactly what I want to do** but SO says it won't work https://stackoverflow.com/questions/19602812/less-mixin-a-variable-class-name [[LESS]]

## 10:52 doesn't look like there's [[combinable prefixes/suffixes]] in [[LESS]].

## There are a **few hundred total classes in tailwindcss**? based off https://tailwind.build/classes [[TTL Class List]]

## **Clarifying quesitons** [[TTL Questions for Conaw]]
### Is it tailwindcss that doesn't work, or postcss?

### why doesn't tailwindcss work?

## **Does [[LESS]] help me implement tailwind at all?**

## 10:58 I have a meeting, **taking a break for ~30 minutes** [[session time]] 00:58

## 11:31 **back** __maybe only briefly__

## **New plan: get tailwind to compile every single class to css, then use text editor / write transpiler on that to get LESS** [[TTL Strategy]]

## Need to ask tailwind people how to get everything into css 

## 11:36 tailwind discord link https://discord.gg/7NF8GNe
### Hi, I'm trying to use Tailwind classes in a project that doesn't work with Tailwind. 
Is there a way to compile all Tailwind classes to one css file? something like
.bg-red-100{
background-color: #fff5f5; 
}
...

### posted 11:45

## Tailwind does that JS thing where their website is pretty and fluffy, hard to find deep documentation. if only ui people didn't make things so pretty

## **idea: make an html div for every class. then extract styles**
:PROPERTIES:
:ID:6098215e-d928-435a-a68f-5fdfb9f16b1e
:END:
### <div class="bg-red-400">

### extract styles using .getcomputedstyle [[TTL Scrape Computed Styles]]

### extract from however tailwind stores their styles

## 11:57 **how do tailwind classes interact?**
### A lot of them seem to have no interaction, which makes things easier

### what interaction is there, if any?

## 11:57 going to make txt file list of all classes with regex [[TTL Class List]]
### remove headers

### ^[^.]*\n

### remove * classes-won't deal with them yet

### \/.*$

### Convert to html
#### ">:)</div>\n

#### <div clas="

## 12:16 There are actually **1218 total classes excluding -* classes** according to https://tailwind.build/classes [[TTL Class List]]

## ((6098215e-d928-435a-a68f-5fdfb9f16b1e))
### 12:21 made class list html 

### it is beautiful ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fgraphminer%2F24cjIZQ75n.png?alt=media&token=929121e5-4f0f-4a72-bb4c-e91722413f08)

### next make js script that scrapes computed styles from all of these

## 12:26 **TAKING BREAK** [[session time]] 00:55

## 13:27 **BACK FROM BREAK**

## {{TODO null}} make a higher level view of these timeline cells with block refs

## 13:46 script not working in online demo tailwindcss

## 13:51 **It's actually easy to get 100% of tailwind classes compiled to css!** [[TTL Tailwind Compiled CSS]]
### this is **183k** lines long...

## [[TTL Questions for Conaw]]
### do you want global tailwind styles too?

## 14:19 How to computed style minus default style? https://stackoverflow.com/questions/42025329/how-to-get-the-applied-style-from-an-element-excluding-the-default-user-agent-s [[TTL Scrape Computed Styles]]

## 14:32 Got json with computed styles of divs with 1 class

## Made less mixin file. it passes the easy test [[Conaw]] messaged me!

## 15:16 added readme, pushed to github

## 15:25 **TAKING BREAK** [[session time]]: 01:58

## 16:51 **starting short session** to document + test what I have already

## 17:10 organizing my repo into folders

## 17:37 just made this Roam more graph-y. That was actually a big [[TTL Mistake]]. I should treat this page like daily notes, whereas before I was treating everyting as one document!!!

## 17:43 now testing on with tailwindcss examples

## first test https://play.tailwindcss.com/ completely failed
### seems like main reason why is `inset-0` which is one of the * classes I don't do yet

## 17:48 **TAKING BREAK** [[session time]] 00:57

## 18:56 **Starting up**

## According to [[Conaw]], need to use functions. It's not okay to copy compiled css. 
### copying compiled css would produce more value faster imo

## [[TTL Strategy]] **Old : use tailwindcss compiler to do all the combinatorial stuff,  copy hard code to less**

## [[TTL New Strategy]] **New: use functions to do as much as possible**
### figure out which pairs of [[TTL class category]] go together, make functions that take 

## [[TTL Feature Priorities]]
### everything that can modify background

## [[TTL Combinatorial Names]] https://stackoverflow.com/questions/31792181/how-to-join-variable-names
### possibility: use https://stackoverflow.com/questions/16724549/is-appending-class-names-within-a-class-with-less-bad-practices with list of &___ inside

## [[TTL Combinatorial Names]] **finally found how to combine names. use nested `each`**

## 19:21 [[TTL New Strategy]] make maps from name to style for each type, use nested each to combine them

## [[TTL Class List]] to names \(\)\{([^\}]*|\n)*\}

## [[LESS]] if you make a variable of a variable, you have to deref twice

## 20:36 got color+location combinations, for example bg-red-400 and placeholder-grey-100

## 20:37 **need general purpose way to sequence names where I can add to the front or back of the name** [[TTL New Strategy]]
### sequence([(class,attr,value)], list, (class,attr,value),list-entry)->(class,attr,value)

## 20:56 **break** [[session time]] 02:00

## 21:22 **start**

## Grunt can create custom less functions https://github.com/gruntjs/grunt-contrib-less

## Idea: use string functions to remove an item at the end of a list so that we can cover all the combinations of [a,b,c] including any number of elements missing

## 22:32 **break** [[session time]] 01:10

## 23:05 **ugh i keep working on this**

## Discovered &{} is an empty code block! this allows you to modify your `each` variables before you put them in the selector!

## ~00:00 **break** [[session time]] 01:00

## 05:38 **starting up again**

## What I've learned about [[LESS]]
### You can't declare variables inside the curly brackets of an `each`. Only selectors are code blocks.
#### You can always use the empty extension selector, &{}, to create a code block

### **user defined functions aren't supported out of the box**

### **only parameterized selectors, such as .myselect(@param){} are supported**

### **escaping strings is very important**. LESS supports all the regular css syntax, so it needs to escape differently in different contexts, and a lot.

### **you can iterate through the styles in a mixin with each as a map**

### After you use a string function, like replace, use e() to "escape" that string, which removes quotes around it

## 06:20 new project structure: two files, data.less, which has maps like {l:left; r:right; t:top; b:bottom} and fns.less, which has functions that use those maps

## 06:30 I'm using "null" to stand in for "" in maps and replacing them during the loop. this is ugly [[TTL Improvements]]

## 07:02 **BREAK** [[session time]] 01:24 

## end of 10 hours. Because I badly misunderstood the problem for the first 5 hours, I am still working.

## 10:19 **STARTING** writing up the [[TTL New Strategy]] I've been following

## 10:38 Adding opacity. This is the first one I've done that's an interaction between two classes, color and opacity. I'm doing this by putting the color loop inside an opacity loop (with null), and generating classes for each combination. 
### there is a standalone opacity property, but that applies to children, which isn't what we want.

## 11:17 got opacity done. How do I make a two class rule, (.class.class) tree-shake? 

## 11:19 Switching approach on opacity. Adding it into the color class, instead of having its own class {{Done null}}
### .hover:bg-pink-50-opacity-20

## 11:20 I may have a problem with opacity class + placeholder, or any pseudo-element. right now the opacity comes after, when it needs to come before {{Done null}}

## 11:37 Tailwind doesn't count visibility=hidden elements in its layout. It's a nice feature, but I'm not including it yet [[TTL Feature Priorities]]

## 11:38 I haven't been using css variables (--var). Tailwind uses them to communicate information between different elements. For example, __bg-opacity-30__ defines __--tw-bg-opacity: 30;__, and __bg-red-400__ defines --tw-bg-opacity:100;__. That means if color comes after opacity, the opacity doesn't work, right? but in tailwind, it does work somehow.

## 11:44 **taking break** [[session time]] 01:30

## 
