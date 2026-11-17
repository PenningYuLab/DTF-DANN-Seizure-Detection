**--------------------------------------------**
Repository Structure

Code/validation_model
|--- Analysis			# Function folder 
	|---cellConcatenate.m	# 轉換資料格式
	|---cellNormImgInfo.m	# 計算資料集的 mean、std、variance，標準化資料集用(Cell)
	|---NormImgInfo.m		# 計算資料集的 mean、std、variance，標準化資料集用(4D-array)
	|---GradientReversalLayer.m	# DANN的梯度反轉層
	|---trainDannOptions.m	# 調整 Model 的  hyperparameters
	|---saveOptions.m		# 儲存結果於資料夾的名稱設定function 
	|---Subjects.mat		# 4隻狗與2位患者資料資訊，用於訓練時讀取資料用
	|---KaggleValidationIdx	# 事先產生的validation data index, 用於訓練時劃分train data 和 validation data 
|--- dog_2d_model.mlx		# 2D-DANN/2D-CNN 的 4隻狗訓練程式
|--- dog_2d_model_hypertune.mlx		# 2D-DANN/2D-CNN 的 4隻狗最佳超參數找尋
|--- patient_2d_model.mlx		# 2D-DANN/2D-CNN 的 2位患者訓練程式
|--- dog_1d_model_channelpair.mlx	# 1D-DANN/1D-CNN 的4隻狗沿頻道對訓練方向的訓練程式
|--- dog_1d_model_frequency.mlx	# 1D-DANN/1D-CNN 的4隻狗沿頻率訓練方向的訓練程式
|--- patient_1d_model_channelpair.mlx	# 1D-DANN/1D-CNN 的4隻狗沿頻道對訓練方向的訓練程式
|--- patient_1d_model_frequency.mlx	# 1D-DANN/1D-CNN 的2位患者沿頻道對訓練方向的訓練程式

**--------------------------------------------**
(Function 用法以及詳細介紹可以到各個.m檔中查看使用方法以及使用時機)

訓練方式有2種:
(1) Dog 1~ Dog 4
(2) Patient2 and patient 8
又分 "2d", "1d-channels", "1d-frequecy"

Work flow:
1. 可以根據需求選擇性的跑某一個檔案，更改code中第一段的變數"specifyIndex", 指定target subject
   			                i.e : 在Dog model 中 specifyIndex=1 即為 target subject = Dog_1
			                
			                調整其中變數"dannOpt"中的選項cnn, 可以選擇跑cnn或是dann
			                 i.e : {cnn=true}, cnn or {cnn=false}, dann
2. 結果會有 training loss、 validation loss、validation AUC 的 curve plot.
