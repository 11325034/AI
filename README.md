# 115 人工智慧期中報告:Google Colab 使用 TensorFlow 進行自訂物件偵測 (Custom Object Detection)



---

## 📌 專案簡介

在電腦視覺領域中，物件偵測（Object Detection）不僅需要識別影像中的物體類別，還需要標註出其具體的位置（Bounding Box）。本範例透過 Google Colab 提供的免費 GPU 算力，示範從環境配置、資料集準備、模型訓練到最終推論驗證的全流程。

- **組員**：11325034 許竣傑  11325036 蔡典佑
- **指定文章主題**：tensorflow圖形檢測_使用Google Colab使用Tensorflow進行自定義對象檢測

---

## 🛠️ 環境與工具

- **開發平台**：[Google Colaboratory](https://colab.research.google.com/) (GPU 執行階段)
- **程式語言**：Python 3.x
- **核心框架**：TensorFlow 2.x / TensorFlow Object Detection API
- **輔助工具**：Google Drive (用於儲存資料集與模型權重)

---

## 🚀 執行流程與步驟

本專案 `TensorFlow_Object_Detection_Colab.ipynb` 包含以下關鍵步驟：

### 1. 環境設定與 GPU 確認
* 切換 Colab 執行階段為 GPU (`T4 GPU`)。
* 檢查 GPU 狀態與 TensorFlow 版本。

### 2. 安裝 TensorFlow Object Detection API
* 下載 TensorFlow Models 官方 GitHub 儲存庫。
* 安裝 Protobuf 並編譯相關 Protobuf 檔案。
* 設定環境變數並完成 API 安裝作業。

### 3. 資料集準備與標註 (Dataset Preparation)
* 載入自訂圖片資料集與標註檔 (`.xml` 或 `.json`)。
* 將標註資料轉為 TensorFlow 專用的 `TFRecord` 格式。
* 建立類別映射檔 (`label_map.pbtxt`)。

### 4. 模型配置與訓練 (Model Training)
* 下載預訓練模型權重 (例如: SSD MobileNet V2 FPN)。
* 設定訓練配置文件 (`pipeline.config`) 包含學習率、Batch Size 與路徑設定。
* 執行模型訓練作業。

### 5. 模型匯出與推論測試 (Inference)
* 匯出訓練完成的凍結模型 (SavedModel / Checkpoint)。
* 載入測試圖片並進行物件偵測測試。
* 繪製標註框 (Bounding Boxes) 與信心分數 (Confidence Scores)。

---

## 📁 檔案結構

```
├── README.md                              # 本說明文件
└── TensorFlow_Object_Detection_Colab.ipynb  # Colab 主程式碼檔
```

---

## 📝 執行說明

1. 點擊 GitHub 中的 `.ipynb` 檔案，可選擇開啟於 Google Colab 中執行。
2. 執行前請確認已於 Colab 頂端選單選擇 `執行階段` -> `變更執行階段類型` -> `Hardware accelerator: GPU`。
3. 依序執行各個 Code Cell 即可完成模型構建與驗證。
