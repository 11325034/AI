# 人工智慧期中報告：Google Colab 部署 Python 專案

## 一、組員
- 組員一：黃嘉彬
- 班級／組別：傳播3A

## 二、參考文章
- 文章名稱：Google Colab 部署自己的机器学习项目
- 文章網址：
  https://blog.csdn.net/weixin_37589575/article/details/94591580

## 三、實作目的
依照指定文章，將 Python 專案資料夾上傳至 Google Drive，
使用 Google Colab 掛載雲端硬碟，
切換至專案所在位置並執行 main.py。

本次測試內容為匯入 PyTorch 並列印成功訊息，
沒有進行模型訓練。

## 四、使用環境
- Google Colab
- Google Drive
- Python 3
- PyTorch
- 硬體加速器：（填入實際設定，例如 CPU 或 GPU）

## 五、檔案結構
```text
AI-Colab-Report/
├── README.md
├── Colab_Project_Report.ipynb
└── test/
    └── main.py
```

## 六、main.py 內容
```python
import torch
print('Run successfully!')
```

## 七、執行方式

### 1. 準備專案
將本專案中的 test 資料夾上傳到 Google Drive
「我的雲端硬碟」根目錄。

預期位置：
我的雲端硬碟/test/main.py

### 2. 開啟筆記本
下載 Colab_Project_Report.ipynb，
在 Google Colab 中使用「檔案 → 上傳筆記本」開啟。

### 3. 設定環境
依照課堂與原文要求設定執行環境，
再依序執行筆記本中的儲存格。

### 4. 掛載 Google Drive
```python
from google.colab import drive
drive.mount('/content/drive')
```

### 5. 查看目錄
```python
!ls
```

### 6. 切換至專案資料夾
```python
import os
os.chdir('/content/drive/MyDrive/test')
print("目前資料夾：", os.getcwd())
```

### 7. 確認程式檔案
```python
!ls
```

應看到 main.py。

### 8. 執行程式
```python
!python main.py
```

## 八、實際執行結果
（完成後填寫實際觀察結果。）

若測試成功，輸出為：
```text
Run successfully!
```

此結果表示程式完成 PyTorch 匯入與列印，
不代表曾經訓練模型，也不代表已驗證 GPU 運算。

## 九、與原文的差異
- 原文使用舊版 Colab 介面，本次依目前介面操作。
- Google Drive 授權依目前介面完成。
- 本次使用的專案路徑為：
  /content/drive/MyDrive/test

## 十、遇到的問題與解決方式
（只保留實際遇到的問題。）

例如：
- 找不到 Python 檔案：
  檢查檔案是否上傳、檔名是否正確、
  目前工作目錄是否為 test。
<img width="1905" height="898" alt="image" src="https://github.com/user-attachments/assets/ba7d4efa-eaa3-4c4d-8c8d-95b0cbab824d" />
