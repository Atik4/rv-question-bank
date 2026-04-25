# Question Template Schema

```json
{
  "board": "ICSE",
  "grade": 10,
  "subject": "Mathematics",
  "chapter": "Quadratic Equations",
  "familyId": "solve_factorisation",
  "questionTemplate": "Solve: x² - {a}x + {b} = 0",
  "questionLatexTemplate": "\\text{Solve: } x^2-{a}x+{b}=0",
  "variables": {
    "a": {"type":"number","min":1,"max":20},
    "b": {"type":"number","min":1,"max":100}
  },
  "answerRule": "roots from factors of b summing to a",
  "optionStrategy": ["sign_error","swap_root","single_root"],
  "difficultyBase": 30,
  "marks": 2,
  "isActive": true
}
```

## Variable Types

* number
* choice
* derived

## Rules

Templates must generate only schema-compliant questions.
