
## TensorFlow 模型再現性
此 repo 示範如何在 TensorFlow DNN 和 CNN 模型實現模型再現性。使得每次執行實驗結果都相同。


| DNN      | CNN                                                  |
|----------|------------------------------------------------------|
| [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/1010code/tensorflow-reproducibility/blob/main/tensorflow-DNN.ipynb) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/1010code/tensorflow-reproducibility/blob/main/tensorflow-CNN.ipynb) |



## 亂數設定
亂數種子是一種產生亂數的一種規律，如果不鎖住亂數種子的數值，則每次執行結果會因為系統時間的變動性而產生不同的結果。在程式語言當中會有許多套件或函式庫會使用到亂數的機制，例如 sklearn 的 train_test_split 切割資料集會亂數的隨機切割資料集，或是神經網路每個神經元的初始值權重...等。

```py
# 設定亂數種子數值
seed_value= 4
# 1. 設定 Python 環境變數亂數種子
import os
os.environ['PYTHONHASHSEED']=str(seed_value)
# 2. 設定 Python 內建亂數生成器亂數種子
import random
random.seed(seed_value)
# 3. 設定 Numpy 亂數種子
import numpy as np
np.random.seed(seed_value)
# 4. 設定 TensorFlow 亂數種子
import tensorflow as tf
tf.random.set_seed(seed_value)
```

