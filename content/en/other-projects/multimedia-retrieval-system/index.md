---
title: "Multimedia Retrieval System: 3D Shape Search with Feature-Based Similarity"
date: 2025-11-14T00:00:00+02:00
draft: false
weight: 6
summary: "A 3D shape retrieval system that normalizes mesh data, extracts geometric descriptors, and retrieves similar models through feature-based similarity search."
tags: ["Python", "Open3D", "NumPy", "SciPy", "Scikit-learn", "3D Shape Retrieval", "Multimedia Retrieval", "Feature Extraction", "Similarity Search", "k-NN", "ANN", "Streamlit", "Course Project"]
showAuthor: false
---

## Overview

**Multimedia Retrieval System** is a 3D shape retrieval project focused on building a content-based retrieval pipeline for 3D mesh models. The system allows a query shape to be compared against a database of 3D objects and returns the most similar meshes based on extracted geometric features. The project covered the full retrieval pipeline: reading and visualizing 3D meshes, preprocessing and cleaning inconsistent models, normalizing shapes, extracting shape descriptors, designing a similarity-based query algorithm, improving retrieval quality, and exploring scalability through efficient neighbour search. The final system combines 3D geometry processing, feature engineering, similarity measurement, and interactive retrieval.

## System Pipeline

The project was implemented as an end-to-end 3D shape retrieval system. The pipeline included:

- loading and visualizing 3D mesh models,
- preprocessing meshes with highly inconsistent resolution and scale,
- resampling overly coarse or dense meshes,
- normalizing shapes into a shared coordinate frame,
- extracting elementary and distribution-based 3D shape descriptors,
- standardizing features for comparison,
- computing similarity between query shapes and database shapes,
- returning the top matching models,
- improving scalability with nearest-neighbour search and an interactive interface.

This pipeline was designed to make 3D models comparable despite differences in mesh density, position, scale, and original modelling quality.

## Normalization

A key part of the system was shape normalization. The goal was to make all 3D objects comparable before feature extraction and retrieval.

The normalization process included:

- translating each mesh so that its barycenter was moved to the origin,
- scaling each mesh to a unit size based on its bounding-box extent,
- aligning each mesh to its principal axes,
- applying a flipping test to make orientation more consistent.

This step reduced the influence of irrelevant differences such as original object position, scale, and rotation. As a result, later descriptors could focus more on shape structure.

## Feature Extraction

After normalization, each 3D shape was converted into a fixed-length feature vector. The system used both elementary descriptors and distribution-based descriptors.

The elementary descriptors included:

- surface area,
- volume,
- compactness,
- 3D rectangularity,
- diameter,
- convexity,
- eccentricity.

In addition, the system extracted five shape distribution descriptors:

- A3: angle between three sampled points,
- D1: distance from barycenter to a sampled point,
- D2: distance between two sampled points,
- D3: square root of the area of a triangle formed by three sampled points,
- D4: cube root of the volume of a tetrahedron formed by four sampled points.

To improve descriptor stability, area-weighted surface sampling was used instead of simple vertex-index sampling. This helped produce smoother and more consistent histograms for similar shapes.

## Query Algorithm

The query system was designed to compare an input 3D model with all shapes in the database and return the most similar results.

The first query attempts used Euclidean distance and cosine distance, but the results were poor because different feature groups had different value ranges and levels of reliability. To improve retrieval quality, the similarity computation was redesigned.

The improved query algorithm used:

- Z-score normalization for single-value descriptors,
- L1 distance for elementary descriptors,
- Earth Mover's Distance, implemented through 1D Wasserstein distance, for histogram-based descriptors,
- weighted feature distances to balance the contribution of different descriptors.

This produced a more meaningful similarity score between the query mesh and database meshes. After the improvement, the system retrieved more visually and semantically similar shapes compared with the earlier Euclidean and cosine distance approaches.

## Scalability and Interface

To make the retrieval system more practical for larger datasets, the project also explored scalable search methods. Exact k-nearest-neighbour search was used as a correctness baseline, while approximate nearest-neighbour search was introduced to reduce query time.

The system also included feature-space visualization using t-SNE, which helped show how different object classes were distributed in the extracted feature space. A Streamlit-based interface was developed to allow users to upload a query mesh and view retrieved shapes interactively.

## My Contributions

This was a group project, and I contributed to the implementation and technical development of the retrieval pipeline.

My main independent contributions were the **normalization**, **feature extraction**, and **query algorithm** components.

- Independently implemented the 3D mesh normalization pipeline, including translation to origin, unit-size scaling, principal-axis alignment, and orientation consistency checks.
- Independently implemented the feature extraction process, including elementary 3D descriptors and distribution-based shape descriptors such as A3, D1, D2, D3, and D4.
- Improved descriptor stability by using area-weighted sampling for shape distribution histograms.
- Independently designed and implemented the feature-based query algorithm for retrieving similar 3D shapes.
- Tested different similarity measures, including Euclidean distance and cosine distance, and identified their limitations for this retrieval task.
- Improved the retrieval method by combining Z-score normalization, L1 distance for elementary descriptors, Earth Mover's Distance for histogram descriptors, and weighted feature distances.
- Contributed to the final report, technical explanation, and result interpretation.

## Tools and Methods

**Tools:** Python, Open3D, NumPy, SciPy, Pandas, Matplotlib, Scikit-learn, Streamlit  
**Methods:** 3D mesh processing, normalization, feature extraction, shape descriptors, histogram descriptors, similarity search, k-nearest neighbours, approximate nearest neighbours  
**Descriptors:** Surface area, volume, compactness, rectangularity, diameter, convexity, eccentricity, A3, D1, D2, D3, D4  
**Focus Areas:** Multimedia retrieval, 3D shape retrieval, content-based retrieval, geometric similarity, feature engineering

## Project Material

<a href="/files/Multimedia_Retrieval_System_Final_version.pdf" target="_blank" rel="noopener noreferrer">
View the full report
</a>