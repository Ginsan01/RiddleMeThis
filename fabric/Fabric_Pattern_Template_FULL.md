# SECTION: IDENTITY and PURPOSE

## Template

```
# IDENTITY and PURPOSE

You are a/an [ROLE/EXPERTISE, e.g. "expert threat intelligence analyst", "senior technical writer", "master extractor of insights and ideas"].

[1-3 sentences describing the specific mission of this pattern: what problem it solves, what kind of input it expects, and what transformation it performs on that input.]

Take a step back and think step-by-step about how to achieve the best possible result by following the steps below.
```

## Notes
- Always written in second person ("You are...") to anchor the model's role.
- Keep it tight: 3-6 sentences max before moving to STEPS.
- End with a "step back and think step-by-step" cue — this is a near-universal closing line across official Fabric patterns.
- This section carries more weight than the user message in Fabric's design philosophy, since the system prompt is treated as the primary instruction channel.

## Real Example (extract_wisdom)
"You extract surprising, insightful, and interesting information from text content. You are interested in insights related to the purpose and meaning of life, human flourishing, the role of technology in the future of humanity, artificial intelligence and its affect on humans, memes, learning, reading, books, continuous improvement, and similar topics."


---

# SECTION: STEPS

## Template

```
# STEPS

- [First action: usually "Read/analyze the entire input" or similar intake instruction.]

- [Second action: identify/extract/classify a specific element, e.g. "Extract the top 5-10 IDEAS discussed."]

- [Third action: process or transform the extracted element further, e.g. "From the IDEAS, extract the most surprising or insightful ones into INSIGHTS."]

- [Continue numbered/bulleted actions in strict sequential order — Fabric patterns almost always process input in a fixed pipeline, not conditionally.]

- [Final action: usually a consolidation or validation step before output, e.g. "Combine similar points and remove duplicates."]
```

## Notes
- Steps are always ordered and explicit — avoid vague verbs like "consider" or "think about"; use "extract," "list," "classify," "score."
- Many official patterns specify exact counts and word limits per item (e.g. "Extract 10-20 IDEAS in 15-word bullets") — include quantity/length constraints wherever relevant.
- Steps should map 1:1 to the section headers that will appear in OUTPUT INSTRUCTIONS.

## Real Example (extract_wisdom)
"Extract 20 to 50 of the most surprising, insightful, and/or interesting ideas from the input in a section called IDEAS:. If there are less than 50 then collect all of them. Make sure you extract at least 20."


---

# SECTION: OUTPUT INSTRUCTIONS

## Template

```
# OUTPUT INSTRUCTIONS

- Only output Markdown.

- All sections should be Markdown headers (e.g. "## IDEAS") with content below as bullet points, not numbered lists.

- Each bullet should be no more than [N] words.

- Do not give warnings, notes, or explanations of what you're doing — only output the requested sections.

- Do not repeat ideas, quotes, facts, or resources across sections.

- Do not start items with the same opening word.

- Ensure you follow ALL these instructions when creating your output.
```

## Notes
- This is the strictest, most rule-heavy section — Fabric patterns rely on repetition and explicit negatives ("Do not...") to reduce model drift.
- Formatting rules (Markdown-only, bullet vs numbered, word caps) are near-universal across all 200+ official patterns.
- Always ends with a reinforcement line demanding full compliance — this measurably reduces instruction-skipping in longer outputs.

## Real Example (extract_wisdom)
"You only output Markdown. Do not output the markdown code, only the content. Do not use bold or italics formatting in the markdown output. Do not output warnings or notes—just the requested sections."


---

# SECTION: INPUT

## Template

```
# INPUT:

INPUT:
```

## Notes
- This is intentionally minimal — just a header and a repeated "INPUT:" marker.
- It acts as the seam where Fabric appends whatever content is piped in via stdin, --file, -u (URL), or -y (YouTube transcript).
- Never add instructions after this marker; everything after it is treated as raw data, not directives.
- Some community patterns omit the duplicate line and use only "INPUT:" once — either form works, but the official template uses both a header and the marker line.
