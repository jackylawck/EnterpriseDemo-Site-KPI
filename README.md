# 🏗️ Enterprise Demo: 地盤高級管工 KPI 考核系統 (EnterpriseDemo-Site-KPI)

[![System](https://img.shields.io/badge/System-EnterpriseDemo--Site--KPI-0078D4.svg)](https://github.com/jackylawck/EnterpriseDemo-Site-KPI)
[![Compliance](https://img.shields.io/badge/Compliance-ISO%209001%20%7C%20ISO%2042001-green.svg)](./GOVERNANCE_AND_COMPLIANCE.md)
[![Privacy](https://img.shields.io/badge/Privacy-PDPO%20%7C%20Zero--Data--Retention-purple.svg)](./PRIVACY_POLICY.md)
[![Stack](https://img.shields.io/badge/Stack-Streamlit%20%7C%20ReportLab-orange.svg)](#)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)

An ISO-Compliant, Mobile-First & Zero-Data-Retention KPI Performance Assessment Demo for Construction Site Staff.  
專為營造工程業打造之數位化地盤 KPI 績效評核與報告生成系統（概念驗證 Demo 專案）。

🌐 **互動架構與計分模擬器 / Interactive Showcase & Simulator:** [https://jackylawck.github.io/EnterpriseDemo-Site-KPI/](https://jackylawck.github.io/EnterpriseDemo-Site-KPI/)

---

## 🌐 項目簡介 / System Overview

**EnterpriseDemo-Site-KPI** 是一個開源概念驗證（PoC）專案，展示如何以「治理即代碼」（Governance-as-Code）原則將傳統紙本《高級管工關鍵績效指標 (KPI) 考核協議書》轉化為互動式行動端 Web 應用。系統支援地盤現場單手實時動態算分、ISO 7.5 實據單號追溯，並可一鍵匯出符合 ISO 9001 及 ISO/IEC 42001 標準的官方 A4 四方簽署 PDF 報告。

**EnterpriseDemo-Site-KPI** is an open-source Proof of Concept (PoC) that digitizes paper-based Senior Foreman KPI agreements into a mobile-first web application. Built on a **stateless Zero-Data-Retention architecture** with no persistent database, it enables real-time on-site scoring, ISO 9001 Clause 7.5 evidence traceability, and automated generation of audit-ready A4 PDF reports with 4-party sign-off blocks.

---

## ✨ 核心特色與治理亮點 / Key Features & Governance

1. **📱 手機端極致優化 (Mobile-First & Real-Time Scoring)**
   - 採用單欄自適應介面與大尺寸觸控組件，適合地盤現場單手操作。
   - 移除阻塞式表單，輸入原始次數與成本後**即時（Real-time）自動計算比率與 11 項 KPI 得分**。

2. **🔒 零資料保留架構 (Zero-Data-Retention & Stateless)**
   - 系統僅在單次連線會話（Session）的記憶體內進行即時運算與 PDF 渲染，**伺服器端不設任何永久性資料庫**，會話結束即自動清除，從底層杜絕敏感考核個資外洩風險。

3. **🛡️ ISO 9001 & ISO/IEC 42001 合規治理 (ISO Compliance)**
   - **條款 7.5 可追溯性**：內建「ISO 7.5 可追溯核實證據單號／文件編號」欄位（如地盤日誌、安全巡查編號），確保每項扣分均有據可查。
   - **確定性演算法透明度**：全面公開 11 項 KPI 算分規則與閥值邊界，不含黑箱 AI 自動決策，符合 ISO/IEC 42001 可解釋性與人類監督（HITL）要求。

4. **⚖️ 嚴謹的一票否決與 PIP 機制 (Veto, CAPA & PIP Integration)**
   - 支援「重大失聯（≥5次）」、「人為重大事故」或「誠信／考勤虛報」勾選，自動觸發一票否決（強制 F 級），並連動至 ISO 糾正措施程序（CAPA）或 30–60 日績效改善計劃（PIP）。

5. **📄 100% 穩定之 ReportLab PDF 引擎 (Standardized PDF Export)**
   - 採用純 Python `ReportLab` 引擎，避免雲端環境缺少 C 語言底層庫引致的部署報錯。
   - 生成含 4 方審核簽署欄（被考核員工、直屬上司、QMS/HR 審核員、公司代表）的矢量 A4 報告，檔名採標準化格式：`[員工編號]_[員工姓名]_[考核日期].pdf`（例如：`DEMO-001_示範員工_20261119.pdf`）。

---

## 📊 考核四大維度與權重 / KPI Assessment Matrix

| 考核維度 (Dimension) | 權重 (Weight) | 核心評核指標 (11 KPIs) | ISO 7.5 核實憑據重點 (Audit Trail) |
| :--- | :---: | :--- | :--- |
| **一、溝通及匯報**<br>Communication & Reporting | **20%** | 1.1 緊急通訊準時回覆率（8分）<br>1.2 開工／異常／收工匯報完整率（8分）<br>1.3 工作行程及場地交接紀錄（4分） | 通訊紀錄、每日匯報時間戳記、跨場地交接登記表（排除非辦公時間及訊號盲區） |
| **二、工程進度及技術執行**<br>Progress & Technical Execution | **35%** | 2.1 里程碑按時完成率（15分）<br>2.2 首次驗收通過率（12分）<br>2.3 圖紙版本／RFI／技術交底（8分） | 總進度表、驗收批次紀錄單、RFI 正式澄清文件及工前交底簽署表 |
| **三、物料及成本控制**<br>Material & Cost Control | **15%** | 3.1 物料核對準確率（8分）<br>3.2 可避免物料損耗率（7分） | 採購收貨對單表、報廢審定單（排除設計變更及非本施工組導致之正常損耗） |
| **四、安全及團隊管理**<br>Safety & Team Management | **30%** | 4.1 安全巡查整改完成率（12分）<br>4.2 風險評估及事件呈報（10分）<br>4.3 出勤核實及人手調配（8分） | 安全巡查整改通知書、動態風險評估紀錄、工具箱會議及每日出勤核實紀錄 |

---

## 📦 專案檔案結構 / Repository Structure

```text
EnterpriseDemo-Site-KPI/
├── app.py                        # Streamlit 前端網頁應用主程式（即時計分與 ISO 7.5 欄位）
├── generate_pdf.py               # ReportLab PDF 報告生成模組（含文件管制與 4 方簽署欄）
├── index.html                    # GitHub Pages 雙語專案介紹與互動計分模擬器
├── requirements.txt              # Python 套件依賴清單（streamlit, reportlab, pandas）
├── GOVERNANCE_AND_COMPLIANCE.md  # 治理、法規與 ISO 標準適用性評估聲明
├── PRIVACY_POLICY.md             # 個人資料收集聲明（PICS）與零留存政策
├── LICENSE                       # MIT 開源授權條款
└── README.md                     # 專案說明與部署指南

```

---

## 🚀 部署與本地運行 / Deployment & Quick Start

### 1. 本地端運行 (Local Development)

```bash
git clone [https://github.com/jackylawck/EnterpriseDemo-Site-KPI.git](https://github.com/jackylawck/EnterpriseDemo-Site-KPI.git)
cd EnterpriseDemo-Site-KPI
pip install -r requirements.txt
streamlit run app.py

```

### 2. 部署至 Streamlit Community Cloud

1. 將最新代碼 Commit & Push 至 GitHub 儲存庫 `jackylawck/EnterpriseDemo-Site-KPI`。
2. 登入 [Streamlit Community Cloud](https://share.streamlit.io/) 並點擊 **New app**。
3. 選擇 Repository `jackylawck/EnterpriseDemo-Site-KPI`、`main` 分支與主程式 `app.py`。
4. 點擊 **Deploy!** 即可完成線上發布。

---

## ⚠️ 免責聲明 / Disclaimer

本專案為企業管治、ISO 品質管理體系及無狀態架構研究而設之開源概念驗證（Enterprise Demo）。系統內所有示範數據、機構名稱、員工編號及單據代號均為虛擬脫敏佔位符，不涉及任何真實企業機密商業數據。

