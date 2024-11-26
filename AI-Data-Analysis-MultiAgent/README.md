# AI-Driven Research Assistant

![System Architecture](Architecture.png)

# AI 數據分析多智能體系統

## 概述

這是一個進階的 AI 驅動研究助理系統，運用多個專門的智能體來協助數據分析、視覺化和報告生成等任務。該系統採用 LangChain、OpenAI 的 GPT 模型和 LangGraph 來處理複雜的研究流程，整合多樣化的 AI 架構以實現最佳性能。

## 主要特點

- 假設生成與驗證
- 數據處理與分析
- 視覺化圖表生成
- 網路搜尋與信息檢索
- 程式碼生成與執行
- 報告撰寫
- 品質審查與修訂
- **多樣化架構整合**：
  - 監督智能體負責監控分析流程
  - 思維鏈推理用於解決複雜問題
  - 評論智能體負責品質保證和錯誤檢查
- **創新筆記智能體**：
  - 持續記錄專案當前狀態
  - 提供更有效率的歷史信息傳遞方式
  - 提升系統在不同分析階段的上下文維護能力
- **自適應工作流程**：根據數據和任務需求動態調整分析方法

## 系統特色

本系統的獨特之處在於整合了專門的筆記智能體，有別於傳統的數據分析流程。通過維護簡潔而全面的專案狀態記錄，系統可以：

1. 減少計算開銷
2. 改善不同分析階段的上下文保留
3. 實現更連貫一致的分析結果

## 系統要求

- Python 3.10 或更高版本
- Jupyter Notebook 環境

## 安裝步驟

1. 克隆儲存庫：
```bash
git clone https://github.com/starpig1129/ai-data-analysis-MulitAgent.git
```
2. 創建並啟動 Conda 虛擬環境：
```bash
conda create -n data_assistant python=3.10
conda activate data_assistant
```
3. 安裝相依套件：
```bash
pip install -r requirements.txt
```
4. 設定環境變數：
**將 `.env Example` 重新命名為 `.env` 並填入所有數值**
```sh
# 數據存儲路徑（必填）
DATA_STORAGE_PATH =./data_storage/

# Anaconda 安裝路徑（必填）
CONDA_PATH = /home/user/anaconda3

# Conda 環境名稱（必填）
CONDA_ENV = envname

# ChromeDriver 執行檔路徑（必填）
CHROMEDRIVER_PATH =./chromedriver-linux64/chromedriver

# Firecrawl API 金鑰（選填）
# 注意：如果缺少此金鑰，查詢功能可能會受限
FIRECRAWL_API_KEY = XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

# OpenAI API 金鑰（必填）
# 警告：此金鑰為必要項目，程式無法在缺少此金鑰的情況下運行
OPENAI_API_KEY = XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

# LangChain API 金鑰（選填）
# 用於監控處理過程
LANGCHAIN_API_KEY = XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
```

## 使用方法

1. 啟動 Jupyter Notebook

2. 在 data_storage 中放入您的數據檔案 YourDataName.csv

3. 打開 `main.ipynb` 檔案

4. 運行所有單元格以初始化系統並創建工作流程

5. 在最後一個單元格中，您可以通過修改 `userInput` 變數來自訂研究任務

6. 運行最後幾個單元格以執行研究流程並查看結果

## 主要組件

- `hypothesis_agent`：生成研究假設
- `process_agent`：監督整個研究流程
- `visualization_agent`：創建數據視覺化
- `code_agent`：編寫數據分析程式碼
- `searcher_agent`：進行文獻和網路搜尋
- `report_agent`：撰寫研究報告
- `quality_review_agent`：執行品質審查
- `note_agent`：記錄研究流程

## 工作流程

系統使用 LangGraph 創建一個狀態圖來管理整個研究流程。工作流程包括以下步驟：

1. 假設生成
2. 人工選擇（繼續或重新生成假設）
3. 處理（包括數據分析、視覺化、搜尋和報告撰寫）
4. 品質審查
5. 根據需要進行修訂

## 自訂設定

您可以通過修改 `main.ipynb` 中的智能體創建和工作流程定義來自訂系統行為。

## 注意事項

- 確保您有足夠的 OpenAI API 額度，因為系統會進行多次 API 呼叫
- 根據任務的複雜度，系統可能需要一些時間來完成整個研究流程
- **警告**：智能體系統可能會修改正在分析的數據。強烈建議在使用本系統前備份您的數據

## 當前問題和解決方案
1. OpenAI 內部伺服器錯誤（錯誤代碼：500）
2. 筆記智能體效率改進
3. 整體運行時間優化
4. 優化器需要改進

## 貢獻

歡迎提交 Pull Request。對於重大變更，請先開啟 Issue 討論您想要改變的內容。

## 授權

本專案採用 MIT 授權 - 詳見 [LICENSE](LICENSE) 文件。