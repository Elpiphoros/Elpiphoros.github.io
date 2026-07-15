---
title: "Triangular Classifiers and k-NN: Experimental Research on Synthetic Data"
date: 2024-11-04T00:00:00+02:00
draft: false
summary: "An experimental research project studying how k-nearest neighbor classification behaves on synthetic 2D data with a triangular separator."
tags: ["Python", "k-NN", "Classification", "Synthetic Data", "Experimental Research", "Data Mining", "Computational Experiment", "Course Project"]
showAuthor: false
---

## Overview

**Triangular Classifiers and k-NN** is a coursework project focused on experimental research. The project studied how k-nearest neighbor classification behaves on synthetic two-dimensional data when the true class boundary is defined by a triangular separator.

In the experiment setup, points inside a triangle were assigned one class, while points outside the triangle were assigned another class. Instead of using the known triangular classifier directly, the project tested how well k-NN could approximate this classification rule under different data conditions.

The project investigated three factors:

- the density of labeled points,
- the fraction of outliers,
- the perimeter of the triangular separator.

## Experimental Design

The experiments used synthetically generated 2D point sets. For each setting, labeled points were generated inside a square domain, and 10,000 random test points were classified using k-NN. The number of misclassified test points was then counted. Each experiment was repeated 20 times, and the mean and standard deviation of the misclassification counts were reported.

The first experiment varied the number of labeled points to study the effect of data density. The second experiment varied the fraction of outliers by randomly flipping some labels. The third experiment varied the scale of the triangle to study whether the perimeter of the separator affected k-NN performance.

## My Contributions

This was a group experimental research project. My main contribution was **Experiment 3**, which examined the relationship between the scale of the triangular separator and the number of k-NN misclassifications.

I independently implemented the third experiment and interpreted its results. This included setting up different triangle scale factors, running repeated simulations, calculating the mean and standard deviation of misclassification counts, and explaining why a larger triangle perimeter led to more misclassifications.

## Results

The experiments showed that k-NN performance depends strongly on the structure of the labeled data. Higher point density reduced the number of misclassifications, while a higher outlier fraction increased misclassifications non-linearly.

For Experiment 3, the results showed that increasing the scale of the triangular separator also increased the number of misclassifications. A likely explanation is that a larger triangle has longer boundary edges, creating more regions where nearby points from different classes can influence the k-NN majority vote.

## Tools and Methods

**Tools:** Python, data visualization tools  
**Methods:** k-nearest neighbor classification, synthetic data generation, repeated experiments, parameter variation, mean and standard deviation analysis  
**Focus Areas:** classification behavior, experimental research, geometric decision boundaries, misclassification analysis

## Project Materials

<a href="/files/triangular-classifiers-knn-report.pdf" target="_blank" rel="noopener noreferrer">
View the final report
</a>