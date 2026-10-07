# RiddleMeThis

# Pattern Builder

> **A work in progress for creating custom Fabric-style LLM patterns through conversation.**

Pattern Builder is an experimental project for creating reusable LLM patterns by working with an AI model interactively.
Instead of writing a complex prompt from scratch, you describe what you want the pattern to accomplish and work with the model through a structured pattern-building process.
The model progressively develops the pattern with you, allowing you to review and modify each part before moving on to the final result.

## Acknowledgements

This project would not exist without the work of **Daniel Miessler** and the [Fabric](https://github.com/danielmiessler/fabric) project.
A huge thank you to Daniel for creating Fabric and for collecting, developing, and organizing the strategies and patterns that inspired this project.
Fabric demonstrates the value of treating prompts as reusable building blocks for AI workflows.
This project takes that idea in a different direction: instead of only using existing patterns, it focuses on **creating new patterns interactively and tailoring them to a specific use case**.

## What Is Pattern Builder?

Pattern Builder is a conversational system for creating **Fabric-style patterns for LLMs**.
The basic idea is:

Describe what you need
        ↓
Understand the use case
        ↓
Define the pattern's purpose
        ↓
Define the input
        ↓
Define the processing steps
        ↓
Define the output
        ↓
Select useful strategies
        ↓
Find matching existing patterns
        ↓
Combine or create a custom pattern
        ↓
Review and approve
        ↓
Final Pattern

Rather than trying to write the perfect prompt immediately, the builder lets you develop the prompt through a series of increasingly specific decisions.

## The Main Idea

The core idea behind Pattern Builder is simple:

> **Create a pattern that fits your needs instead of adapting your needs to an existing prompt.**

You start with an idea.

For example:

I need a pattern that analyzes technical documentation
and produces a security assessment.

The builder then helps turn that idea into a structured pattern.
You can correct the model whenever its interpretation is wrong, add requirements, remove unnecessary behavior, or completely change direction.
The final pattern is the result of that interaction.

## Using Pattern Builder with ChatGPT

One intended use case is **ChatGPT Projects**.

The basic workflow is:

1. Create a new ChatGPT Project.
2. Upload the Pattern Builder files.
3. Copy the project instructions into the Project Instructions field.
4. Start a conversation with the builder.
5. Describe the pattern you want to create.
6. Work through the individual stages.
7. Approve or modify each stage.
8. Select relevant strategies.
9. Review the final pattern.
10. Copy the resulting pattern and use it wherever you need it.

The same general concept can be adapted to other LLM interfaces that support system instructions and uploaded reference files.

## Starting the Builder

The intended activation phrase is:

FABRIC START


When the builder recognizes this activation, it begins the pattern-building workflow.

The project instructions define this trigger and instruct the model to load and follow the pattern-building workflow. 

If the trigger does not work, simply describe the pattern you want:

I need a pattern for analyzing technical documentation
and identifying security risks.

The builder can then be prompted to begin the process manually.

# How the Pattern-Building Process Works

The builder is intentionally divided into stages.

The purpose of the stages is to prevent the model from immediately jumping to a final prompt before the requirements have been properly defined.

## 1. Identity and Purpose

The first stage defines what the pattern is and what it is supposed to accomplish.

The builder establishes:

- The role of the model
- The expertise required
- The purpose of the pattern
- The problem it solves
- The expected input
- The transformation performed by the pattern

You can modify the proposed definition before continuing.

## 2. Input

The next stage defines how the pattern receives its input.
The builder keeps this section deliberately simple and separates the pattern's instructions from the data that will eventually be processed.

## 3. Steps

The third stage defines the actual processing pipeline.

For example:

1. Read the entire input.
2. Identify the main claims.
3. Classify the claims.
4. Evaluate supporting evidence.
5. Identify weaknesses.
6. Rank the findings.
7. Produce the final assessment.

The intention is to make the transformation explicit rather than leaving the model to determine the entire workflow implicitly.
The builder encourages concrete actions such as:

- Read
- Analyze
- Extract
- Identify
- Classify
- Compare
- Score
- Summarize
- Transform
- Validate
- Consolidate
- 
## 4. Output Instructions

The fourth stage defines what the final result should look like.
The output instructions are generated specifically for the pattern being created rather than simply applying the same generic output format to every task.
For example, a pattern might produce:

- A ranked list
- A table
- A report
- A structured assessment
- JSON
- Markdown sections
- A comparison
- A set of recommendations

The output requirements are therefore designed around the actual purpose of the pattern.

# Strategy Selection

After the core pattern has been defined, the builder can recommend strategies that may improve the result.

Strategies can also be combined.

Examples include:

standard
self-refine
reflexion
self-consistent
tree-of-thought
least-to-most

The strategy selection stage allows the user to choose whether a strategy should be applied and, where appropriate, combine multiple strategies.

For example:

Pattern
   +
Self-Refine
   ↓
Initial result
   ↓
Critique
   ↓
Improved result


The builder can also recommend a combination when the task benefits from multiple approaches.

# Using Fabric Patterns

A major part of the project is the ability to use existing Fabric patterns as references.
The repository contains Fabric-related reference material that allows the builder to identify patterns that may already be useful for a particular request.
For example, if you ask for a pattern involving summarization, analysis, extraction, comparison, or refinement, the builder can search the available Fabric patterns for something that already addresses part of the problem.
The goal is **not to reinvent an existing pattern unnecessarily**.
The builder can:

1. Find an existing pattern.
2. Explain why it is relevant.
3. Use it directly where appropriate.
4. Combine multiple patterns into a pipeline when necessary.
5. Create a new custom pattern when no suitable existing pattern exists.

# Combining Patterns

Some tasks are better solved by a sequence of patterns rather than one large pattern.
For example:

Input
  ↓
Extraction Pattern
  ↓
Analysis Pattern
  ↓
Refinement Pattern
  ↓
Final Output

The builder can treat these as separate stages rather than blindly merging all their instructions together.
This preserves the individual purpose of each pattern.

# Creating Custom Patterns

If an existing Fabric pattern or combination of patterns does not fit the requested use case, Pattern Builder can create a custom pattern.
The custom pattern is built from the requirements developed during the previous stages.
A custom pattern goes through the same review process as an existing pattern.
The user can modify the pattern before approving it.

# Approval and Versioning
The builder is designed so that important decisions are explicitly approved before continuing.
The normal interaction uses:

A — Approve and continue
B — Modify this section
C — Show alternatives
D — Other action

This allows you to gradually refine the pattern instead of accepting an automatically generated final prompt.
Complete pattern drafts are versioned:

Pattern Draft v1
Pattern Draft v2
Pattern Draft v3

This makes changes easier to track while experimenting with different approaches.

# Why This Approach?

Traditional prompt creation often looks like this:

Idea
 ↓
Write prompt
 ↓
Test prompt
 ↓
Rewrite prompt
 ↓
Test again
 ↓
Rewrite again

Pattern Builder attempts to make the process more structured:

Idea
 ↓
Clarify purpose
 ↓
Define input
 ↓
Define processing
 ↓
Define output
 ↓
Select strategies
 ↓
Compare existing patterns
 ↓
Build
 ↓
Review
 ↓
Approve

The goal is not to eliminate experimentation.
The goal is to make the experimentation more systematic.

# Fabric Relationship

Pattern Builder is **inspired by and built around concepts from Fabric**.
Fabric provides a large collection of reusable AI patterns and strategies. The official Fabric project describes patterns as reusable AI prompts organized around real-world tasks.
Pattern Builder focuses on a different problem:
> **How can we interactively create a new pattern that fits a particular use case?**
The projects are therefore complementary.
Fabric provides a large body of existing patterns and strategies.
Pattern Builder provides a conversational process for:

- Understanding a new requirement
- Selecting an existing pattern
- Combining patterns
- Selecting strategies
- Designing a custom pattern
- Reviewing the result

# Repository Structure

The repository deliberately separates the original Pattern Builder work from Fabric-related reference material.

pattern-builder/
│
├── README.md
├── LICENSE
├── NOTICE.md
│
├── builder/
│   │
│   ├── Project_Instructions.md
│   ├── instruction_setV2.md
│ 
│
├── fabric/
│   │
│   │
│   └── reference/
│       ├── 01_IDENTITY_and_PURPOSE.md
│       ├── 02_INPUT.md
│       ├── 03_STEPS.md
│       ├── 04_OUTPUT_INSTRUCTIONS.md
│       ├── Fabric_Pattern_Template_FULL.md
│       ├── Fabric_Strategies_Reference.md
│       ├── Fabric_Patterns_Catalog.md
│       └── Fabric_patterns.md
│


# Original Work vs. Fabric Material

The repository distinguishes between original Pattern Builder work and material originating from Fabric.

## Original Pattern Builder Work

This includes:

- The interactive pattern-building concept
- The conversational workflow
- The staged approval process
- Pattern draft versioning
- Input tracking
- Strategy selection workflow
- Pattern matching workflow
- Pattern pipeline workflow
- Custom pattern workflow
- Execution approval workflow
- Project-specific instructions
- Original documentation

## Fabric-Related Material

This includes:

- Fabric pattern templates
- Fabric pattern examples
- Fabric pattern catalog information
- Fabric strategy descriptions
- Fabric pattern collections
- Fabric-derived reference material

The separation is intended to make the origin of the material clear and preserve the appropriate attribution and licensing information.

# Third-Party Material

The Fabric project is currently released under the MIT License. Its upstream repository contains the applicable MIT license text and copyright notice.
Fabric-related files in this repository should therefore retain the applicable Fabric copyright and license information.
The Pattern Builder project does not claim ownership of Fabric's original material.
The `LICENSE` file at the root of this repository applies to **original Pattern Builder work**, while the `fabric/` directory contains separately identified Fabric-related material.

# Current Limitations

## Work in Progress

This project is experimental.
Do not expect perfect or deterministic behavior.
The Pattern Builder is itself controlled by an LLM, which means that the model can occasionally fail to follow the workflow exactly.

### `FABRIC START` Does Not Always Work

Although the project instructions define `FABRIC START` as the intended activation mechanism, the model does not always recognize or execute the trigger correctly.
If this happens, simply describe the pattern you want:

I need a pattern for analyzing technical documentation
and producing a security assessment.


## The Model May Skip Steps

The builder explicitly instructs the model not to skip stages.
However, LLMs can sometimes ignore instructions or jump ahead.
For example, the builder may occasionally attempt to generate a complete pattern before all stages have been approved.
If this happens, tell it:


You skipped a stage. Go back to the previous stage
and continue the pattern-building process from there.

## The Model May Not Follow Its Own Instructions

This is an inherent limitation of an LLM-based workflow.
The project attempts to reduce this behavior through:

- Explicit sequential instructions
- Approval gates
- State tracking
- Versioning
- Repeated constraints
- Explicit failure handling
- Pattern validation

Nevertheless, these mechanisms cannot guarantee perfect compliance.

# What This Project Is Not

Pattern Builder is not intended to be:

- A replacement for Fabric
- A new LLM
- A guarantee of prompt quality
- A deterministic prompt compiler
- A guarantee that generated patterns will work perfectly
- A replacement for testing generated patterns

Generated patterns should always be reviewed and tested for their intended use.

# Experimental Nature

The project is deliberately experimental.
The workflow will likely change as different models are tested and new approaches to interactive pattern creation are discovered.
Expect:

- Bugs
- Inconsistent model behavior
- Changes to the workflow
- Changes to the instructions
- Imperfect generated patterns
- Occasional skipped stages
- Different results between models
- Different results between conversations

# Contributing

Ideas, testing, improvements, and experimentation are welcome.

Useful contributions include:

- Improving the pattern-building workflow
- Improving the interaction model
- Finding ways to reduce skipped stages
- Improving pattern validation
- Developing better pattern-selection methods
- Testing different LLMs
- Creating examples
- Documenting successful workflows
- Identifying failure modes

If you find a case where the builder behaves unexpectedly, documenting the exact interaction is especially useful.

# Credits

## Daniel Miessler / Fabric

Special thanks to **Daniel Miessler** for creating Fabric and for developing and collecting the patterns and strategies that inspired this project.
Fabric was created by Daniel Miessler in January 2024 and remains an independent open-source project.
[Fabric GitHub Repository](https://github.com/danielmiessler/fabric?utm_source=chatgpt.com)

# License

## Pattern Builder

Original Pattern Builder work in this repository is released under the:

**MIT License**

See `LICENSE`.

The MIT license applies to original work created for this project.

## Fabric

Fabric-related material is identified separately in the `fabric/` directory.
Fabric is also licensed under the MIT License according to its current upstream repository. The applicable Fabric copyright and license notices should be retained with that material.

See:

`fabric/LICENSE`

for the applicable license text.

## Important

The presence of an MIT license at the repository level does not mean that all material in the repository was originally authored by the Pattern Builder project.
Third-party material remains attributed to its original authors.



# Disclaimer

This project is provided as an experimental open-source project.
Generated patterns and LLM outputs should be reviewed before being used in production, security-sensitive, business-critical, or otherwise consequential situations.

## Project Status

**Work in Progress**

The project is functional enough for experimentation, but it is not considered finished.
The primary goal at this stage is to explore whether conversational, staged pattern construction can make the creation of reusable LLM patterns easier, more precise, and more accessible.

**Expect experimentation.**


