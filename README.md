tensorflow圖形檢測_使用Google Colab使用Tensorflow進行自定義對象檢測
--------------------------------------------------------------------
跨領域-人工智慧期中報告 11124111 王志節 11124114 黃安德

本文是關於如何使用 TensorFlow 物件偵測 API 建立自訂物件偵測器的詳細步驟，從安裝環境、資料收集、標註資料、產生 TFRecords 到訓練模型和測試物件偵測器，我們將使用Tensorflow物件來偵測API建立自訂物件偵測器，我將選擇檢測蘋果果實，但是您可以選擇要偵測自己的自訂物件的任何影像。

## 摘要中的主要步驟：
1. 安裝環境
2. 數據收集
3. 數據標註
4. 產生用於訓練的 TFRecord
5. 訓練配置
6. 模型訓練
7. 導出推論圖
8. 物體探測測試

設定Google Colab環境
------------------------------
  Python ```3.6```或```更高版本```。
  Ubuntu ```18.04/google colab```
  Tensorflow/Tensorflow-gpu
複製TensorFlow模型倉庫運行以下程式碼，克隆```TensorFlow```模型庫並進入```research```目錄：
```
git clone https://github.com/tensorflow/models.git
```
建構環境
-------------
Protobuf編譯: Tensorflow物件偵測API使用Protobufs配置模型和訓練參數。在使用該框架之前，必須先編譯Protobuf函式庫。這應該透過從tensorflow / models / research /目錄執行以下命令來完成：

```
#From TFmodels/research/
```
將庫加入到PYTHONPATH在google colab運行時，應將TFmodels / research /和slim目錄附加到PYTHONPATH。
Gathering data
-------------------------
2.1 開啟您的google chrome瀏覽器並安裝一個名為Download All Images的擴充功能。

2.2 現在在Google圖片中搜尋所需的圖片選擇，在我的例子中是「 Apple」。現在，按一下「下載所有圖像」擴充功能按鈕，該按鈕將位於瀏覽器的右上角。您將獲得一個包含圖像的zip檔。然後將其提取。

























