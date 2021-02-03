---
title: Copy Pasta
---

## Search
### site:(lesswrong.com | forum.effectivealtruism.org | overcomingbias.com | openphilanthropy.org | alignmentforum.org)

### site:(lesswrong.com | forum.effectivealtruism.org | overcomingbias.com | openphilanthropy.org | alignmentforum.org | slatestarcodex.com | gwern.net | guzey.com | applieddivinitystudies.com | lukemuehlhauser.com | https://paulfchristiano.medium.com/ | https://sideways-view.com/ | https://ai-alignment.com/ | http://applieddivinitystudies.com/ )
:PROPERTIES:
:ID:fb8e8432-ae49-4ddf-b6e4-4a0a5f1fee51
:END:

### #Blogs

## Python Print All
### print(" ".join([f"{k}: {v}" for k, v in {**locals(),**{"SELF":vars(self)}}.items() if'__'not in k and'self'not in k and not callable(v)]))

## Union Find
### ```python
uf=list(range(len(points)))
def union(x, y):
    uf[find(x)] = find(y)

 def find(x):
     if x != uf[x]:
         uf[x] = find(uf[x])
     return uf[x]```
