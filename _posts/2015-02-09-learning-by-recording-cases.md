---
layout: post
title: Learning by recording cases
date: 2015-02-09T20:00:12+00:00
author: Chan Le
permalink: /learning-by-recording-cases/
---
Learning by recording cases is a way to solve problem, by looking for a similar problem we encountered in the past, then try to apply the previous solution to the new problem. Think of finding price for a house, given historical data of previous similar deals. Price of a similar house in a similar location would be a good estimation. One natural solution to find a similar encountered problem is k-nearest-neighbors.

# Case-based reasoning:

The process goes as follow: Retrieval -> Adaptation -> Evaluation -> Storage. The AI agent first retrieve a problem from memory, then try to adapt the previous solution to current problem, then try to run & evaluate that solution, and finally store it in memory for future usages.

## Retrieval

k-nn is a method for retrieval. it's linear. However if we represent the case differently (look at the storage section), it's possible to retrieve the case in log(N) by representing the cases in a discrimination tree.

## Adaptation

For adaptation, there are several methods:

*   model-based method: already input files in python, similar process can be done in java. Find way from home -> restaurant, we can use a case where we go to office near restaurant, then using the model map to find way from office to restaurant.
*   recursive case based method: find the way from home to a restaurant, we can find way to office, then find way from office to restaurant.
*   rule based method: Using heuristic. For example, find the center of the city by look for tallest building. Find way back to home by reverse the path we came on.

## Evaluation

If we find way back home by reverse the path we came on, while evaluating we can find some paths are one-way only -> reject this solution and went back to adaptation/ retrieving phase.

## Storage

### Indexing

Indexing finding path in map problem: The example below modeling origin point as a way to represent the path. ![](https://www.dropbox.com/s/e98lht4h515xgep/Screenshot%202015-02-10%2011.56.55.png?dl=1)

### Discrimination tree

It's like the answer tree for 20-questions game. This add the benefit of look for a case take only O(logN). Add new cases take O(1) too by adding new discrimination rule ![](https://www.dropbox.com/s/hg97wpbs3ctx0tj/Screenshot%202015-02-10%2012.30.55.png?dl=1)

## Advanced

The process isn't always linear. It's possible to skip the adaptation phase if the retrieval phase return a perfect match. It's also good to store failure cases to anticipate & avoid going into those failure cases.  

 _This is an ongoing series of posts where I try to learn a concept by writing blog post about it. The screen shots from this post is taken from the [KBAI course](https://www.udacity.com/course/ud409) in Udacity._
