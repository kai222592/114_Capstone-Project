# 第10組

## 功能性需求與非功能性需求
### 功能性需求
---
#### 1. 問卷設計與發放系統 (Questionnaire Design & Distribution System)

 * 說明： 必須建立一個能夠蒐集所有研究變數的結構化問卷。此問卷需要能夠線上填寫與回收，以利於對台灣大學生進行大規模資料蒐集。
 * 具體功能：問卷題目需完整涵蓋「感知有用性」、「感知易用性」、「資訊品質」、「系統品質」、「服務品質」、「持續使用意圖」以及受訪者背景資料（如年級、主修科系、Gemini使用頻率等）。
   系統需提供一個獨立的網頁連結，讓受訪者能方便地透過網路填答。後台需能自動彙整所有回收的問卷數據，並能將其匯出為常見的數據格式（如 .csv 或 .xlsx）以利後續分析。

#### 2. 數據統計與分析功能 (Data Statistical & Analysis Function)

 * 說明： 這是研究的核心，指處理原始數據並驗證研究假設的具體分析流程。
 * 具體功能：必須能夠執行「信度與效度分析」，以確保問卷品質的穩定與準確。必須能夠進行「描述性統計」，以呈現樣本的基本樣貌與特徵。
   必須能夠執行核心的統計模型分析，用以檢驗各個變數之間的因果關係，並驗證研究假設是否成立。

#### 3. 研究結果呈現與報告生成 (Result Presentation & Report Generation)

 * 說明： 研究的最終產出，需將複雜的數據分析結果轉化為易於理解的資訊。
 * 具體功能：能夠將數據分析結果視覺化，例如繪製包含路徑係數與顯著性的研究模型圖。能夠生成清晰的統計表格，如各變數的平均數、標準差、相關係數矩陣等。
   最終產出的報告必須明確條列研究假設的驗證結果（支持或不支持），並根據結果撰寫結論與管理意涵。

---

### 非功能性需求

#### 1. 研究信度與效度 (Reliability & Validity)

 * 信度 (Reliability)： 問卷量表的內部一致性信度必須達到學術上可接受的標準（通常要求 > 0.7）。
 * 效度 (Validity)： 問卷題目必須能準確地測量到我們想要測量的概念（如「感知有用性」），數據分析需證明模型的配適度良好，確保研究結論不是由隨機誤差所造成。

#### 2. 資料隱私與倫理遵循 (Data Privacy & Ethical Compliance)

 * 匿名性： 必須確保問卷填答過程完全匿名，研究團隊無法透過任何方式追溯到特定填答者的個人身份。
 * 知情同意： 在問卷開頭必須清楚說明研究目的、資料用途，並明確告知填答者其數據僅供學術研究使用，以取得他們的知情同意。
 * 資料安全： 蒐集到的原始數據必須妥善保管，防止外洩。

#### 3. 成果可理解性與應用性 (Readability & Applicability)

 * 可理解性： 最終報告的撰寫應避免過度使用艱澀的術語。對於必要的專有名詞，應提供淺顯的解釋。圖表應清晰易讀，能直觀地傳達核心發現。
 * 應用性： 報告中提出的「實務建議」必須具體、中肯且具備可操作性，真正能為AI輔助學習的實踐提供有價值的參考。
---
## 功能分解圖
```mermaid
graph TD
    A[探討Gemini輔助學習之持續使用意圖,以台灣的學生為例]

    A --> B1[1. 使用者管理]
    B1 --> B11[1.1 使用者註冊]
    B1 --> B12[1.2 使用者登入]
    B1 --> B13[1.3 權限控管]

    A --> B2[2. 任務管理]
    B2 --> B21[2.1 任務建立]
    B2 --> B22[2.2 任務分配]
    B2 --> B23[2.3 任務進度更新]
    B2 --> B24[2.4 任務查詢與排序]

    A --> B3[3. 小組進度追蹤]
    B3 --> B31[3.1 進度儀表板]
    B3 --> B32[3.2 任務統計報表]
    B3 --> B33[3.3 任務提醒通知]

    A --> B4[4. 通訊與協作功能]
    B4 --> B41[4.1 任務留言板]
    B4 --> B42[4.2 系統公告]

    A --> B5[5. 系統管理與維護]
    B5 --> B51[5.1 小組與帳號管理]
    B5 --> B52[5.2 系統安全與備份]
    B5 --> B53[5.3 日誌與錯誤追蹤]
    %% ---- 節點配色 ----
    style A fill:#d7b6f6,stroke:#a678d3,stroke-width:2px,color:#000,font-weight:bold
    style B1 fill:#fff3c4,stroke:#c2a83e,stroke-width:1px
    style B2 fill:#fff3c4,stroke:#c2a83e,stroke-width:1px
    style B3 fill:#fff3c4,stroke:#c2a83e,stroke-width:1px
    style B4 fill:#fff3c4,stroke:#c2a83e,stroke-width:1px
    style B5 fill:#fff3c4,stroke:#c2a83e,stroke-width:1px

    style B11 fill:#ffffff,stroke:#bcbcbc
    style B12 fill:#ffffff,stroke:#bcbcbc
    style B13 fill:#ffffff,stroke:#bcbcbc

    style B21 fill:#ffffff,stroke:#bcbcbc
    style B22 fill:#ffffff,stroke:#bcbcbc
    style B23 fill:#ffffff,stroke:#bcbcbc
    style B24 fill:#ffffff,stroke:#bcbcbc

    style B31 fill:#ffffff,stroke:#bcbcbc
    style B32 fill:#ffffff,stroke:#bcbcbc
    style B33 fill:#ffffff,stroke:#bcbcbc

    style B41 fill:#ffffff,stroke:#bcbcbc
    style B42 fill:#ffffff,stroke:#bcbcbc

    style B51 fill:#ffffff,stroke:#bcbcbc
    style B52 fill:#ffffff,stroke:#bcbcbc
    style B53 fill:#ffffff,stroke:#bcbcbc
```
---


---
## 使用案例圖



## 使用案例說明


