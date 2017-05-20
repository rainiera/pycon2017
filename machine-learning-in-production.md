## Snakes on a Hyperplane: Python Machine Learning in Production

speaker: Jessica Lundin  
time: Friday 5:10 pm - 5:40 pm  
[description](https://us.pycon.org/2017/schedule/presentation/673/)  

- Machine Learning Manager at Microsoft Research


**model performance: unknown production distribution**

- Production data won't be the same as pre-production training data
- techniques for suspected distribution differences between preproduction and production:
    - visualization (histograms, pairplots)
    - clustering (unsupervised techniques on top of supervised)
    - Kullback-Leibler (KL) divergence

**model performance: unbalanced problems**

- metrics
    - accuracy
    - precision
    - recall

- oversampling - upsample the rare class - add noise to 

- cost-sensitive classification:
    - rare-class upsampling with replacement
    - importance weighting
    - boosting
        - penalize your model where you incorrectly estimate
    - undersampling
- treat it as an anomaly detection problem (one-class SVM)

**snakes on a hyperplane**

- 2-D -> classes separated by a hyperplane
- SVMs
- the kernel trick

**practical tips**

**logging**
- timestamp, instance ids
- model run time
- model results, performance metrics
- model convergence errors

**auditing**
- manual process of digging into logs and data to resolve unexpected behavior


