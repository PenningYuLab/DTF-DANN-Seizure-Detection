**--------------------------------------------**
Repository Structure

Code/test_model
|--- Analysis			# Function folder 
	|---cellConcatenate.m	# 轉換資料格式
	|---cellNormImgInfo.m	# 計算資料集的 mean、std、variance，標準化資料集用(Cell)
	|---NormImgInfo.m		# 計算資料集的 mean、std、variance，標準化資料集用(4D-array)
	|---GradientReversalLayer.m	# DANN的梯度反轉層
	|---trainDannOptions.m	# 調整 Model 的  hyperparameters
	|---saveOptions.m		# 儲存結果於資料夾的名稱設定function 
	|---Subjects.mat		# 4隻狗與2位患者資料資訊，用於訓練時讀取資料用
|--- final_				# "testProb.mat" saved direction
|--- testProbability			# test results saved direction 
|--- convert_to_testProb.mlx		# 將所有 subjects 的 test results 轉換成老師需求的"testProb.mat"格式
|--- test_2d_dog.mlx		# 2D-DANN/2D-CNN 的 4隻狗訓練程式
|--- test_1d_dog_channelpair.mlx	# 1D-DANN/1D-CNN 的4隻狗沿頻道對訓練方向的訓練程式
|--- test_1d_dog_frequency.mlx	# 1D-DANN/1D-CNN 的4隻狗沿頻率訓練方向的訓練程式
|--- test_2d_patient.mlx		# 2D-DANN/2D-CNN 的2位患者訓練程式
|--- test_1d_patient_channelpair.mlx	# 1D-DANN/1D-CNN 的2位患者沿頻道對訓練方向的訓練程式
|--- test_1d_patient_frequency.mlx	# 1D-DANN/1D-CNN 的2位患者沿頻率訓練方向的訓練程式

**--------------------------------------------**
(Function 用法以及詳細介紹可以到各個.m檔中查看使用方法以及使用時機)

訓練方式有2種:
(1) Dog 1~ Dog 4
(2) Patient2 and patient 8
又分 "2d", "1d-channels", "1d-frequecy"

Work flow:
1. 可以根據需求選擇性的跑某一個test_*.mlx檔案，其輸出結果會儲存至"testProbability"這個路徑
2. Run  "convert_to_testProb.mlx" 將儲存於"testProbability"的結果轉成最終格式 "testProb.mat"
