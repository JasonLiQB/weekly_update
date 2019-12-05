# RandomForestClassifier:
Code:
```
model = AutoMLClassifier(
    scoring="roc_auc",
    estimators = [RandomForestClassifierModel()],
    resampling_strategy=3, 
    output_dir="~/ray_results",
    n_jobs=1,
)

model.fit(X_, y_raw_, total_time=60, max_time_per_task=60)
```
**successfully** finish the ray tune optimization
```
model.best_config_:
>>>
Configuration:
  model_choice, Value: 'random_forest'
  preprocessor:imputation_strategy, Value: 'most_frequent'
  random_forest:bootstrap, Value: False
  random_forest:class_weight, Value: 'balanced_subsample'
  random_forest:criterion, Value: 'gini'
  random_forest:max_depth, Constant: 'None'
  random_forest:max_features, Value: 0.128405044796278
  random_forest:max_leaf_nodes, Constant: 'None'
  random_forest:min_impurity_decrease, Constant: 0.0
  random_forest:min_samples_leaf, Value: 10
  random_forest:min_samples_split, Value: 18
  random_forest:min_weight_fraction_leaf, Constant: 0.0
  selector:max_n_features, Constant: 500
  selector:sampling_ratio, Constant: 'None'
```

# Overall pipeline test:

