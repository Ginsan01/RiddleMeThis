# Fabric Prompt Strategies Reference

Detailed, LLM-readable descriptions of all Fabric strategies. Each strategy is a JSON meta-prompt stored in `~/.config/fabric/strategies/` that layers on top of a pattern's existing system prompt via the `--strategy` flag, without replacing the pattern's core IDENTITY/STEPS/OUTPUT INSTRUCTIONS.

---

## cot (Chain-of-Thought)

Before producing any final answer, generate an explicit, ordered sequence of intermediate reasoning steps that connect the input to the conclusion. Each step must logically follow from the previous one. Do not skip steps or jump to conclusions; surface the reasoning trace itself as part of the process, then output the final answer only after the full chain is complete.

**Usage:** `echo "input" | fabric --strategy cot -p pattern_name`

---

## cod (Chain-of-Draft)

Produce reasoning as a series of extremely terse draft notes, capped at roughly five words per step, instead of full sentences. Each draft step should capture only the essential state or transformation needed to move toward the answer. This minimizes token overhead while preserving a step-by-step reasoning skeleton.

**Usage:** `echo "input" | fabric --strategy cod -p pattern_name`

---

## tot (Tree-of-Thought)

Generate multiple distinct reasoning paths (branches) for solving the same problem in parallel, rather than committing to one linear chain. Evaluate each branch's plausibility or correctness at each depth level, prune weak branches, and expand promising ones. Select the final answer from the branch that reaches the most coherent, well-supported conclusion.

**Usage:** `echo "input" | fabric --strategy tot -p pattern_name`

---

## aot (Atom-of-Thought)

Decompose the problem into the smallest possible independent sub-problems ("atoms") that have no interdependencies. Solve each atomic unit separately and in isolation, then recombine the atomic solutions into a final composite answer. This reduces compounding errors that occur in long sequential chains.

**Usage:** `echo "input" | fabric --strategy aot -p pattern_name`

---

## ltm (Least-to-Most)

Order sub-problems by increasing difficulty. Solve the simplest sub-problem first, then use that solution as additional context/input when solving the next-hardest sub-problem, continuing until the most complex sub-problem is solved last, using all prior partial answers as scaffolding.

**Usage:** `echo "input" | fabric --strategy ltm -p pattern_name`

---

## self-consistent

Independently generate multiple full reasoning paths (using varied sampling) for the same question. Compare the final answers produced by each path and select the answer that appears most frequently (majority vote/consensus), discarding outlier reasoning paths that diverge from the consensus.

**Usage:** `echo "input" | fabric --strategy self-consistent -p pattern_name`

---

## self-refine

Generate an initial candidate answer. Then, acting as a critic, evaluate that answer for errors, omissions, or weaknesses. Using the critique, generate a revised answer that explicitly addresses the identified issues. Output only the refined version, not the original draft or the critique itself, unless asked.

**Usage:** `echo "input" | fabric --strategy self-refine -p pattern_name`

---

## reflexion

Generate an initial answer, then produce a brief self-critique identifying specific shortcomings (factual errors, missing context, unclear structure). Use that critique as feedback to generate one improved final answer. Unlike self-refine, reflexion typically limits this to a single critique-revise cycle rather than iterating repeatedly.

**Usage:** `echo "input" | fabric --strategy reflexion -p pattern_name`

---

## standard

Answer the input directly using the pattern's base instructions with no additional reasoning scaffold, meta-prompt, or multi-step decomposition layered on top. This is the default/no-strategy behavior.

**Usage:** `echo "input" | fabric --strategy standard -p pattern_name`

---

## Management Commands

- List installed strategies: `fabric --liststrategies`
- Install/select strategies interactively: `fabric --setup`
