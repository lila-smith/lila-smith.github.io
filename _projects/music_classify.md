---
layout: project
title: DDR - Dance Dance Robotics
date: September 29, 2014
image: confusion.png
---
By, Austin Lawrence (Ablarry91@gmail.com)
EECS-349: Machine Learning, Northwestern University

A TECHNICAL WRITEUP PDF OF THIS PROJECT IS AVAILABLE FOR DOWNLOAD [HERE](https://www.dropbox.com/s/d28be3kp65hij3v/DDR_Final_Paper.pdf?dl=0)

## Intro
The objective of this project is to classify music and use this information to instruct a specific dancing scheme for a robot.

## Motivation
As consumer-level robots slowly find their place in a typical household, human personification is inevitable.  We argue with automated personal assistants, name our vacuums, and marvel at their literal interpretation of the world.  Despite this, machines of this category still lack the ability to facilitate an emotional response between the machine and a human.  To go beyond the status of an appliance, and possibly use robotics as a means of emotional therapy or entertainment, much development is still needed to create machine that reacts in a human-like manner.  Perhaps the most successful case of this may be the querky [Jibo](https://www.jibo.com/) robot, though even it has noticeable limitations.  Though not quite analogous to emotion, having an ability to classify the genre of an mp3 music file is a step in the direction of autonomous emotion classification.

## Method
As a quick start to the project, the [Million Song Dataset](http://labrosa.ee.columbia.edu/millionsong/) provided a foundational amount of data in the meta and analytical nature.  Thanks to the information available in this dataset, several characteristics of songs can be utilized, including:

* Duration: the length of a song
* Artist familiarity: an estimation of how familiar the artist is to the world
* Artist hotness: an estimation of how popular an artist is
* Song hotness: an estimation of how popular a song is
* End of fade in: an estimation of when the song finishes fading in
* Start of fade out: an estimation of when the song begins to fade out
* Loudness: Overall loudness of a song in dB
* Mode: whether a song is in major or minor key
* Key: an estimation of the song’s key
* Tempo: an estimation of how fast the song is
* Time signature: an estimation of a song’s time signature

Using Python [SQLite](https://www.sqlite.org/) to generate the database and [Weka](http://www.cs.waikato.ac.nz/ml/weka/) for learning purposes, a Bayes Net classifier was found to generate the best results, next to a J48 Decision Tree classifier.  Success is measured against the genre provided by the Million Song Dataset and the classification accuracy.

## Results
Between decision tree, clustering, naïve Bayes, and Bayes Networks, the latter was found to generate the highest classification accuracy. At a classification accuracy of 43.7% against a ZeroR accuracy of 18.7%, much can still be done to improve the quality of this classifier.  Regardless, this implementation was successful in correctly identifying the majority class for each instance.   The mot influential features were artist hotness, artist familiarity, and loudness.

## Discussion
The most interesting observation to make from these results corresponds to the chronological development of these independent genres.  For example, pop has a higher misclassification for the music genre rock.  From a sequential standpoint, much of where pop is today is due to the musical influence of rock that developed prior, such as upbeat tempos, loud choruses, and popularity in mainstream media.
Additional musical features may help improve the quality of classification, provided that the features are more distinct to particular types of music.  Features not available in the dataset used in this study, such as the presence of a vocalist, deviation of tempo, and deviation of loudness may help distinguish various classes from their peers.

##Conclusion
Though this exercise proved useful in classifying musical genres with a heightened reliability, more work is to be done to improve accuracy to a meaningful level.  Going forward, it is of interest to transition this study into the area of feature extraction from mp3 files, as opposed to acquiring this information from another source in a precompiled format.  Doing so may influence the types of features available to study, and optimistically, improvement in the quality of musical genre classification.


