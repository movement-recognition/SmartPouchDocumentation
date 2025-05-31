# Model Evaluation

This document describes the model evaluation process and metrics for SmartPouch_v2.

## Evaluation Metrics

### 1. Classification Metrics
```python
def calculate_metrics(y_true, y_pred):
    metrics = {
        'accuracy': accuracy_score(y_true, y_pred),
        'precision': precision_score(y_true, y_pred, average='weighted'),
        'recall': recall_score(y_true, y_pred, average='weighted'),
        'f1': f1_score(y_true, y_pred, average='weighted')
    }
    return metrics
```

### 2. Regression Metrics
```python
def calculate_regression_metrics(y_true, y_pred):
    metrics = {
        'mse': mean_squared_error(y_true, y_pred),
        'rmse': np.sqrt(mean_squared_error(y_true, y_pred)),
        'mae': mean_absolute_error(y_true, y_pred),
        'r2': r2_score(y_true, y_pred)
    }
    return metrics
```

## Cross-Validation

### 1. K-Fold Cross-Validation
```python
def perform_cross_validation(model, X, y, k=5):
    kf = KFold(n_splits=k, shuffle=True, random_state=42)
    scores = []
    
    for train_idx, val_idx in kf.split(X):
        X_train, X_val = X[train_idx], X[val_idx]
        y_train, y_val = y[train_idx], y[val_idx]
        
        model.fit(X_train, y_train)
        score = model.score(X_val, y_val)
        scores.append(score)
    
    return np.mean(scores), np.std(scores)
```

### 2. Stratified Cross-Validation
```python
def perform_stratified_cv(model, X, y, k=5):
    skf = StratifiedKFold(n_splits=k, shuffle=True, random_state=42)
    scores = []
    
    for train_idx, val_idx in skf.split(X, y):
        X_train, X_val = X[train_idx], X[val_idx]
        y_train, y_val = y[train_idx], y[val_idx]
        
        model.fit(X_train, y_train)
        score = model.score(X_val, y_val)
        scores.append(score)
    
    return np.mean(scores), np.std(scores)
```

## Model Comparison

### 1. Statistical Tests
```python
def compare_models(model1_scores, model2_scores):
    t_stat, p_value = stats.ttest_rel(model1_scores, model2_scores)
    return {
        't_statistic': t_stat,
        'p_value': p_value,
        'significant': p_value < 0.05
    }
```

### 2. Performance Comparison
```python
def compare_performance(models, X_test, y_test):
    results = {}
    for name, model in models.items():
        y_pred = model.predict(X_test)
        results[name] = calculate_metrics(y_test, y_pred)
    return results
```

## Error Analysis

### 1. Confusion Matrix
```python
def analyze_errors(y_true, y_pred):
    cm = confusion_matrix(y_true, y_pred)
    plt.figure(figsize=(10, 8))
    sns.heatmap(cm, annot=True, fmt='d')
    plt.title('Confusion Matrix')
    plt.ylabel('True Label')
    plt.xlabel('Predicted Label')
    plt.show()
```

### 2. Error Patterns
- Misclassification analysis
- Feature importance
- Error distribution
- Edge cases

## Model Interpretability

### 1. Feature Importance
```python
def plot_feature_importance(model, feature_names):
    importance = model.feature_importances_
    indices = np.argsort(importance)
    
    plt.figure(figsize=(10, 6))
    plt.title('Feature Importance')
    plt.barh(range(len(indices)), importance[indices])
    plt.yticks(range(len(indices)), [feature_names[i] for i in indices])
    plt.show()
```

### 2. SHAP Values
```python
def explain_predictions(model, X):
    explainer = shap.TreeExplainer(model)
    shap_values = explainer.shap_values(X)
    
    plt.figure(figsize=(10, 6))
    shap.summary_plot(shap_values, X)
    plt.show()
```

## Evaluation Reports

### 1. Performance Summary
- Overall metrics
- Class-wise performance
- Error analysis
- Recommendations

### 2. Visualization
- ROC curves
- Precision-Recall curves
- Learning curves
- Residual plots

## Best Practices

1. Use multiple evaluation metrics
2. Perform cross-validation
3. Analyze error patterns
4. Document findings
5. Share insights

## Related Documents

- [Model Training](model_training.md)
- [Deployment](deployment.md)
- [One Record Implementation](one_record_implementation.md)

## Next Steps

1. Implement evaluation pipeline
2. Set up automated testing
3. Create evaluation reports
4. Document findings

---

*Last updated: March 10, 2024* 