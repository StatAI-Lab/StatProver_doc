<style>
  h1:first-of-type { 
    display: none !important; 
  }
</style>

# [StatProver](https://statprover.com)

**An LLM-Based Automated Proof Generation and Self-Correction System for Rigorous Statistical Derivations**, by **[StatAI Lab](https://statai-lab.github.io/)**, School of Statistics and Data Science, Shanghai University of Finance and Economics

<video width="100%" autoplay loop muted playsinline>
  <source src="./videos/demo.mp4" type="video/mp4">
</video>

# Core Technical Features

**1. Bi-directional Max-Matching Retrieval**

Instead of using global sentence embeddings (which suffer from semantic dilution), StatProver extracts dual-perspective keywords and uses asymmetric matching to find the most similar reference problems from a database of 40,366 statistical problems.

**2. LLM-as-a-Judge Framework Selection**

GPT-5.4 evaluates retrieved candidates not just by similarity, but by whether their actual proof structure provides actionable reference value for the current problem.

**3. Data-Driven Fault Repository**

By analyzing 80,000+ failure trajectories from LLM attempts on StatEval, we built an empirical fault repository. During inference, StatProver dynamically segments proofs, matches against historical faults, and executes targeted corrections.


# System Pipeline

![StatProver Pipeline Architecture](figs/StatProver.png)


# Key Contributions

- **Retrieval-Driven Proof Framework Refinement**:  We employ a bi-directional max-matching algorithm and an LLM-as-a-Judge mechanism to retrieve optimal reference frameworks. This dynamically refines the initial draft into a logically robust macro-skeleton, preventing early trajectory drift.

- **Data-Driven Snippet-Level Self-Correction**: Leveraging a large-scale repository of empirical LLM reasoning failures, we introduce a dynamic self-correction mechanism to identify and surgically rectify subtle micro-level logical leaps that standard self-reflection methods fail to detect. 

- **Interactive Proof Assistant Platform**: We present StatProver, a modular six-stage pipeline that supports both end-to-end automated proof generation and flexible HIL workflows. This system is officially deployed and publicly accessible at https://statprover.com.


# Try It Out

**[Download Full StatProver Technical Report (PDF)](StatProver_Technical_Report.pdf)**

**[Official Website](https://statprover.com) : 3 free use per day!**

# Contact Us

- **[Prof. Fan Zhou](https://mlzxzhou.github.io/)**: zhoufan@mail.shufe.edu.cn
- **[StatAI Lab](https://statai-lab.github.io/)**: statai@163.com