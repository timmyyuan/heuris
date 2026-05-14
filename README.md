Heuris is a replayable heuristic system for static analysis and evolving code rules. Instead of relying on heavyweight compiler pipelines, it extracts structural facts from source code and evaluates composable heuristics designed for continuous iteration, replayable analysis, and regression-driven rule evolution. Heuris focuses on fast developer feedback, explainable diagnostics, and maintainable static analysis across growing codebases and languages.

## Repository Layout

```text
heuris/
├── rules/
│   ├── README.md
│   └── go/
│       ├── README.md
│       └── prealloc/   # Git submodule
└── README.md
```

Rule projects live under `rules/<language>/<rule-name>`. These projects can stay independently versioned as Git submodules while Heuris keeps the higher-level structure, documentation, replay conventions, and cross-rule orchestration in the main repository.

`prealloc` is currently managed as the Go rule submodule at `rules/go/prealloc`.

## Inspiration

Heuris is inspired by [Learning Beyond Gradients](https://trinkle23897.github.io/learning-beyond-gradients/), especially its framing of heuristic systems as maintainable, replayable software structures that can improve through feedback, tests, and coding-agent iteration.
