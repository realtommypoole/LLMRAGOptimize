# LLMRAGO + LoRASFT
## LLM RAG Optimization with Low-Rank Adaptation & Supervised Fine Tuning

**Purpose:** This project fine tunes nano LLMs with limited QA sets of sizes (8, 32, 64, 256) in order to see how varying sizes of QA fine-tuning data impacts optimization via SFT. 

**Project Setup & Dependencies:** This project requires API keys for HuggingFace and Anthropic, and will cost around $5 to run (as of Spring 2026). Additionally, this project was run in Colab Pro on G4 GPU, with expanded memory. Subscriptions may be required to mirror in that environment. 

**Dataset:** As the knowledge base for distillation, this project used a PDF version of the textbook *Artificial Intelligence: A Modern Approach (3rd ed.)* by Stuart Russell & Peter Norvig. Any PDF could be used as long as it has enough context to generate 300 QA pairs. 

**Project Outline:**

<img width="1720" height="2440" alt="project_outline_color" src="https://github.com/user-attachments/assets/151e46ec-b4b8-4ee8-80df-2494543f2440" />

**Results & Key Findings:**


**Citation:**
Russell, S. & Norvig, P. (2010). Artificial Intelligence: A Modern Approach (3rd ed.)
Evaluation metrics aligned to Microsoft Azure AI Foundry standards.
