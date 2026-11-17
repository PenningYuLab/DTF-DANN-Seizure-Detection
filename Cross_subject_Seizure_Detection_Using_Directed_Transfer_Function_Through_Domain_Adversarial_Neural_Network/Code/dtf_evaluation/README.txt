**--------------------------------------------**
Repository Structure
feature_extractor/
|--- DTF_example
|    |--- Ch4_03_MVAR_tutorial.mlx       				# Function for concatenating cell arrays
|    |--- Practical Biomedical Signal Analysis Using MATLAB.pdf 	# Methods books
|
|--- MVAR            						# Function for calculating MVAR coefficients
|
|--- NMM							# Generated neural mass model data(400Hz), for DTF simulation 
|--- DTF_AIC.mlx                           				# Calculating AIC order of subjects
|--- DTF_seizure_detection.mlx                           			# 1. Calculating MVAR coefficients 
|					  		    2. Calculating DTFs 
|					   		    3. Saved to specified direction
|
|--- plotDataDist_different_axis.mlx				# Plot DTFs distribution of each subject
|--- fileReadSeizureDetection.m                           			# Function for read Kaggle seizure detection dataset 
|--- subjects.mat 						# Subject information 

**--------------------------------------------**
Workflow: 

1. Run "DTF_AIC.mlx" 計算subject data 的 best MVAR order.
2. Run "DTF_seizure_detection.mlx" 使用所選的best MVAR order計算segment 的 DTFs並儲存至路徑"D:\Seizure_detection_DTF_graph"，此為模型的inputs