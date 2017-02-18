---
id: 240
title: 'KBAI: Classification'
date: 2015-03-30T00:55:13+00:00
author: Chan Le
layout: post
guid: http://blog.chan.io/?p=240
permalink: /kbai-classification/
categories:
  - Tech
---

Imaging that you've to tell which type an animal is: is it a bird, a mammal or a reptile? How do you do that? I bet you'll look at percepts/ properties of the animal to decide: whether the animal has feather or not, whether the animal is warm-blooded or cold-blooded... There are $latex 2^n $ properties combination available, hence there are $latex 2^n $ actions/ decision we can make from those properties.

# Formality of concepts:

The more formal a concept is, the more strictly/ explicitly defined it is. Example: Right Angle > Reptitle > Foo > Holiday > Inspirational > Saltiness

## Axiomatic Concepts

Conceps that are well-defined as list of necessary and sufficient conditions, such as a Circle: set of point have length R from a center point.

## Prototype Concepts

Base concepts defined by a typical example with override properties. Ex: A **chair** with 3 legs, without back

## Exemplar concepts:

Defined by abstraction of instances or exemplars of the concept. Ex: beauty, defined by beauty of a scene, a figure... This don't even have typical definition.

# Top-down classification:

This is use when we have some properties that can differentiate concepts right away. For example, has wing or not can define whether the animal is a bird or a reptile.

# Bottom up classification

Look at the nodes properties and abstract it in a bottom-up manner. Useful for things like predict the stock market.

 _This is an ongoing series of posts where I try to learn a concept by writing blog post about it. The screen shots from this post is taken from the [KBAI course](https://www.udacity.com/course/ud409) in Udacity._
