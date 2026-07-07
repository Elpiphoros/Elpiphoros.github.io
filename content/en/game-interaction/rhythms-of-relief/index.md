---
title: "The Rhythms of Relief: A Stress-Relieving Music Recommender System"
date: 2024-11-01T00:00:00+02:00
draft: false
weight: 5
summary: "An interactive music recommender system prototype designed to support student stress relief through audio feature extraction, k-Means clustering, and user-controlled preference adjustment."
tags: ["Python", "Librosa", "k-Means", "Music Recommender System", "HCI", "Interaction Design", "User Study", "Audio Feature Extraction", "Prototype Design", "Student Well-being", "Course Project"]
showAuthor: false
---

## Overview

**The Rhythms of Relief** is an interactive music recommender system prototype designed to support student stress relief. The project explores how music recommendation can be personalized for students who use music as a way to regulate stress.

The project investigates how students choose different types of music when they feel stressed. The system uses student-curated stress-relief songs, extracts audio features, groups songs through k-Means clustering, and presents recommendations through an interactive prototype.

The project combines music information retrieval, machine learning, interaction design, and user study methods.

## Research Focus

The main research question was whether a hybrid music recommender system could be developed to support emotion-based stress coping for university students.

The project focused on three related questions:

- what musical features may contribute to stress reduction for students,
- whether student-selected stress-relief songs can be grouped through k-Means clustering based on acoustic features,
- how effective an interactive recommender prototype can be in providing personalized songs for stress coping.

A key idea behind the project was that stress-relief music is not one-size-fits-all. Some students may prefer calm, soft, and relaxing songs, while others may use energetic or motivating music to process stress.

## Data and Audio Feature Analysis

The dataset was built from student-curated stress-relief songs. It combined songs from an existing student playlist with additional songs collected through an exploratory survey.

Audio features were extracted using Python and Librosa. The analysis focused on features such as:

- tempo,
- RMS energy,
- spectral centroid,
- spectral contrast,
- spectral flatness.

After preprocessing and feature selection, k-Means clustering was used to identify groups of songs based on their audio characteristics. The cluster analysis suggested that student stress-relief music could broadly be understood through two coping strategies: calm and relaxing music, and energetic or motivating music.

This finding supported the need for personalization in music recommendation for stress relief. A system that only recommends slow or relaxing music may not match every student's preferred way of coping with stress.

## Prototype Design

The prototype was designed as an interactive music recommender system. Users could listen to recommended songs, skip songs, like songs they preferred, and adjust the direction of recommendations through several preference controls.

The prototype included controls for:

- slower or faster songs,
- more subtle or more intense music,
- melancholic or uplifting mood,
- liking and exporting selected songs,
- viewing the user's listening journey across clusters.

The purpose of the prototype was not only to recommend songs automatically, but also to give users agency over the recommendation process. This was especially important because stress coping is personal and context-dependent.

![Prototype interface of The Rhythms of Relief](prototype-interface.png)

*Prototype interface showing music playback, preference adjustment controls, liked songs, and cluster-based recommendation navigation.*

## User Testing

The prototype was tested with students to evaluate its usability, recommendation relevance, and overall design concept. Participants interacted with the system and then completed a questionnaire about their experience.

The results showed generally positive responses. Participants rated the design concept highly, and many reported that the prototype provided appropriate music choices for stress relief and matched their preferences. The test also revealed areas for improvement, such as clearer interface guidance, more flexible preference controls, a larger song database, and more reliable audio feature extraction.

Overall, the user testing suggested that the concept had promising potential, but that the system would need further development before becoming a fully functional hybrid recommender system.

## My Contributions

This was a group project, and I contributed to the research, prototype, and evaluation process as part of the team.

- Participated in designing the concept of a music recommender system for student stress relief.
- Contributed to the research process, including discussions of stress coping, music personalization, and recommender system approaches.
- Helped organize and interpret student-curated stress-relief song data.
- Contributed to the audio feature analysis and clustering-based recommendation approach.
- Participated in prototype design and user testing.
- Helped analyze user feedback on usability, preference matching, and recommendation effectiveness.
- Contributed to the final report and presentation materials.

## Tools and Methods

**Tools:** Python, Librosa, k-Means clustering, interactive prototype interface  
**Methods:** Audio feature extraction, cluster analysis, exploratory survey, user testing, questionnaire analysis  
**Focus Areas:** Music recommendation, student stress relief, personalization, HCI, user experience  
**Data:** Student-curated stress-relief songs and prototype testing feedback

## Project Material

<a href="/files/FinalReportProper.pdf" target="_blank" rel="noopener noreferrer">
View the full report
</a>