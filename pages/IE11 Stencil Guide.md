---
title: IE11 Stencil Guide
---

## If your component has children, but doesn't render <slot>, the children will be rendered anyway. To avoid this, use <div style="display:none"><slot /></div>. 

## Css Grid works on ie11, but use span, not end, to set how many grid cells something takes up. End=-1 doesn't work.

## Putting shadow and non-shadow things in one div causes rendering issues. For example, <div><p>hi</p><slot /></div> doesn't work, because the div has <p> child in shadowdom, and <slot> child outside. Instead, make slots only children.

## Don't iterate through children of components. Instead make query that works if shadowdom is just a div

## Moving nodes around in dom with appendChild isn't reliable.

## use event.key not event.keyCode for onkey

## scrollX doesn't work

## portal {{Todo null}}
### import styles in tsx
