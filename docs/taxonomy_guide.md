# Taxonomy Guide

This document provides detailed explanations of our 2D taxonomy for interactive evaluation.

## Overview

Interactive evaluation requires assessing **how systems act over time**, not just their final outputs. Our taxonomy organizes benchmarks along two orthogonal axes:

## Axis 1: Evaluation Inputs (What trajectories connect to)

### 🛠️ Tools & Environments

**Definition**: Systems interact with external digital environments (web browsers, operating systems, code repositories, databases, APIs).

**Key Characteristics**:
- Deterministic or semi-deterministic state transitions
- Programmatic observation spaces (DOM, file systems, API responses)
- Clear action spaces (clicks, commands, API calls)

**Example Benchmarks**:
- **WebArena**: Navigate and complete tasks on websites
- **OSWorld**: Interact with desktop operating systems
- **SWE-Bench**: Resolve GitHub issues in code repositories
- **ToolBench**: Use APIs and external tools to solve tasks

**Evaluation Challenges**:
- State space complexity
- Partial observability
- Resettability and reproducibility

---

### 👤 Users

**Definition**: Systems interact with humans who provide feedback, clarify instructions, or collaborate on tasks.

**Key Characteristics**:
- Non-deterministic human responses
- Natural language communication
- Evolving goals and preferences
- Subjective quality judgments

**Example Benchmarks**:
- **UserSim**: Simulated user interactions for task clarification
- **MT-Bench**: Human evaluation of conversational quality
- **AlpacaEval**: Human preference judgments on helpfulness

**Evaluation Challenges**:
- Recruiting human participants
- Annotation cost and scalability
- Inter-annotator agreement
- Capturing implicit preferences

---

### 🤝 Other Agents

**Definition**: Systems interact with other AI agents in multi-agent scenarios requiring coordination, negotiation, or competition.

**Key Characteristics**:
- Strategic behavior
- Communication protocols
- Emergent coordination
- Game-theoretic considerations

**Example Benchmarks**:
- **Sotopia**: Social interactions between AI agents
- **Avalon**: Deception and deduction games
- **AgentBench**: Multi-agent task completion

**Evaluation Challenges**:
- Agent diversity and population dynamics
- Equilibrium analysis
- Reproducibility with stochastic agents

---

### 🌐 Hybrid & Dynamic

**Definition**: Systems operate in environments combining multiple input types OR environments with persistent state that changes over time.

**Key Characteristics**:
- Persistent state across sessions
- Long time horizons
- Multiple interaction modalities
- Non-episodic structure

**Example Benchmarks**:
- **AppWorld**: Persistent application state across tasks
- **Minecraft collaborative building**: Mixed agent-user-environment
- **Classroom simulation**: Dynamic human-agent-environment systems

**Evaluation Challenges**:
- State management and reproducibility
- Long-term dependency tracking
- Cross-session evaluation

---

## Axis 2: Evaluation Programs (How trajectories → judgments)

### ✅ Task Success

**Definition**: Did the system achieve its specified goal?

**Metrics**:
- Binary success rate
- Partial credit for subtask completion
- Goal state matching (exact or fuzzy)

**Examples**:
- **WebArena**: Page navigation success, form submission correctness
- **SWE-Bench**: Test pass rate after patch application
- **GAIA**: Correct final answer to multi-step questions

**Limitations**:
- Doesn't capture **how** the goal was achieved
- Ignores process quality
- May miss safety violations

---

### ⚙️ Process Quality & Efficiency

**Definition**: Evaluate **how** the system achieved its goal — tool usage, action efficiency, code quality.

**Metrics**:
- Number of actions taken
- Cost (API calls, token usage)
- Code locality (SWE-Bench)
- Tool selection appropriateness
- Redundancy and backtracking

**Examples**:
- **SWE-Bench**: Code locality (minimal file edits)
- **ToolBench**: Tool call efficiency
- **API-Bank**: API usage optimality

**Why it matters**:
- Detects systems that succeed through brute force
- Identifies inefficiencies
- Reveals learning vs. search trade-offs

---

### 🔄 Recoverability & Robustness

**Definition**: Can the system detect errors, revise plans, and recover from failures?

**Metrics**:
- Recovery rate after perturbations
- Time to recover
- Adaptation to distribution shifts
- Self-correction frequency

**Examples**:
- **OSWorld**: Handling UI changes or missing elements
- **Perturbed instructions**: Measuring robustness to noisy inputs
- **Agent Hospital**: Diagnosing and fixing failures

**Why it matters**:
- Real-world systems face unexpected situations
- Brittleness is a major deployment risk
- Separates memorization from reasoning

**Challenges**:
- Defining meaningful perturbations
- Baseline comparison (perturbed vs. unperturbed)

---

### 🛡️ Safety, Alignment & Social Competence

**Definition**: Does the system behave safely, follow social norms, and respect user preferences?

**Metrics**:
- Safety violation rate
- Norm adherence
- Cooperative vs. competitive behavior
- Deception detection
- Ethical decision-making

**Examples**:
- **Sotopia**: Social goal achievement, relationship maintenance
- **Machiavelli**: Ethical behavior in games
- **Toxicity detection**: Avoiding harmful outputs during interactions

**Why it matters**:
- Critical for real-world deployment
- Misalignment can cause harm
- Social competence required for human collaboration

**Challenges**:
- Defining "correct" social behavior
- Cultural context dependency
- Trade-offs between goals and constraints

---

## Using the Taxonomy

### Categorizing a Benchmark

When analyzing a new benchmark, ask:

1. **What does the system interact with?** (Evaluation Inputs)
   - Only tools/environments? → Tools & Environments
   - Humans in the loop? → Users
   - Multiple AI agents? → Other Agents
   - Mix of above or persistent state? → Hybrid & Dynamic

2. **What properties are measured?** (Evaluation Programs)
   - Only final success? → Task Success
   - Efficiency or quality of actions? → Process Quality
   - Error recovery tested? → Recoverability
   - Social/safety aspects? → Safety & Alignment

**Note**: Benchmarks may belong to multiple categories!

### Design Implications

- **Tools & Environments**: Focus on reproducibility, observation design
- **Users**: Invest in annotation protocols, subjective metrics
- **Other Agents**: Consider population dynamics, equilibrium
- **Hybrid & Dynamic**: Long-term state management critical
- **Task Success**: Ensure goal specification is precise
- **Process Quality**: Log trajectories richly
- **Recoverability**: Design meaningful perturbations
- **Safety**: Operationalize norms, define constraints

---

## Key Insights from Survey

1. **Most benchmarks focus on Task Success alone** — missing process and safety
2. **Hybrid & Dynamic severely underexplored** — only 7 of 70+ benchmarks
3. **Trajectory data often collected but not used** — logged but only scored on outcomes
4. **Substrate determines what gets measured** — web environments enable action tracking, users enable preference measurement

---

## Further Reading

- See [README.md](../README.md) for framework overview
- See [benchmarks.json](../data/benchmarks.json) for categorized benchmarks
- See paper Section 3 for formal definitions
