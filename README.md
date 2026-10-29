# 人工智慧期中報告：程式操作與逐行說明書 11325034 許竣傑  11325036 蔡典佑

## 題目：基於 TensorFlow Object Detection API 之水果辨識系統

### 一、專題簡介（Project Introduction）

本專題主要使用 Python 程式語言與 TensorFlow Object Detection API，建立一套人工智慧物件偵測系統。透過準備訓練資料、整理影像標籤、轉換資料格式及訓練模型，讓電腦能夠學習影像中的目標物件特徵，並進行後續的物件辨識與定位。

在資料處理階段，本專題使用 `generate_tfrecord.py` 程式，將 CSV 標籤檔案與對應的圖片資料進行整合，轉換成 TensorFlow 可以讀取的 TFRecord 格式，作為後續模型訓練的資料來源。

### 二、開發環境與技術架構（Development Environment）

一、開發環境

1. 作業平台：Google Colab 雲端運算平台。
2. 程式語言：Python 3。
3. 深度學習框架：TensorFlow。
4. 物件偵測工具：TensorFlow Object Detection API。
5. 資料處理程式：`generate_tfrecord.py`。
6. 資料格式：CSV、圖片檔案及 TFRecord。

二、資料夾與檔案說明

1. `images/train/`：存放模型訓練所需的圖片。
2. `images/test/`：存放模型測試所需的圖片。
3. `images/train_labels.csv`：記錄訓練圖片中目標物件的標籤及相關位置資訊。
4. `images/test_labels.csv`：記錄測試圖片中目標物件的標籤及相關位置資訊。
5. `data/train.record`：轉換完成後的訓練資料檔案。
6. `data/test.record`：轉換完成後的測試資料檔案。
7. `generate_tfrecord.py`：負責將圖片及標籤資料轉換成 TFRecord 格式的 Python 程式。

### 三、完整實作步驟說明（Step-by-Step Implementation）

#### 第一階段：開發環境與程式執行準備

##### 步驟 1：確認 Python 執行環境

（1）確認目前使用的 Python 版本，確保程式可以在指定的環境中執行。

（2）確認 TensorFlow 與相關套件是否已經安裝。

（3）確認目前的工作目錄及專案檔案位置，避免程式因為找不到檔案而發生錯誤。

##### 步驟 2：準備 TensorFlow Object Detection API

（1）取得 TensorFlow Models 專案中的 Object Detection API。

（2）確認相關模組已經完成安裝與設定。

（3）檢查 Python 是否能夠正確載入 `object_detection` 模組，確保後續資料轉換程式可以正常執行。

#### 第二階段：訓練資料與標籤準備

##### 步驟 3：整理訓練圖片

（1）將需要用來訓練模型的圖片放入 `images/train/` 資料夾。

（2）確認每張圖片都有對應的標籤資料。

（3）檢查圖片檔案與 CSV 標籤資料中的檔名是否一致，避免程式無法找到對應圖片。

##### 步驟 4：整理測試圖片

（1）將用來測試模型的圖片放入 `images/test/` 資料夾。

（2）確認測試圖片具有對應的標籤資訊。

（3）將測試資料與訓練資料分開管理，以利後續模型訓練及測試。

#### 第三階段：執行 TFRecord 資料轉換

##### 步驟 5：執行訓練資料轉換

（1）使用 `generate_tfrecord.py` 讀取訓練圖片及其標籤資料。

（2）讀取 `images/train_labels.csv`，取得訓練圖片的標籤資訊。

（3）讀取 `images/train/` 中的對應圖片。

（4）將圖片及相關標籤資訊轉換成 TensorFlow 使用的資料格式。

（5）將轉換結果儲存為 `data/train.record`，供模型訓練時使用。

##### 步驟 6：執行測試資料轉換

（1）使用相同的資料轉換程式處理測試資料。

（2）讀取 `images/test_labels.csv`，取得測試圖片的標籤資訊。

（3）讀取 `images/test/` 中的對應圖片。

（4）將測試圖片及標籤資訊轉換成 TFRecord 格式。

（5）將轉換結果儲存為 `data/test.record`，供後續模型評估使用。

#### 第四階段：確認轉換結果

##### 步驟 7：檢查輸出檔案

（1）確認 `data/train.record` 是否成功產生。

（2）確認 `data/test.record` 是否成功產生。

（3）如果檔案沒有產生，應檢查輸入資料路徑、CSV 欄位、圖片檔名及程式執行時的錯誤訊息。

（4）確認資料轉換成功後，再進行後續模型訓練。

### 四、遭遇問題與解決方案（Troubleshooting & Challenges）

#### 問題一：找不到 object_detection 模組

（1）問題描述：

執行 Python 程式時，出現 `ModuleNotFoundError: No module named 'object_detection'` 錯誤，表示 Python 無法找到程式所需的 Object Detection API 模組。

（2）解決方向：

確認 TensorFlow Models 專案是否已下載，並檢查 Object Detection API 是否完成安裝，以及 Python 模組搜尋路徑是否正確設定。

#### 問題二：找不到圖片或 CSV 標籤檔案

（1）問題描述：

當程式指定的檔案路徑與實際儲存位置不一致時，可能會發生檔案不存在的錯誤。

（2）解決方向：

檢查 `images/train/`、`images/test/`、`images/train_labels.csv` 及 `images/test_labels.csv` 等路徑，確認檔案名稱與資料夾位置正確。

#### 問題三：TFRecord 檔案沒有成功產生

（1）問題描述：

當圖片、標籤資料或程式設定有誤時，資料轉換程序可能無法正常完成。

（2）解決方向：

檢查 CSV 標籤內容、圖片與標籤的對應關係、輸出資料夾是否存在，以及程式執行過程中的錯誤訊息，再重新執行轉換程序。

### 五、專題心得（Conclusion & Reflections）

透過本專題，我們可以了解人工智慧物件偵測系統在正式訓練之前，需要先完成環境設定、圖片整理、標籤準備及資料格式轉換等工作。

在實作過程中，除了撰寫及執行 Python 程式之外，也需要理解不同程式模組之間的關係，並確認資料夾路徑與套件安裝是否正確。當程式發生錯誤時，必須根據錯誤訊息逐步檢查問題來源。

透過這次實作，我們能夠更深入了解 TensorFlow Object Detection API 的資料處理流程，並為後續模型訓練、物件辨識與定位功能建立基礎。
