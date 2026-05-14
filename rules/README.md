# Rules

This directory contains independently versioned heuristic rule projects.

Each rule should live at:

```text
rules/<language>/<rule-name>
```

Use Git submodules for rule projects that have their own release cadence, tests, fixtures, or upstream history. The main Heuris repository should only own shared organization, documentation, replay conventions, and cross-rule integration.

To add another rule project:

```sh
git submodule add <repository-url> rules/<language>/<rule-name>
```
