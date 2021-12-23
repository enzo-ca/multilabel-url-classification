# Multilabel URL Classification using Feature Learning
By: Enzo Casamassima
For: CMPE 789 - CyberML - Spring 2021

## Purpose

For CMPE-789 the objective was to pick a topic and elaborate a research project that would replicate some existing results. In addition, we had to conduct original research and try to come up with different approaches not previously used.

Keywords: URL Classification, Malicious URL detection, t-SNE, CNN, NLP.

## Description of files

* **Final Presentation Multilabel URL Classification.pdf**: Deck of slides with a description of the project, including related research, methods, results, conclusions + extra backup slides with more detailed explanations about the methods/results.

### Notebooks
* **supervised_features.ipynb**: This is a replication of the paper "Detecting Malicious URLs Using Lexical Analysis" by Mamun et al., which is where the ISCX2016 dataset (main dataset used throughout this project) comes from. The results here using a Random Forest (RF) classifier is consistent with the results reported in their paper. Furthermore, some additional experiments were performed to see if other classifiers could be useful, and the one that tries to come close is SVM (Support Vector Machine) but is nowhere near the performance of the RF.
* **data_exploration_fwaf.ipynb**: Here we have some initial exploration of the FWAF dataset. This notebook is mostly leftover since this dataset, while used in the final presentation and report, it is not made up of URL samples but rather URL queries, making it a completely different problem to tackle. Nevertheless, our MB (Multinomial Bayes) classifier achieved better results on this dataset compared to the RF classifier used by Mamum et al.
* **data_exploration_iscx.ipynb**: This is the main notebook showing all the results and analysis performed for 3 different datasets used in the final presentation and report.

***Note***: Each Jupyter notebook includes links to download the datasets, which you will need to run the code again.

## Future Work
* There might be a way to 'join' manually created features using the sk-learn classifiers in addition to the TF-IDF method in order to improve performance. This could include a column counting the frequency of a specific symbol or even a custom formula to assign importance to different parts of the URL.
* The URL could be parsed in its individual components (site, top-level domain, path, etc).
* The Char-CNN approach worked very well, so creating a hybrid approach between engineered features and unsupervised learning should be ideal for a practical solution. The only hybrid approach I could find at the time of writing, was a [combination of char-level and word-level CNN](http://arxiv.org/abs/1802.03162), which produces state of the art results.

## Credits
* [ChCNN](https://github.com/rashimo/ChCNN). Base for CNN approach on ISCX2016; code adapted to use different labels.