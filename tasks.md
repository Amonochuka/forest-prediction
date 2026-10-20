# Forest Prediction - Task Split (Fair distribution for 3 developers)

Team: Dixon Osure (#dosure), Amon Ochuka (#aochuka), Phil Aturo (#phaturo)

## Work Split (equal difficulty)

### Dev 1: Dixon Osure (#dosure) - Data Exploration & Feature Engineering
**Focus:** EDA, data understanding, feature creation
**Difficulty:** Medium-High

- [ ] **Task 1.1:** Download/extract data files (train.csv, test.csv, covtype.info) to `data/`
- [ ] **Task 1.2:** Create `notebook/EDA.ipynb` with comprehensive EDA
  - Data shape, types, missing values
  - Target distribution analysis
  - Feature distributions and correlations
  - Identify patterns for feature engineering
- [ ] **Task 1.3:** Implement `scripts/preprocessing_feature_engineering.py`
  - Distance to hydrology: `sqrt((Horizontal_Distance_To_Hydrology)^2 + (Vertical_Distance_To_Hydrology)^2)`
  - Fire points - roadways difference
  - Other composite features based on EDA insights
  - Handle categorical wilderness/soil type features if needed
  - Create reusable preprocessing pipeline
- [ ] **Deliverable:** Clean feature engineering pipeline, EDA insights documented

### Dev 2: Amon Ochuka (#aochuka) - Model Selection & Training
**Focus:** Model building, validation, optimization
**Difficulty:** Medium-High

- [ ] **Task 2.1:** Implement `scripts/model_selection.py`
  - Split train.csv into Train(1)/Test(1) with stratification (<33% for test split)
  - 5-fold stratified cross-validation on Train(1)
  - Grid search over: Gradient Boosting, KNN, Random Forest, SVM, Logistic Regression
  - Handle scaling (StandardScaler) where needed (SVM, KNN, Logistic Regression)
  - Tree-based models (RF, GB) can use unscaled data
- [ ] **Task 2.2:** Model evaluation and selection
  - Ensure train accuracy < 0.98 on train set (0)
  - Compare models using cross-validation scores
  - Select best model
  - Display confusion matrix as DataFrame with True/Predicted labels
  - Plot learning curves for best model
- [ ] **Task 2.3:** Model persistence
  - Save best model as `results/best_model.pkl`
  - Save confusion matrix heatmap as `results/confusion_matrix_heatmap.png`
  - Save learning curve as `results/learning_curve_best_model.png`
  - Document results in README.md
- [ ] **Deliverable:** Best trained model with validation, plots, reproducible pipeline

### Dev 3: Phil Aturo (#phaturo) - Prediction, Documentation & Integration
**Focus:** Final predictions, documentation, project setup
**Difficulty:** Medium-High

- [ ] **Task 3.1:** Project setup and documentation
  - Create `README.md` with project info, team members, approach, results
  - Create `requirements.txt` with all dependencies
  - Ensure proper project structure as specified
- [ ] **Task 3.2:** Implement `scripts/predict.py`
  - Load trained model from `results/best_model.pkl`
  - Preprocess test data using same feature engineering pipeline
  - Make predictions on test set
  - Compute accuracy
  - Save predictions to `results/test_predictions.csv`
- [ ] **Task 3.3:** Final integration & validation
  - Ensure all scripts work together
  - Add final test accuracy to README.md (>0.65 target)
  - Verify submission structure matches requirements
  - Coordinate final push
- [ ] **Deliverable:** Prediction pipeline, complete documentation, final submission

## Collaboration Guidelines
- All work should be committed with clear messages
- Feature engineering changes should be coordinated between Dev1 and Dev2
- Dev2 and Dev3 need to coordinate on model format and prediction interface
- Use feature branches or direct commits as per team preference
- Test integration before final submission

## Timeline
- Day 1-2: EDA and Feature Engineering (Dev1) + Setup (Dev3)
- Day 2-3: Model Selection (Dev2) working with engineered features
- Last Day: Predictions (Dev3) with best model from Dev2
