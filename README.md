# LLMRAGO + LoRASFT
## LLM RAG Optimization with Low-Rank Adaptation & Supervised Fine Tuning

**Purpose:** This project fine tunes nano LLMs with limited QA sets of sizes (8, 32, 64, 256) in order to see how varying sizes of QA fine-tuning data impacts optimization via SFT. 

**Project Setup & Dependencies:** This project requires API keys for HuggingFace and Anthropic, and will cost around $5 in Anthropic tokens to run as of April 2026. Additionally, this project was run in Colab Pro on G4 GPU, with expanded memory. Subscriptions may be required to mirror in that environment. 

**Dataset:** As the knowledge base for distillation, this project used a PDF version of the textbook *Artificial Intelligence: A Modern Approach (3rd ed.)* by Stuart Russell & Peter Norvig. Any PDF could be used as long as it has enough context to generate 300 QA pairs. 

**Project Outline:**

<img width="1720" height="2440" alt="project_outline_color" src="https://github.com/user-attachments/assets/151e46ec-b4b8-4ee8-80df-2494543f2440" />

**Results & Key Findings:**
<img width="321" height="300" alt="image" src="https://github.com/user-attachments/assets/6f313713-e69e-4549-a107-7cde1ac22390" />

The dataset size effect did not follow the hypothesized monotonic pattern. Averaging across architectures, the 32-pair split produced the highest mean overall score (3.353), outperforming the 64-pair (3.253), 256-pair (3.258), and 8-pair (3.294) splits. This inverted-U pattern, as seen in Figure 4 below, suggests an optimal range near 32 pairs for this corpus and architecture class, with larger datasets providing diminishing or negative returns.

The results appear to disprove the hypothesis of monotonic dataset scaling in this context. The expectation was that larger QA datasets for fine-tuning would result in better performance, but that was not true in all cases. In fact, the results pointed to a potential sweet spot in the middle with an inverted curve, where more questions caused underperformance pointing to a potential training issue or overfitting. Furthermore, given the synthetic dataset, as well as the limited QA sizes and test set, the confidence interval calculation showed significant overlap in results weakening any claims around the final outcome of this study.

Despite the absence of strong monotonic scaling, fine-tuned nano models remain a practically viable alternative to frontier deployments in many contexts. Nemotron variants consistently outperformed their base model across smaller dataset sizes, and even the weakest fine-tuned nano (llamaNano_ft_64q, overall 3.067) achieved scores within approximately 26% of Claude's frontier benchmark (4.125) — while the best nano (nemotron_ft_32q, 3.567) closed that gap to roughly 14%. For applications where response latency, inference cost, or data privacy constraints make API-based frontier models impractical, a fine-tuned nano running on local hardware may offer an acceptable tradeoff. The remaining gap was most pronounced on completeness, suggesting nano models are best suited to use cases that prioritize grounded, relevant responses over exhaustive coverage of complex questions.


**Citation:**
Russell, S. & Norvig, P. (2010). Artificial Intelligence: A Modern Approach (3rd ed.)
Evaluation metrics aligned to Microsoft Azure AI Foundry standards.
