# Quick Start Guide

Welcome! This guide will help you navigate the Interactive Evaluation project.

## 📚 Understanding the Work

### 1. Read the Paper
Start with the [paper on arXiv](https://arxiv.org/) to understand our framework:
- **Section 1**: Motivation — why response-centered evaluation is insufficient
- **Section 2**: Framework — the E: X → Y mapping
- **Section 3**: Taxonomy — organizing interactive benchmarks
- **Section 4**: Survey — 70+ benchmarks analyzed
- **Section 5**: Design principles — recommendations for future work

### 2. Explore the Taxonomy
Read the [Taxonomy Guide](taxonomy_guide.md) for detailed explanations of:
- **4 Evaluation Input categories**
- **4 Evaluation Program types**
- How to categorize benchmarks

### 3. Browse Benchmarks
- **Structured data**: [benchmarks.json](../data/benchmarks.json)
- **2D Taxonomy map**: [taxonomy_map.pdf](../assets/taxonomy_map.pdf)
- **Statistics**: [metadata.json](../data/metadata.json)

---

## 🔍 Exploring Benchmarks

### By Stage
```bash
# Response-Centered (Stage 1): 20 benchmarks
SQuAD, MMLU, GSM8K, HumanEval, MBPP, etc.

# Task-Driven (Stage 2): 16 benchmarks  
SWE-Bench, GAIA, Mind2Web, ToolBench, etc.

# Interactive (Stage 3): 34 benchmarks
WebArena, OSWorld, Sotopia, AppWorld, etc.
```

### By Evaluation Input
- **Tools & Environments**: 42 benchmarks (web, OS, code, APIs)
- **Users**: 8 benchmarks (human feedback, preferences)
- **Other Agents**: 5 benchmarks (multi-agent coordination)
- **Hybrid & Dynamic**: 7 benchmarks (persistent state, mixed inputs)

### By Evaluation Program
- **Task Success**: 58 benchmarks (goal achievement)
- **Process Quality**: 12 benchmarks (efficiency, code quality)
- **Recoverability**: 2 benchmarks (error recovery, robustness)
- **Safety & Social**: 7 benchmarks (norms, cooperation, safety)

---

## 🎯 Use Cases

### For Researchers
**Designing a new benchmark?**
1. Use our taxonomy to identify gaps
2. Follow our 5 design principles (README)
3. Check what existing benchmarks measure
4. Consider hybrid/dynamic settings (underexplored!)

**Writing a paper?**
- Cite specific benchmarks from our database
- Use taxonomy to organize related work
- Reference design principles in methodology

### For Practitioners
**Evaluating a system?**
1. Identify what it interacts with (Axis 1)
2. Determine what properties matter (Axis 2)
3. Select appropriate benchmarks from our database
4. Consider multiple evaluation programs (not just task success)

**Building an agent?**
- See which benchmarks test your interaction mode
- Check what top systems achieve
- Identify underexplored capabilities

### For Students
**Learning about evaluation?**
1. Start with the taxonomy guide
2. Browse benchmarks by category
3. Read papers for representative benchmarks
4. Trace evolution from Stage 1 → 2 → 3

---

## 📊 Viewing the Taxonomy

### Access the Map
```bash
# Clone the repository
git clone https://github.com/yourusername/Interactive_Evaluation.git
cd Interactive_Evaluation

# View the taxonomy map
open assets/taxonomy_map.pdf
```

The 2D taxonomy map shows all representative benchmarks organized by:
- **Y-axis**: Evaluation Programs (Task Success, Process Quality, Recoverability, Safety/Alignment/Social)
- **X-axis**: Evaluation Inputs (Tools & Environments, Users, Other Agents, Hybrid & Dynamic)
- **Color**: Stage (Response-Centered, Task-Driven, Interactive)

---

## 🤝 Contributing

Want to add a benchmark or improve the project?

1. **Add a benchmark**: See [CONTRIBUTING.md](../CONTRIBUTING.md)
2. **Report an error**: Open a GitHub issue
3. **Improve docs**: Submit a PR
4. **Improve taxonomy**: Suggest refinements via issues

---

## 📖 Key Concepts

### What is Interactive Evaluation?
Evaluation that goes beyond final outputs to assess:
- **Trajectories**: sequences of actions and observations
- **Processes**: how goals are achieved, not just whether
- **Recovery**: adaptation to errors and changes
- **Safety**: avoiding harm during interaction

### Why does it matter?
- LLMs increasingly act through tools, users, agents
- Brittle systems that "pass" may fail catastrophically
- Need to test **how** systems behave, not just final success

### The E: X → Y Framework
- **X**: Evidence (expands from responses to trajectories)
- **E**: Evaluation program (maps evidence to judgments)
- **Y**: Judgments (task success, safety, efficiency, etc.)

### The 2D Taxonomy
Organizes benchmarks by:
1. **What systems interact with** (inputs)
2. **What properties are measured** (programs)

---

## 🔗 Quick Links

- [Main README](../README.md) — Project overview
- [Taxonomy Guide](taxonomy_guide.md) — Detailed framework
- [Benchmarks Data](../data/benchmarks.json) — Raw JSON
- [2D Taxonomy Map](../assets/taxonomy_map.pdf) — Visual overview
- [Paper on arXiv](https://arxiv.org/) — Full research article
- [Contributing](../CONTRIBUTING.md) — How to help

---

## ❓ FAQ

**Q: How do I cite this work?**  
A: See the BibTeX in the [README](../README.md).

**Q: Can I use the benchmark data for my research?**  
A: Yes! It's MIT licensed. Please cite our paper.

**Q: How often is the database updated?**  
A: We aim for monthly updates as new benchmarks are published.

**Q: I disagree with a categorization. What should I do?**  
A: Open an issue with your reasoning! We welcome discussion.

**Q: Can I add a benchmark not in the survey?**  
A: Yes, as long as it fits our definition of interactive evaluation.

**Q: How do I cite individual benchmarks?**  
A: Each benchmark entry in `benchmarks.json` includes a `paper_url` field with citation information.

---

## 📬 Contact

Questions? Reach out:
- **Keyang Xuan**: keyangx@utexas.edu
- **Peiyang Song**: psong@caltech.edu
- **GitHub Issues**: For technical questions

---

Happy exploring! 🚀
