---
id: 215
title: Incremental Concept Learning
date: 2015-02-10T00:30:22+00:00
author: Chan Le
layout: post
permalink: /incremental-concept-learning/
categories:
  - Tech
---

![](https://www.dropbox.com/s/173axudui2zsbh6/Screenshot%202015-02-10%2014.24.47.png?dl=1)   The AI agent generalize or specialize a concept while learning, depends on whether the concept fits the current definition or not. Think of it as a child try to learn the concept of a dog. At first, he may think of the dog as any animal that has four legs. Meeting a cat and being told that it's not a cat will help him **specialize** the concept to exclude cat, and meeting a dog that is different from his concept of dog will help him **generalize** the concept to include the new dog.

# Heuristics use in ICL:

Each role/ link in a concept should not be fixed constant, but variables which learning can change.

## Forbid-link heuristic:

![](https://www.dropbox.com/s/1pli9oasx27giln/Screenshot%202015-02-10%2015.23.02.png?dl=1) While specialization, a link must be absent to be a positive match of the concept. => Specialization to exclude feature

## Drop-link heuristic:

![](https://www.dropbox.com/s/68p7fula5ucopri/Screenshot%202015-02-10%2015.18.26.png?dl=1) While generalization, comparing representation of the concept and the new positive example, then drop link from old concept so that the new concept also match the example and the old concept. => Generalization to ignore feature

## Required-link heuristic:

![](https://www.dropbox.com/s/45i4d1ud27planb/Screenshot%202015-02-10%2015.20.16.png?dl=1) While specialization, comparing representation of the concept and the new negative example, then add "must" label to links that are not in the example. => Specialization to require feature. Perhaps instead of drop/add link we could also have "weight" of the link, then add/ remove weight as necessary.

## Enlarge-set heuristic:

![](https://www.dropbox.com/s/zi0mgpydxfzixxq/Screenshot%202015-02-10%2015.24.57.png?dl=1) While generalization, there can be multiple objects/link in the same role as one object/link in a concept, hence ESH works by adding "or object B" to "object A" to broaden the concept

## Climb-tree heuristic:

![](https://www.dropbox.com/s/zmyqfo0ipla64j0/Screenshot%202015-02-10%2015.25.35.png?dl=1) While generalization, we can learn from background knowledge (A is C && B is C) by replacing "A or B" with C. => generalization with background knowledge

## Close-interval:

Expand the range of value to make the example a positive of the concept. Ex: expand dog size definition to match more dogs

# Comparing to ML:

In ML, we have lots of example given at the beginning. We can't do statistical ML with small number of examples, hence ICL is better especially when examples are given throughout the learning process.  

 _This is an ongoing series of posts where I try to learn a concept by writing blog post about it. The screen shots from this post is taken from the [KBAI course](https://www.udacity.com/course/ud409) in Udacity._
