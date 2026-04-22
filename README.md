<style>
  h1:first-of-type { 
    display: none !important; 
  }
</style>


![StatProver](https://raw.githubusercontent.com/StatAI-Lab/StatProver_doc/main/figs/logo.png)

<p align="center">
  <b>An Automated Statistical Proof Assistant</b>
</p>

**StatProver** is developed by **[StatAI Lab](https://statai-lab.github.io/)**, led by **[Prof. Fan Zhou](https://mlzxzhou.github.io/)** at the School of Statistics and Data Science, Shanghai University of Finance and Economics. As part of the lab’s broader research on statistical reasoning with large language models, this project reflects our efforts to build reliable AI systems for rigorous statistical proofs.


## What StatProver Does

StatProver provides a structured workflow for automated proof generation and self-correction, helping users transform a statistical proposition or source document into a complete LaTeX proof. Built on the comprehensive statistical reasoning benchmark **[StatEval](https://stateval.github.io/)**, StatProver retrieves relevant references to refine proof skeletons and performs self-correction by learning from the strategies and details of similar theoretical proofs.

<video width="100%" autoplay loop muted playsinline>
  <source src="https://raw.githubusercontent.com/StatAI-Lab/StatProver_doc/main/videos/demo.mp4" type="video/mp4">
</video>

The system supports both end-to-end automated proof construction and flexible human-in-the-loop interaction. Users can intervene at key stages such as problem refinement, framework selection, and error correction, making the proof process both efficient and controllable.



## How StatProver Works

StatProver does not rely on one-shot proof generation. Instead, it organizes the derivation process into a six-stage pipeline that supports both automated execution and human intervention at key checkpoints.

![StatProver Pipeline Architecture](https://raw.githubusercontent.com/StatAI-Lab/StatProver_doc/main/figs/StatProver.png)

* **Step 1. Interactive Problem Refinement**

The system first checks whether the input problem is complete and identifies missing assumptions, definitions, or notation. Users can supplement these details manually or let the model help complete them, producing a structured problem description with explicit prerequisites and proof goals.

* **Step 2. Candidate Retrieval and User Verification**

StatProver extracts core keywords from the problem and retrieves relevant reference cases from a large statistical problem database using embedding-based similarity. It then narrows these candidates and presents the most relevant ones for user verification before they are used in later stages.

* **Step 3. Dynamic Framework Refinement**

Using the verified reference cases, the system evaluates whether their proof frameworks provide useful methodological guidance for the current task. When appropriate, it refines the initial proof skeleton by incorporating helpful proof strategies while keeping the target problem itself as the primary source of structure.

* **Step 4. Draft Proof Generation**

Based on the refined framework and the completed problem description, StatProver generates a full draft proof with detailed intermediate derivation steps rather than a short final answer.

* **Step 5. Data-Driven Snippet-Level Diagnosis**

The generated proof is segmented into fine-grained logical units and checked against a repository of historical error patterns. This allows the system to detect local reasoning flaws, logical jumps, and other proof-level inconsistencies that are often missed by generic self-reflection.

* **Step 6. Global Correction and Final Output**

Finally, StatProver performs targeted correction based on the diagnosed issues and consolidates the revised reasoning into a rigorous final proof in LaTeX format.

## Key Contributions

**Contribution 1. Retrieval-Driven Framework Refinement**

StatProver retrieves reference cases from a database of **40,366** research-level statistical problems drawn from **[StatEval](https://stateval.github.io/)**. Through similarity-based retrieval and framework verification, the system refines the initial proof skeleton and improves the global structure of the derivation.

**Contribution 2. Data-Driven Snippet-Level Self-Correction**

StatProver also uses a large empirical fault repository containing over **80,000** error snippets, constructed from LLM failure trajectories on **[StatEval’s](https://stateval.github.io/)** research-level data. This repository supports fine-grained diagnosis and targeted correction, allowing the system to identify subtle logical gaps and proof errors beyond standard self-reflection.

**Contribution 3. Interactive Proof Assistant Platform**

StatProver integrates these components into a unified proof assistant that supports both fully automated generation and flexible human-in-the-loop workflows. The platform is publicly available and designed to assist researchers in producing rigorous statistical proofs more efficiently and reliably. This system is officially deployed and publicly accessible at **[https://statprover.com](https://statprover.com)**.

## Try It Out!

**[Official Website](https://statprover.com) : 3 free use on registry, 1 free use per day!**

**[Download Full StatProver Technical Report (PDF)](https://raw.githubusercontent.com/StatAI-Lab/StatProver_doc/main/StatProver_Technical_Report.pdf)**

## Contact Us

If you have any questions or are interested in collaboration, please feel free to reach out to our laboratory:

* **[StatAI Lab](https://statai-lab.github.io/)**: [statai@163.com](mailto:statai@163.com)
* **[Prof. Fan Zhou](https://mlzxzhou.github.io/)** (Project Leader): [zhoufan@mail.shufe.edu.cn](mailto:zhoufan@mail.shufe.edu.cn)