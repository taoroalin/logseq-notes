---
title: Roam Parser
---

## TODO [[Haskell]][[Read]] https://www.haskell.org/onlinereport/derived.html#derived-appendix

## [[Instaparse]][[Adding Matching Lookahead]] ((fd6c316f-6802-4f50-96a8-a7d987c96cbb))
### [[GLL]] algorithm: worst case time: O(n^3). short for Generalized ll
#### rd parsers, control flow follows structure

#### Allows for grammar rule factorisation. is that seperating out common components of different rules?

#### Everything defaults to plaintext. that's a bit of a problem.

## [[Roam Parser]] is there [[Priority]]? yes. for example, ** this is** [[Bold ** Page]] 
### non cosmetics

### cosmetics

## [[Clojure]] cljc conditional is #?(...). splicing with #?@(...)

## dilbert's essay on how to write
### I went from being a bad writer to a good writer after taking a one-day course in “business writing.” I couldn’t believe how simple it was. I’ll tell you the main tricks here so you don’t have to waste a day in class.

Business writing is about clarity and persuasion. The main technique is keeping things simple. Simple writing is persuasive. A good argument in five sentences will sway more people than a brilliant argument in a hundred sentences. Don’t fight it.

Simple means getting rid of extra words. Don’t write, “He was very happy” when you can write “He was happy.” You think the word “very” adds something. It doesn’t. Prune your sentences.

Humor writing is a lot like business writing. It needs to be simple. The main difference is in the choice of words. For humor, don’t say “drink” when you can say “swill.”

Your first sentence needs to grab the reader. Go back and read my first sentence to this post. I rewrote it a dozen times. It makes you curious. That’s the key.

Write short sentences. Avoid putting multiple thoughts in one sentence. Readers aren’t as smart as you’d think.

Learn how brains organize ideas. Readers comprehend “the boy hit the ball” quicker than “the ball was hit by the boy.” Both sentences mean the same, but it’s easier to imagine the object (the boy) before the action (the hitting). All brains work that way. (Notice I didn’t say, “That is the way all brains work”?)

That’s it. You just learned 80% of the rules of good writing. You’re welcome

## [[Clojure]] need to use :refer-macros to import macros

## in figwheel, macros must be in .clj file?

## Fuck I created the whole .insta file before testing because in my experience instaparse has great error messages, but apparently not! just crashed with no message!

## Regex is much faster than Instaparse, so you always want to regex  when you don't need [[Instaparse]]

## Parsing external URLs
### currently only accepting http, https, www.

### In order to use auto-whitespace, I need to keep all tokens atomic. 

## Experiments: in this block is nonsense that tests the current Roam parser
### just text
:PROPERTIES:
:ID:1682114e-f404-43df-ba60-782fbff65d6e
:END:

### **[[December 4th, 2020]]**

### __**boldi**__

### {{[[December4th,2020]] null}}

### {{embed ((1682114e-f404-43df-ba60-782fbff65d6e))}}

### [block is thing [[December 4th, 2020]]](((1682114e-f404-43df-ba60-782fbff65d6e)))

### www.graphminer.com

### $$latex$$ {{https //twitter.com/robinhanson/status/1335053605037072390}}

### 
