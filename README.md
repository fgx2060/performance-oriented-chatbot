# ⚡ Performance-Oriented Chatbot (以效能為導向的客製化聊天機器人)

## 📖 專案簡介
本專案專注於開發一個高效能的客製化聊天機器人，結合 **LangChain、RAG、LoRA/QLoRA 微調** 與 **向量資料庫檢索**，解決 LLM 在醫療（特別是牙科產業）應用上的限制：  
- 記憶更新不足  
- 無法引用即時知識  
- 回答不精確  

透過效能導向的設計，本系統能在 **Google Colab（CPU 環境）** 上運行，實現資源受限情況下的高效聊天機器人。  

---

## ⚙️ 功能特色
- **語意檢索 + 生成 (RAG)**：彌補 LLM 無法自行更新的缺陷。  
- **LoRA / QLoRA 微調**：降低記憶體消耗，提升運行效能。  
- **向量檢索 (FAISS / ChromaDB)**：快速找到最相關的醫療知識。  
- **Chunking 技術**：分段處理避免長度限制，提升檢索準確度。  
- **BLEU / ROUGE 評估**：量化回覆品質。  
- **終端機互動介面**：支援 CLI 問答互動。  
- **AnythingLLM + Ollama 整合**：提供多人共享的 RAG 聊天機器人架構。  

---

## 🛠️ 技術架構
使用者問題 → 向量化 (OpenAIEmbeddings) → ChromaDB / FAISS 檢索 → 篩選相關段落 → LangChain Prompt → LLM (TinyLlama-1.1B-Chat) → 生成答案


- **模型**：TinyLlama-1.1B-Chat + LoRA/QLoRA  
- **框架**：LangChain、PEFT (Parameter-Efficient Fine-Tuning)  
- **資料庫**：ChromaDB / FAISS  
- **平台**：Google Colab (CPU)、Jupyter Notebook (`main.ipynb`)  

---

## 🚀 使用方式
1. 安裝依賴：
   ```bash
   !pip install sentence-transformers faiss-cpu transformers peft bitsandbytes accelerate langchain
   ```
   
2. 執行 main.ipynb，完成以下流程：

    - 資料前處理（Chunking & Tokenization）
    - 建立向量資料庫 (FAISS / ChromaDB)
    - LoRA / QLoRA 微調 TinyLlama
    - 問答測試與效能評估
      
3. 啟動互動式 CLI 模式
   
## 成果報告書 
 - 人工智慧實務實作-以效能為導向的客製化聊天機.pdf

## 參考文獻
 - TSP_CMC_54360.pdf
