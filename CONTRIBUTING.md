# Contributing to Interactive Evaluation

Thank you for your interest in contributing to the Interactive Evaluation project! This document provides guidelines for contributing to our benchmark database and documentation.

## 🎯 Ways to Contribute

### 1. Add New Benchmarks

Help us keep the benchmark database up-to-date by adding new interactive evaluation benchmarks.

**Requirements:**
- The benchmark must be publicly available (paper or code)
- It should fit within our definition of interactive evaluation
- Provide accurate metadata (citations, stars, URLs)

**How to add:**
1. Fork the repository
2. Add your benchmark to `data/benchmarks.json` following the schema below
3. Update `data/metadata.json` statistics
4. Submit a pull request with a clear description

**Benchmark Schema:**
```json
{
  "id": "unique-identifier",
  "name": "Benchmark Name",
  "year": 2025,
  "stage": "Interactive|Task-Driven|Response-Centered",
  "task_type": "Brief task description",
  "evaluation_input": ["Tools & Environments", "Users", etc.],
  "evaluation_program": ["Task Success", "Process Quality", etc.],
  "citations": 100,
  "stars": 500,
  "paper_url": "https://arxiv.org/...",
  "github_url": "https://github.com/...",
  "description": "One-sentence description"
}
```

### 2. Improve Categorization

If you believe a benchmark is miscategorized:
1. Open an issue explaining your reasoning
2. Provide evidence from the paper or code
3. Suggest the correct category based on our taxonomy

### 3. Fix Errors

Found a typo, broken link, or incorrect data?
1. Open an issue or directly submit a PR
2. For data corrections, cite your source

### 4. Enhance Visualizations

We welcome improvements to our visualization tools:
- Better interactive features
- Mobile responsiveness
- Accessibility improvements
- New visualization types

### 5. Expand Documentation

Help make our framework clearer:
- Add examples and use cases
- Clarify definitions
- Improve explanations
- Translate content

## 📋 Pull Request Process

1. **Fork & Branch**: Create a new branch from `main`
2. **Make Changes**: Follow our style guide below
3. **Test**: Ensure JSON is valid and visualization still works
4. **Commit**: Write clear, descriptive commit messages
5. **PR**: Submit with a detailed description of changes

### Commit Message Format
```
[TYPE] Brief description

Detailed explanation if needed

- Added benchmark: BenchmarkName
- Updated metadata for citations
- Fixed typo in README
```

Types: `[ADD]`, `[UPDATE]`, `[FIX]`, `[DOCS]`, `[VIZ]`

## 📏 Style Guide

### JSON Files
- Use 2-space indentation
- Keep alphabetical order where possible
- Validate JSON before committing

### Markdown
- Use proper heading hierarchy
- Include links where relevant
- Keep lines under 120 characters when possible

### Benchmark Descriptions
- One clear sentence
- Focus on what makes it distinctive
- Avoid marketing language

## 🔍 Review Process

1. All PRs require at least one review
2. Automated checks must pass
3. Maintainers may request changes
4. Once approved, we'll merge and update the visualization

## ❓ Questions?

- **General questions**: Open a GitHub Discussion
- **Bug reports**: Open an issue with the "bug" label
- **Feature requests**: Open an issue with the "enhancement" label
- **Private inquiries**: Email keyangx@utexas.edu

## 📜 Code of Conduct

- Be respectful and constructive
- Focus on the work, not the person
- Assume good intent
- No harassment or discrimination

## 🙏 Recognition

All contributors will be acknowledged in our [Contributors](CONTRIBUTORS.md) file and on the project website.

---

Thank you for helping build a comprehensive resource for the interactive evaluation community!
