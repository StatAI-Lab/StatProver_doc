<style>
  h1:first-of-type { 
    display: none !important; 
  }
</style>


![StatProver](figs/logo.png)




<p align="center">
  <b>An  Automated Proof Generation and Self-Correction Agent for Rigorous Statistical Derivations</b>
</p>



Recently, the team **[StatAI Lab](https://statai-lab.github.io/)**, led by Professor **[Fan Zhou](https://mlzxzhou.github.io/)** from the School of Statistics and Data Science at Shanghai University of Finance and Economics officially released **StatProver**. Following the statistical reasoning evaluation benchmark **[StatEval](https://stateval.github.io/)**, this is another practical achievement by the StatAI Lab in enhancing the statistical proving capabilities of Large Language Models (LLMs). 

## What We Do

Recent benchmarks, such as [StatEval](https://stateval.github.io/), have evaluated state-of-the-art models in this area, showing their limitations in solving research-level proofs. Therefore, a dedicated framework is needed to improve LLM reasoning capabilities for statistical problem-solving. The system we developed aims to solve the issues of logical gaps and formula hallucinations that frequently occur when LLMs handle highly complex statistical derivations, realizing fully automated generation and self-correction from statistical propositions to rigorous LaTeX proofs.

StatProver's design balances the convenience of automation with the rigor of scientific research: the system not only supports one-click, end-to-end fully automated proof generation, but also introduces a flexible human-AI collaboration mechanism. This workflow allows users to manually intervene at key nodes—such as keyword retrieval, framework generation, and error correction—ensuring that the derivation process remains highly controllable and accurate.

## How We Do This

StatProver does not simply have the model generate an answer directly; instead, it ensures the quality of the proof through a robust six-stage pipeline:

![StatProver Pipeline Architecture](figs/StatProver.png)

* **Multimodal Input** Supports text descriptions or uploaded PDF documents to directly identify the proof requirements.
* **Initial Retrieval** Extracts keywords from the problem and calculates embedding cosine similarity to match 40 similar cases from our vector database.
* **Framework Refinement** Refines the initially generated proof framework by cross-referencing the retrieved similar cases.
* **Proof Generation** Generates a complete initial draft of the proof based on the refined framework.
* **Self-Correction** Utilizes an exclusive "error snippet database" to conduct fine-grained, snippet-level logical checks.
* **Final Correction** Summarizes all identified errors, performs targeted fixes on the initial draft, and outputs the final, rigorous proof.

## Highlights

- **Retrieval-Driven Proof Framework Refinement**:  We employ a bi-directional max-matching algorithm and an LLM-as-a-Judge mechanism to retrieve optimal reference frameworks. This dynamically refines the initial draft into a logically robust macro-skeleton, preventing early trajectory drift.

- **Data-Driven Snippet-Level Self-Correction**: Leveraging a large-scale repository of empirical LLM reasoning failures on the statistical reasoning evaluation benchmark [StatEval](https://stateval.github.io/), we introduce a dynamic self-correction mechanism to identify and surgically rectify subtle micro-level logical leaps that standard self-reflection methods fail to detect. 

- **Interactive Proof Assistant Platform**: We present StatProver, a modular six-stage pipeline that supports both end-to-end automated proof generation and flexible HIL workflows. This system is officially deployed and publicly accessible at https://statprover.com.

## Try It Out!

**[Official Website](https://statprover.com) : 3 free use on registry, 1 free use per day!**

**[Download Full StatProver Technical Report (PDF)](StatProver_Technical_Report.pdf)**

## Contact Us

If you have any questions or are interested in collaboration, please feel free to reach out to our laboratory:

* **[StatAI Lab](https://statai-lab.github.io/)**: [statai@163.com](mailto:statai@163.com)
* **[Prof. Fan Zhou](https://mlzxzhou.github.io/)** (Project Leader): [zhoufan@mail.shufe.edu.cn](mailto:zhoufan@mail.shufe.edu.cn)