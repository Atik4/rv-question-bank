# Prompt Template

```text
You are generating production-grade curriculum question banks.

Board: <BOARD>
Grade: <GRADE>
Subject: <SUBJECT>
Chapter: <CHAPTER>
Source Content: <BOOK CONTENT>
Count: <N>

Requirements:
1. Strictly follow repository schema.
2. Use textbook style wording.
3. Include options wherever relevant.
4. Include questionLatex for math/science.
5. Include structured answer object.
6. Cover concept variety.
7. No placeholders.
8. Output valid JSON only.
```

## Gemini Thinking Verification Prompt

```text
Review attached JSON question bank.
Check correctness, options, latex, schema compliance, duplicates, difficulty and marks.
Return corrected JSON only.
```
