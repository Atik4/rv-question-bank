# Question Schema

## Required Fields

```json
{
  "board": "ICSE",
  "grade": 10,
  "subject": "Mathematics",
  "chapter": "Quadratic Equations",
  "topic": "Factorisation",
  "familyId": "solve_factorisation",
  "questionText": "Solve: x² - 16 = 0",
  "questionLatex": "\\text{Solve: } x^2-16=0",
  "options": [],
  "answer": {},
  "difficultyScore": 22,
  "difficultyLabel": "easy",
  "marks": 2,
  "sourceType": "book_curated"
}
```

## difficultyLabel enum

* easy
* medium
* hard

## sourceType enum

* book_curated
* template_generated
* teacher_created

## answer.type enum

* numeric
* text
* choice
* multi_value
* expression
* rubric

## If options present

* correctOptionIndex required

## Math Chapters

questionLatex mandatory.
