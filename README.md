# Oversampling Longitudinal Compositional Data for Classification of Microbiome Samples

## Abstract

Microbiome data analysis faces multiple challenges, including compositional constraints, high sparsity, and high dimensionality. In longitudinal studies, these challenges combine with temporal dependencies, further complicating the analytical process. Additionally, in clinical research, disease samples are typically far fewer than healthy controls, leading to severe class imbalance problems that reduce model recognition capabilities for minority classes. This study, using postpartum depression prediction as an application scenario, developed and evaluated a systematic framework aimed at addressing class imbalance in time-series microbiome data through oversampling techniques.

We conducted a systematic comparative analysis of microbiome data from the BASIC prospective study at Uppsala University Hospital, evaluating different zero-value replacement strategies, feature selection methods, data transformation techniques, and oversampling algorithms. Results showed that row-level zero-value replacement, feature selection based on early time point data and labels, centered log-ratio transformation after feature selection, and oversampling with conditional generative models collectively constituted the most effective data processing pathway. This framework increased the recognition rate of minority class samples from a baseline of near zero to over 0.60, significantly enhancing model performance on imbalanced datasets.

The research also revealed that data completeness is crucial for model performance; when missing data was introduced, predictive performance declined significantly even with the complete processing workflow applied. Furthermore, our results indicated that traditional deep learning generative models like conditional Generative Adversarial Networks and conditional Variational Autoencoders struggle to effectively learn distributions from small samples, while statistical models such as conditional Gaussian Mixture Models and conditional Dirichlet distributions perform better with limited samples.

This study provides a viable solution for addressing class imbalance in time-series microbiome data. The developed framework is not only applicable to postpartum depression prediction but can also be extended to other research areas involving time-series microbiome data, such as mental health, allergic diseases, and metabolic disorders, laying the foundation for the application of microbiome analysis in clinical prediction and early intervention.

## Repository Structure

This repository contains code used in our analysis of longitudinal microbiome data with class imbalance problems. The main notebooks are organized as follows:

### Complete Processing Workflows

- **#Final - A**: Main project code, complete processing workflow for data subset A
- **#Final - B**: Complete processing workflow for data subset B
- **#Final - C**: Complete processing workflow for data subset C

### Processing Steps and Comparisons

- **#Final - Step1 Zero-Replacing**: Comparison of methods for handling zero values in high-sparsity matrices during preprocessing
- **#Final - Step2 Feature-Selection**: Comparison of feature selection approaches using cGMMs:
  - Method I: Using data and labels from the first two time points
  - Method II: Using data from the first two time points and labels from the last time point
  - No feature selection baseline

- **#Final - Step2.5 Method I**: Results comparing different oversampling methods with feature selection Method I
- **#Final - Step2.5 Method II**: Results comparing different oversampling methods with feature selection Method II
- **#Final - Step2.8 K-Value**: Selection of optimal number of features
- **#Final - Step3 Data-Transformation**: Comparison of optimal data transformation methods and their application points

### Other Dataset Application: GMAP for Food Allergies
We applied our framework to the GMAP dataset on food allergies, using the same processing steps as in the postpartum depression analysis (Final A workflow). Key outcomes include:

1. **Identical Workflow**: Employed row - level zero - value replacement, early time - point feature selection, centered log - ratio transformation, and conditional generative model oversampling.
2. **Performance Improvement**: Achieved significant enhancement in model performance for minority class samples related to food allergies (Sensitivity from 0.08 to 0.63).
3. **Generalizability**: Validated the framework's applicability across different microbiome datasets. 

