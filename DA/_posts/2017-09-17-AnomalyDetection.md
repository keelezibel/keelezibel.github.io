---
layout: single
title: Anomaly detection
categories: Coding
tags: 
- 
- 
---

Anomaly detection or outlier detection are basically referring to the same problem. What constitutes as an outlier may be vague as the
decision to rule the observation as an outlier/anomaly is up to a human expert.
<br /><br />
Generally, an outlier is simply an observation that deviates from the normal pattern. So, how do we know what is the normal pattern? Is it
possible for intentional attacks such that fradulent activties appear as the norm instead? If so, how do we handle it?
<br /><br />
Challenges of outlier detection: <br />
1. Domain knowledge of normal behavior
2. Unbalanced data (anomalies significantly lesser than normal data)
3. Evolving anomalies

<br />
Following are the types of anomalies: <br />
1. Point Anomaly (single instance anomalous to the rest in n-dimension space)
2. Contextual Anomaly (single instance anomalous within a context)
3. Collective Anomaly (multiple instances collectively becomes anomalous though they are not individually)

{% include figure image_path="/assets/posts/2017-09-17-AnomalyDetection/anomaly.png" caption="Photo Credit: Numenta, Point and Contextual Anomaly" %} 

<br />
Methods:
# Statistical
# Density based 
# Clustering based
# 1 Class Support Vector Machine(SVM)

<br />
[Writing in progress...]
<br />
# Resources:
[Jing Gao, Buffalo](https://www.cse.buffalo.edu//~jing/cse601/fa12/materials/outlier_detection.pdf)
