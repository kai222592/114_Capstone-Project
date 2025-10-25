## 系統環境圖 (DFD)
### 一、System Context Diagram
![系統環境圖](系統環境圖.png)

---
### 二、DFD Level 0
```mermaid
flowchart LR
    %% DFD Level 1：探討Gemini輔助學習之持續使用意圖
    %% 佈局：左外部→核心流程→右外部；資料庫置中靠下

    %% 外部實體 (External Entities)
    E1["台灣的大學生<br/>（研究對象）"]
    E2["研究團隊<br/>（專題執行者）"]
    E3["教育工作者 / AI開發者<br/>（研究成果受眾）"]

    %% 核心處理程序 (Processes)
    subgraph 核心研究流程
        direction TB
        P1["P1: 理論模型與問卷建置<br/>（TAM & AI變數整合）"]
        P2["P2: 問卷發放與資料蒐集<br/>（學生填答、數據匯入）"]
        P3["P3: 數據分析與模型驗證<br/>（統計分析、SEM）"]
        P4["P4: 研究成果撰寫與建議<br/>（報告產出、建議形成）"]
    end

    %% 資料儲存 (Data Stores) - 根據專題實際資料儲存點
    subgraph 資料儲存
        direction LR
        D1["D1: 原始問卷數據<br/>（線上平台匯出）"]
        D2["D2: 分析結果數據<br/>（SPSS/AMOS中間結果）"]
        D3["D3: 理論模型與假說<br/>（研究設計文件）"]
    end

    %% 外部互動 (External Entities <-> Processes)
    E2 -- "研究目標、理論基礎" --> P1
    P1 -- "設計完成問卷" --> P2
    P2 -- "線上問卷連結" --> E1
    E1 -- "已填答問卷數據" --> P2
    
    P4 -- "研究成果報告" --> E3
    P4 -- "最終數據分析結果" --> E2

    %% 流程 <-> 資料庫 (Processes <-> Data Stores)
    P1 <--> D3
    P2 --> D1
    D1 --> P3
    P3 --> D2
    D2 --> P4
    P4 --> D3 
    
    %% 內部處理流程 (Process to Process)
    P1 --> P2
    P2 --> P3
    P3 --> P4
```
---
