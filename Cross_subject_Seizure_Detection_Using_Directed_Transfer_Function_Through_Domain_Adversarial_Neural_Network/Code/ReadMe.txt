**--------------------------------------------**
Repository Structure

Code/
|--- dtf_evaluation    			# Calculate AIC order and save DTF to "Seizure_detection_DTF_graph"
|--- validation_model			# Training on validation data
|--- test_model				# Training on test data

**--------------------------------------------**
Work flow

1. Use file in "dtf_evaluation"
(1)"DTF_AIC.mlx" to calculate the best order of subjects
(2)"DTFSeizureDetection.mlx" to calculate DTFs and saved to "Seizure_detection_DTF_graph"

2. Use file in "validation_model" to verify the hyperparameter settings

3. Use file in "test_model" to train test model and save results to specific file direction 