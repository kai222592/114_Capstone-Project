```mermaid
sequenceDiagram
    
    participant Participant as 研究參與者
    participant System as 線上問卷平台
    participant DB as 問卷數據資料庫
    participant Team as 研究團隊
    Note over Participant, System: 前置條件：研究團隊已發布問卷，參與者已開啟連結

    %% 流程 1: 顯示介面 (已由前置條件完成)
    System-->>Participant: 1. 系統顯示問卷頁面
    
    %% 流程 2: 提交問卷
    Participant->>System: 2. 填寫資料並按下「提交」
    activate System

    %% 替代流程 (Alternate Flow) - 驗證資料
    alt 資料驗證通過 (Happy Path)
        System->>DB: 3. 儲存問卷回覆資料
        activate DB
        DB-->>System: 建立成功
        deactivate DB
        
        System-->>Participant: 4. 顯示「感謝填答」頁面
        System->>Team: 5. (後續) 將新數據納入後台供團隊查看
    else 必填欄位未填 (Alternate Path)
        System-->>Participant: 顯示「您有必填項目尚未完成，請檢查」
    end
    
    %% 在 alt 區塊結束後，才停用系統
    deactivate System

    Note right of System: 後置條件：一份新的問卷數據被成功儲存。
```
