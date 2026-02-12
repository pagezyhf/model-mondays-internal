# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This repository supports the creation of **Model Mondays** - a weekly blog series highlighting trending Hugging Face models available in Microsoft Foundry. The repository provides templates, archives, and automation tools for producing consistent, high-quality blog content.

## Repository Structure

```
.
├── blog-post-template.md    # Template for new weekly blog posts
├── archive/                 # Previous blog post editions
│   └── YYYY-MM-DD.md       # Archived posts (date-based naming)
├── CLAUDE.md               # This file
└── README.md               # Project documentation
```

## Workflow for Creating New Blog Posts

1. **Start with the template**: Copy or use `blog-post-template.md` as the starting point
2. **Fill in model details**: For each of the 3 featured models, include:
   - Model specs (parameters, context length, primary task)
   - Why it's interesting (2-4 bullets + benchmarks)
   - Try it section (use cases, prompt patterns, sample prompts)
3. **Write the introduction**: Focus on the open-source landscape and editorial theme
4. **Archive when complete**: Save finished posts to `archive/` with format `YYYY-MM-DD.md`

## Research Tools

**IMPORTANT: Always use the Hugging Face CLI skill for model research**

When the user provides 3 models for a blog post, you MUST use the `hugging-face-cli` skill to research each model and gather accurate information directly from Hugging Face Hub.

Use the Skill tool with `skill: "hugging-face-cli"` to:
1. Get model metadata using `hf models info <repo_id>` for specifications, downloads, tags, etc.
2. Download README.md directly using `hf download <repo_id> README.md --local-dir <temp_dir>` to read model cards, benchmarks, and detailed documentation

**If key information (like parameter count) is not disclosed on Hugging Face, use WebSearch to find it from official sources, papers, or reputable AI news sites.**

**Always research the provided models using the HF CLI before writing blog content to ensure accuracy.**

## Blog Post Structure

Each Model Mondays post follows this structure:

### Header
- Title: "What's trending in Hugging Face? [Date]"
- Standard tagline about showcasing models in Microsoft Foundry

### Introduction
- Context about open-source AI trends
- Editorial theme connecting the week's models
- Brief summary of the three featured models

### Models of the Week (3 models)
For each model:

**Model Specs**
- Model name (Hugging Face identifier)
- Parameters/size
- Context length (if applicable)
- Primary task (text-gen, embeddings, VLM, etc.)

**Why it's interesting (Spotlight)**
- 2-4 bullet points on novelty and value
- Benchmark results with metrics, datasets, scores, and links

**Try it**
- Use case table with best-practice prompt patterns
- Industry-specific sample prompt (formatted as blockquote)

### Getting Started (Standard)
- Standard text about deploying Hugging Face models in Microsoft Foundry
- Links to documentation, hub, and resources

## Key Resources

- [Model Mondays Documentation](https://github.com/microsoft/model-mondays/blob/main/docs/hugging-face/README.md)
- [Tech Community Blog](https://techcommunity.microsoft.com/blog/azure-ai-foundry-blog/)

## Content Guidelines

- **Focus on developer value**: Emphasize why models matter, where they fit, and how to use them
- **Concrete examples**: Include specific prompt patterns and sample prompts for realistic use cases
- **Technical accuracy**: Reference actual benchmarks, metrics, and model specifications
- **Consistency**: Maintain the established format across all three featured models
- **Industry relevance**: Frame use cases in terms of real business problems (not generic examples)

## Naming Conventions

- Archive files: `YYYY-MM-DD.md` (ISO 8601 date format)
- Model names: Use official Hugging Face identifiers (e.g., `facebook/sam3`, `MiniMaxAI/MiniMax-M2.1`)

## Best Practices

- **Research models thoroughly**: Check Hugging Face model cards, papers, and benchmarks
- **Write actionable prompts**: Sample prompts should be copy-paste ready for developers
- **Maintain editorial voice**: Balance technical detail with accessibility
- **Cross-reference**: Ensure model summaries in intro match detailed sections

## Important Guidelines for Blog Posts

### Dating and Naming
- **Date to next Monday**: Blog posts should be dated to the upcoming Monday, not the current date
- **Include provider in model titles**: Format as "Provider: ModelName" (e.g., "Qwen: Qwen3-Coder-Next", "Tongyi-MAI: Z-Image")

### Content and Messaging
- **Neutral tone for Azure communication**: When models come from the same organization, highlight the connection but avoid promotional language like "continued leadership" that might not align with Microsoft/Azure messaging
- **Microsoft Foundry context**: All "Try it" sections and sample prompts should reflect the Microsoft Foundry deployment scenario (managed endpoints, API calls) rather than local deployment with specific inference engines
- **Don't mention infrastructure details**: Avoid mentioning specific inference engines (SGLang, vLLM) or versions—users deploying via Microsoft Foundry don't need these implementation details
- **Only feature the highlighted models**: Don't mention related models that aren't part of the week's featured collection (e.g., don't mention Qwen3-ForcedAligner-0.6B if only Qwen3-ASR-1.7B is featured)

### Technical Details
- **Always use HF paper links**: Replace arxiv.org links with huggingface.co/papers links (e.g., `https://huggingface.co/papers/2601.21337` instead of `https://arxiv.org/abs/2601.21337`)
- **Explain acronyms**: Define technical terms on first use (e.g., "Classifier-Free Guidance (CFG)" with brief explanation)
- **Follow template structure strictly**: Don't add sections like "Benchmarks" that aren't in the template—integrate all metrics into the "Why it's interesting" bullet points (2-4 bullets total)

### Final Publication
- **Markdown is the foundation**: The markdown file contains content only—images, GIFs, embedded demos, and other rich media are added during the publication process
