# C# & Software Engineering Field Guide Quiz

A single-page quiz app with 441 multiple-choice questions for refreshing C#, .NET and general software engineering fundamentals. It accompanies the *C# & Software Engineering Field Guide* PDF, and each topic matches a chapter area of that guide.

After you answer a question, the app shows the correct option in green, marks your pick if it was wrong, tags the remaining options as wrong, and explains why.

## Live demo

**https://cezarpedroso.github.io/developer-study-guide/**

There is nothing to install. Open the link in any browser, on a phone or a computer.

## Features

- 441 questions across 17 topics, with an explanation for every question
- Choose the topics and the round length (10, 25, 50, 100 or all questions)
- Questions and answer order are shuffled on every round
- Right and wrong options are revealed immediately after each answer
- Keyboard support: `1`-`4` or `A`-`D` to answer, `Enter` to continue
- Results screen with an overall score, a per-topic breakdown and the questions you missed
- **Retry missed** to replay the questions from the round you just finished
- **Drill my misses** to practice every question you have missed before, saved in your browser until you answer it correctly
- Light and dark themes that follow your system setting
- Works on phones and desktops

## Topics

| Topic | Questions |
| --- | --- |
| .NET Basics | 25 |
| C# Fundamentals | 27 |
| OOP | 24 |
| Modern C# | 24 |
| LINQ | 26 |
| Async & Concurrency | 25 |
| Memory & Performance | 22 |
| ASP.NET Core | 29 |
| SQL & EF Core | 29 |
| SOLID & Architecture | 26 |
| Design Patterns | 29 |
| Testing | 20 |
| System Design | 30 |
| Security | 27 |
| DevOps | 26 |
| React & TypeScript | 28 |
| Algorithms | 24 |
| **Total** | **441** |

## How it works

Everything lives in one HTML file: the markup, styles, script and question bank. Fonts are the only external resource (Google Fonts), and the app falls back to system fonts if they cannot load.

Your preferences (selected topics, round length) and the IDs of questions you have missed are stored in the browser's `localStorage` under the key `fieldguide-quiz-v1`. Nothing is sent anywhere. Clearing site data resets your saved misses.

## Adding or editing questions

The question bank is the `DATA` object near the top of the `<script>` block in `index.html`. Each topic is a key that maps to a list of questions, and each question is an array of six strings:

```js
[
  "Question text. Use `backticks` for inline code.",
  "The correct answer",
  "Wrong answer 1",
  "Wrong answer 2",
  "Wrong answer 3",
  "Explanation shown after answering."
]
```

The correct answer is always written first. The app shuffles the four options when it displays the question, so you do not need to randomize them yourself. Add a new key to `DATA` to create a new topic, and it will appear in the topic picker automatically.

## Repository contents

| File | Description |
| --- | --- |
| `index.html` | The quiz app |
| `README.md` | This file |
| `CSharp_Field_Guide.pdf` | The Study Guide |

## Study tips

- Answer first, then read the explanation, even when you were right.
- Use **Drill my misses** a day or two after a round. Spaced repetition works better than rereading.
- Say the answer out loud before you click, as if an interviewer had asked.
