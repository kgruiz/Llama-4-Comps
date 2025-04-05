## 🔹 Benchmark Table

| **Benchmark**                               | **Gemini 2.5 Pro** _(Experimental 03-25)_ | **OpenAI o3-mini** _(High)_ | **OpenAI GPT-4.5** | **Claude 3.7 Sonnet** _(64k Extended Thinking)_ | **Grok 3 Beta** _(Extended Thinking)_ | **DeepSeek R1** |
| ------------------------------------------- | ----------------------------------------- | --------------------------- | ------------------ | ----------------------------------------------- | ------------------------------------- | --------------- |
| **Reasoning & knowledge**                   |                                           |                             |                    |                                                 |                                       |                 |
| Humanity's Last Exam _(no tools)_           | 18.8%                                     | 14.0%\*                     | 6.4%               | 8.9%                                            | —                                     | 8.6%\*          |
| **Science**                                 |                                           |                             |                    |                                                 |                                       |                 |
| GPQA diamond _(single attempt, pass@1)_     | 84.0%                                     | 79.7%                       | 71.4%              | 78.2%                                           | 80.2%                                 | 71.5%           |
| GPQA diamond _(multiple attempts)_          | —                                         | —                           | —                  | **84.8%**                                       | **84.6%**                             | —               |
| **Mathematics**                             |                                           |                             |                    |                                                 |                                       |                 |
| AIME 2025 _(single attempt, pass@1)_        | **86.7%**                                 | 86.5%                       | —                  | 49.5%                                           | 77.3%                                 | 70.0%           |
| AIME 2025 _(multiple attempts)_             | —                                         | —                           | —                  | —                                               | **93.3%**                             | —               |
| AIME 2024 _(single attempt, pass@1)_        | **92.0%**                                 | 87.3%                       | 36.7%              | 61.3%                                           | 83.9%                                 | 79.8%           |
| AIME 2024 _(multiple attempts)_             | —                                         | —                           | —                  | **80.0%**                                       | **93.3%**                             | —               |
| **Code generation**                         |                                           |                             |                    |                                                 |                                       |                 |
| LiveCodeBench v5 _(single attempt, pass@1)_ | 70.4%                                     | **74.1%**                   | —                  | —                                               | 70.6%                                 | 64.3%           |
| LiveCodeBench v5 _(multiple attempts)_      | —                                         | —                           | —                  | —                                               | **79.4%**                             | —               |
| **Code editing**                            |                                           |                             |                    |                                                 |                                       |                 |
| Aider Polyglot                              | 74.0% / 68.6%                             | 60.4% _(diff)_              | 44.9% _(diff)_     | 64.9% _(diff)_                                  | —                                     | 56.9% _(diff)_  |
| **Agentic coding**                          |                                           |                             |                    |                                                 |                                       |                 |
| SWE-bench verified                          | 63.8%                                     | 49.3%                       | 38.0%              | **70.3%**                                       | —                                     | 49.2%           |
| **Factuality**                              |                                           |                             |                    |                                                 |                                       |                 |
| SimpleQA                                    | **52.9%**                                 | 13.8%                       | 62.5%              | —                                               | 43.6%                                 | 30.1%           |
| **Visual reasoning**                        |                                           |                             |                    |                                                 |                                       |                 |
| MMMU _(single attempt)_                     | **81.7%**                                 | No MM support               | 74.4%              | 75.0%                                           | 76.0%                                 | No MM support   |
| MMMU _(multiple attempts)_                  | No MM support                             | —                           | —                  | —                                               | **78.0%**                             | No MM support   |
| **Image understanding**                     |                                           |                             |                    |                                                 |                                       |                 |
| Vibe-Eval (Reka)                            | 69.4%                                     | No MM support               | —                  | —                                               | —                                     | No MM support   |
| **Long context**                            |                                           |                             |                    |                                                 |                                       |                 |
| MRCR _(128k average)_                       | **94.5%**                                 | 61.4%                       | 64.0%              | —                                               | —                                     | —               |
| MRCR _(1M pointwise)_                       | **83.1%**                                 | —                           | —                  | —                                               | —                                     | —               |
| **Multilingual performance**                |                                           |                             |                    |                                                 |                                       |                 |
| Global MMLU (Lite)                          | **89.8%**                                 | —                           | —                  | —                                               | —                                     | —               |

---

## 🔹 Footnotes & Methodology

### **Methodology**

- **Gemini results:** All Gemini 2.5 Pro scores are pass@1 (no majority voting or parallel test time compute unless indicated otherwise). They are all run with the AI Studio API for the model-id `gemini-2.5-pro-exp-03-25` with default sampling settings. To reduce variance, we average over multiple trials for smaller benchmarks. Vibe-Eval results are reported using Gemini as a judge.

- **Non-Gemini results:** All the results for non-Gemini models are sourced from providers' self-reported numbers. All SWE-bench Verified numbers follow official provider reports, using different scaffolding and infrastructure. Google’s scaffolding includes drawing multiple trajectories and re-scoring them using model’s own judgement.

- **Thinking vs non-thinking:** For Claude 3.7 Sonnet: GPQA, AIME 2024, MMMU come with 64k extended thinking; Aider with 32k; and HLE with 16k. Remaining results come from the non-thinking model due to result availability. For Grok-3 all results come with extended reasoning except for SimpleQA (based on xAI reports).

- **Single attempt vs multiple attempts:** When two numbers are reported for the same evaluation, higher number uses majority voting with n=64 for Grok models and internal scoring with parallel test time compute for Anthropic models.

- **Result sources:**
  - Humanity's Last Exam:
    - [agi.safe.ai](https://agi.safe.ai/)
    - [scale.com/leaderboard/humanitys_last_exam](https://scale.com/leaderboard/humanitys_last_exam)
  - AIME 2025: [matharena.ai](https://matharena.ai/)
  - LiveCodeBench: [livecodebench.github.io](https://livecodebench.github.io/)
  - Aider Polyglot: [aider.chat/docs/leaderboards](https://aider.chat/docs/leaderboards)
  - MRCR includes 128k results as a cumulative score and 1M pointwise values to show full-length model capability.

### **Symbol Key**

- `*` indicates evaluation on **text problems only** (no images)
- “diff” = performance difference from base output after edits (for Aider Polyglot)
- “pass@1” = first-attempt success rate (no majority vote)

---

## 🔹 Model Comparison Table

| **Category / Benchmark**                | **Llama 4 Maverick** | **Gemini 2.0 Flash** | **DeepSeek v3.1**          | **GPT-4o** |
| --------------------------------------- | -------------------- | -------------------- | -------------------------- | ---------- |
| **Inference Cost**                      |                      |                      |                            |            |
| Price per 1M Input & Output tokens      | **$0.19–$0.49⁵**     | $0.17                | $0.48                      | $4.38      |
| **Image Reasoning**                     |                      |                      |                            |            |
| MMMU                                    | 73.4                 | 71.7                 | _(No multimodal support)_  | 69.1       |
| MathVista                               | 73.7                 | 73.1                 | _(No multimodal support)_  | 63.8       |
| **Image Understanding**                 |                      |                      |                            |            |
| ChartQA                                 | **90.0**             | 88.3                 | —                          | 85.7       |
| DocVQA _(test)_                         | **94.4**             | —                    | —                          | 92.8       |
| **Coding**                              |                      |                      |                            |            |
| LiveCodeBench _(10/01/2024–02/01/2025)_ | **43.4**             | 34.5                 | **45.8/49.2²**             | 32.3³      |
| **Reasoning & Knowledge**               |                      |                      |                            |            |
| MMLU Pro                                | **80.5**             | 77.6                 | **81.2**                   | —          |
| GPQA Diamond                            | **69.8**             | 60.1                 | 68.4                       | 53.6       |
| **Multilingual**                        |                      |                      |                            |            |
| Multilingual MMLU                       | **84.6**             | —                    | —                          | 81.5       |
| **Long Context**                        |                      |                      |                            |            |
| MTOB _(half book)_                      | **54.0 / 46.4**      | 48.4 / 39.8⁰         | _(Context window is 128K)_ | _(128K)_   |
| MTOB _(full book)_                      | **50.8 / 46.7**      | 45.5 / 39.6¹         | _(Context window is 128K)_ | _(128K)_   |

---

## 🔹 Footnotes

1. **Llama model results** are 0 shot with temperature = 0 and no majority voting or parallel test time compute. For high-variance benchmarks (GPQA Diamond, LiveCodeBench), results are averaged over multiple generations to reduce uncertainty.

2. For **non-Llama models**, highest available self-reported eval results are shown, unless otherwise noted. Evals must come from reproducible models (via API/open weights), and are only from non-thinking modes.

3. **Cost estimates** for non-Llama models are from Artificial Analysis.

4. **DeepSeek v3.1’s** range is unknown (49.2), so internal result (45.8) is used on defined data range. GPT-4o results are from LCB leaderboard.

5. **Specialized long context evals** are not typically reported for generalist models, so internal runs are used to show Llama's frontier performance.

6. **$0.19/1Mtok (3:1 blended)** is the cost estimate for Llama 4 Maverick using distributed inference. On a single host, cost is projected at $0.30–$0.49/1Mtok.

---

## 🔹 Model Comparison Table

| **Category / Benchmark**                | **Llama 4 Scout** | **Llama 3.3 70B**          | **Llama 3.1 405B**         | **Gemma 3 (27B)**          | **Mistral 3.1 (24B)**      | **Gemini 2.0 Flash-Lite** |
| --------------------------------------- | ----------------- | -------------------------- | -------------------------- | -------------------------- | -------------------------- | ------------------------- |
| **Image Reasoning**                     |                   |                            |                            |                            |                            |                           |
| MMMU                                    | 69.4              | —                          | —                          | 64.9                       | 62.8                       | 68.6                      |
| MathVista                               | 70.7              | —                          | —                          | 67.6                       | 68.9                       | 57.6                      |
| **Image Understanding**                 |                   |                            |                            |                            |                            |                           |
| ChartQA                                 | 88.8              | No multimodal support      | No multimodal support      | 76.3                       | **86.2**                   | 73.0                      |
| DocVQA                                  | **94.4**          | —                          | —                          | 90.4                       | **94.1**                   | 91.2                      |
| **Coding**                              |                   |                            |                            |                            |                            |                           |
| LiveCodeBench _(10/01/2024–02/01/2025)_ | 32.8              | **33.3**                   | 27.7                       | 29.7                       | —                          | 28.9                      |
| **Reasoning & Knowledge**               |                   |                            |                            |                            |                            |                           |
| MMLU Pro                                | 74.3              | 68.9                       | 73.4                       | 67.5                       | 66.8                       | 71.6                      |
| GPQA Diamond                            | **57.2**          | 50.5                       | 49.0                       | 42.4                       | 46.0                       | 51.5                      |
| **Long Context**                        |                   |                            |                            |                            |                            |                           |
| MTOB _(half book)_                      | **42.2 / 36.6**   | _(Context window is 128K)_ | _(Context window is 128K)_ | _(Context window is 128K)_ | _(Context window is 128K)_ | 42.3 / 35.1¹              |
| MTOB _(full book)_                      | **39.7 / 36.3**   | —                          | —                          | —                          | —                          | 35.1 / 30.0²              |

---

## 🔹 Footnotes

1. For Llama model results, we report 0 shot evaluation with temperature = 0 and no majority voting or parallel test time compute. For high-variance benchmarks (GPQA Diamond, LiveCodeBench), we average over multiple generations to reduce uncertainty.

2. For non-Llama models, we source the highest available self-reported eval results unless otherwise specified. We only include evals from models that have reproducible evals (via API or open weights), and we only include non-thinking modes.

3. Specialized long context evals are not traditionally reported for generalist models, so we share internal runs to showcase Llama's frontier performance.

---

Would you like a **summary comparison vs GPT-4o**, a **ranking by task (e.g., best for coding)**, or suggestions for model selection based on use case (e.g., cost-efficient, multilingual, visual reasoning)?

Here is the **full transcription** of the benchmark comparison image between **Llama 4 Behemoth**, **Claude Sonnet 3.7**, **Gemini 2.0 Pro**, and **GPT-4.5**, including the footnotes and visible partner ecosystem logos:

---

## 🔹 Model Comparison Table

| **Category / Benchmark**                | **Llama 4 Behemoth** | **Claude Sonnet 3.7** | **Gemini 2.0 Pro** | **GPT-4.5** |
| --------------------------------------- | -------------------- | --------------------- | ------------------ | ----------- |
| **Coding**                              |                      |                       |                    |             |
| LiveCodeBench _(10/01/2024–02/01/2025)_ | **49.4**             | —                     | 36.0               | —           |
| **Reasoning & Knowledge**               |                      |                       |                    |             |
| MATH-500                                | **95.0**             | 82.2                  | 91.8               | —           |
| MMLU Pro                                | **82.2**             | —                     | 79.1               | —           |
| GPQA Diamond                            | **73.7**             | 68.0                  | 64.7               | 71.4        |
| **Multilingual**                        |                      |                       |                    |             |
| Multilingual MMLU _(OpenAI)_            | **85.8**             | 83.2                  | —                  | 85.1        |
| **Image Reasoning**                     |                      |                       |                    |             |
| MMMU                                    | **76.1**             | 71.8                  | 72.7               | 74.4        |

---

## 🔹 Footnotes

1. Llama model results represent our current best internal runs.
2. For non-Llama models, we source the highest available self-reported eval results, unless otherwise specified. We only include evals from models that have reproducible evals (via API or open weights) and we only include non-thinking models.

---

### **1. Natively Multimodal**

> All Llama 4 models are designed with native multimodality, leveraging early fusion that allows us to pre-train the model with large amounts of unlabeled text and vision tokens – a step change in intelligence from separate, frozen multimodal weights.

---

### **2. Advanced Problem Solving**

> Llama 4 Scout and Llama 4 Maverick can tackle intricate problems, offering intelligent solutions across complex domains.

---

### **3. Unparalleled Long Context**

> Llama 4 Scout supports up to 10M tokens of context – the longest context length available in the industry – unlocking new use cases around memory, personalization, and multi-modal applications.

---

### **4. Expert Image Grounding**

> Llama 4 is also best-in-class on image grounding, able to align user prompts with relevant visual concepts and anchor model responses to regions in the image.

---

### **5. Multilingual Writing**

> Llama 4 was also pre-trained and fine-tuned for unrivaled text understanding across 12 languages, supporting global development and deployment.

---

### **6. Model Cards**

#### **Llama 4 Scout**

> Class-leading natively multimodal model that offers superior text and visual intelligence, single H100 GPU efficiency, and a 10M context window for seamless long document analysis.

#### **Llama 4 Maverick**

> Industry-leading natively multimodal model for image and text understanding with groundbreaking intelligence and fast responses at a low cost.

#### **Llama 4 Behemoth Preview**

> An early preview (it’s still training!) of the Llama 4 teacher model used to distill Llama 4 Scout and Llama 4 Maverick. Learn more about it.
> **[View blog]**

---

### **7. Hero Banner**

> **Llama 4: Leading intelligence. Unrivaled speed and efficiency.**
> The most accessible and scalable generation of Llama is here. Native multimodality, mixture-of-experts models, super long context windows, step changes in performance, and unparalleled efficiency. All in easy-to-deploy sizes custom fit for how you want to use it.
