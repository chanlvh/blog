---
layout: post
title: 'KBAI: Logic'
date: 2015-03-30T03:32:12+00:00
author: Chan Le
permalink: /kbai-logic/
---
# Formal logic

## We need it because of two reasons:

*   Soundness: Only valid conclusions can be proven
*   Completeness: All valid conclusions can be proven

## Contains many part:

*   Predicate: Function map object arguments to true/false
*   Implication: If lay-eggs(animal) || fly(animal) => bird(animal))
*   Conjunction/ Disjunction: and/or

## Some reminder:

### Morgan's rule:

$latex \neg (A \wedge B) = \neg A \vee \neg B $

### Rules of inference:

*   Modus ponens: p => q, we have p hence we can conclude that q
*   Modus Tollens: p => q, we have !p hence we can conclude that !q

These two rules aren't feasible for complex logics, because of computation power limitation, there are two other quantifier:

### Universal Quantifiers

$latex \forall and \exists $

## Resolution Theorem Proving

### Simple Example

*   We know: $latex \neg can-move \Rightarrow \neg liftable $ (which is the same as $latex can-move \vee \neg liftable$
*   We find: $latex \neg can-move$
*   We need to prove $latex \neg liftable$

RTP is proving by negation, hence we negate the last one, we get:

*   assume: $latex liftable$

Next step, we find a negation of this assumption, we found one in the 1st sentence, hence we cross that two away: $latex can-move $ $latex \neg can-move$ The only predicate of 1st sentence is can-move, we try to find a negation of that in the other sentences and found one in 2nd sentence -> cross that two -> we left with nothing which is a negation. Hence the original assumption can't be true. Hence liftable is true.

### Complex example:

We know: $latex can-move \vee \neg liftable \vee \neg battery-full$ We find: $latex \neg can-move$ We find: $latex battery-full$ Assume: $latex liftable$ Using similar approach we also came up with null, hence the object is not liftable. Horn Clause is a disjunction that contain at most 1 positive literal.  

 _This is an ongoing series of posts where I try to learn a concept by writing blog post about it. The screen shots from this post is taken from the [KBAI course](https://www.udacity.com/course/ud409) in Udacity._
