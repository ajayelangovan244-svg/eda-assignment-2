# CampaignPulse: Exploring Customer Response to Bank Term-Deposit Campaigns with EDA and Deep Learning

## Project overview
CampaignPulse explores historical direct-marketing campaign records from a Portuguese banking institution and develops a neural-network classifier to estimate whether a client subscribed to a term deposit.

## Dataset
- Dataset variant: `bank-additional-full.csv`
- Official source: [UCI Machine Learning Repository - Bank Marketing](https://archive.ics.uci.edu/dataset/222/bank%2Bmarketing)
- Standard variant: 41,188 rows, 20 input attributes, and target `y` (21 columns including target)
- License: CC BY 4.0; cite Moro, Rita, and Cortez (2014)

## Notebook
Open `CampaignPulse_Deep_Learning.ipynb` in [Google Colab](https://colab.research.google.com/) and run all cells from top to bottom. The notebook downloads the UCI dataset, performs data-quality checks and EDA, trains and compares two MLP configurations, evaluates the selected model, creates plots and feature importance, then generates a results-filled report.

## Main workflow
1. Dataset acquisition and parsing
2. Data understanding and quality checks
3. Statistical summaries and eight EDA visualizations
4. Seven visualization stages, including an interactive Plotly chart
5. Stratified 70:15:15 training / validation / test split
6. Numerical scaling and categorical one-hot encoding fitted on training data only
7. MLP training, early stopping, class weighting, and validation-based selection
8. Test metrics, confusion matrix, ROC curve, and permutation importance
9. Generate `report/CampaignPulse_Project_Report.docx` and `CampaignPulse_Results_Bundle.zip`

## Important modeling decision
The variable `duration` is explored but excluded from model predictors because call duration is only known after a call. Excluding it reduces post-call target leakage for a prediction intended to be useful before contact. The data are historical and results should not be interpreted as causal evidence.

## Results
Model metrics are intentionally not prefilled in this repository README. Run the notebook and use its actual test results in your report.

## References
- Moro, S., Rita, P., & Cortez, P. (2014). *Bank Marketing* [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5K306
- Moro, S., Cortez, P., & Rita, P. (2014). A data-driven approach to predict the success of bank telemarketing. *Decision Support Systems, 62*, 22-31. https://doi.org/10.1016/j.dss.2014.03.001
- Fry, B. (2008). *Visualizing Data*. O'Reilly Media.
- Keras. (n.d.). *The Sequential model*. https://keras.io/api/models/sequential/
- scikit-learn developers. (n.d.). *Permutation feature importance*. https://scikit-learn.org/stable/modules/permutation_importance.html
