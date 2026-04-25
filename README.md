# README.md

## RV Question Bank

Central repository for storing curriculum-aligned question banks for multiple boards, grades, and subjects.

### Purpose

* Maintain high-quality structured questions in one standard schema.
* Enable paper generation, practice tests, MCQs, subjective questions, and analytics.
* Build reusable content assets from textbooks and curriculum sources.

### Core Principles

1. Strict schema consistency across all files.
2. Quality over quantity.
3. Textbook alignment.
4. Every math answer must be validated.
5. Questions should support future reuse (MCQ, subjective, worksheets, adaptive learning).

### Recommended Structure

```text
rv-question-bank/
  README.md
  SOP.md
  PROMPT_TEMPLATE.md
  icse/
    class10/
      mathematics/
        quadratic-equations.json
        value-added-tax.json
  cbse/
    class10/
      mathematics/
```

### Mandatory Schema Rule

All generated questions must strictly follow the approved schema used in this repository. No custom fields unless explicitly approved.

### Quality Gate

Draft with LLM -> Verify with Gemini Thinking -> Human review -> Commit

---

# SOP.md

## Standard Operating Procedure for Adding New Chapters

### Step 1: Collect Source Content

Use chapter PDFs, textbook scans, exercise pages, examples, solved questions.

### Step 2: Understand the Chapter

Identify:

* key concepts
* exercise types
* repeated problem patterns
* board style wording
* difficulty spread

### Step 3: Use ChatGPT to Generate Questions

Use PROMPT_TEMPLATE.md.
Generate questions only in approved schema.

### Step 4: Verify with Gemini Thinking Model (Mandatory)

Check:

* correctness of answers
* option quality
* no duplicate roots/sign errors
* proper LaTeX formatting
* marks and difficulty reasonable
* wording clarity

### Step 5: Human Spot Check

Review at least 10 random questions per file.

### Step 6: Save in Correct Path

Example:

```text
icse/class10/mathematics/quadratic-equations.json
```

### Step 7: Commit Naming Convention

```text
a dd ICSE Class 10 Quadratic Equations question bank
```

### Non-Negotiables

* No placeholder questions
* No sample/dummy content
* No schema drift
* No unchecked math answers
* No low-quality distractors

---

# PROMPT_TEMPLATE.md

## Master Prompt for ChatGPT / LLM Contributors

Use the following prompt:

```text
You are generating production-grade curriculum question banks.

Board: <BOARD>
Class: <GRADE>
Subject: <SUBJECT>
Chapter: <CHAPTER>
Source Content: <PASTE BOOK CONTENT / IMAGES / OCR TEXT>

Requirements:
1. Generate <N> high-quality questions based on textbook style.
2. Cover all important concepts and exercises.
3. Use only the approved repository schema.
4. Include options for all questions where possible.
5. Include questionText and questionLatex for math/science.
6. Include structured answer object.
7. Difficulty score + label.
8. Recommended marks.
9. No placeholder content.
10. Ensure authentic board-style wording.

Output only valid JSON array.
```

## Mandatory Second Pass Prompt (Gemini Thinking)

```text
Review the attached JSON question bank thoroughly.
Check each question for:
1. Mathematical correctness
2. Correct options / correctOptionIndex
3. Wrong sign / factorisation mistakes
4. Duplicate or weak distractors
5. Schema consistency
6. Difficulty and marks alignment
7. LaTeX correctness
8. Board-level quality

Return corrected JSON only.
```

## Final Rule

If ChatGPT and Gemini disagree on an answer, manually re-solve before committing.
