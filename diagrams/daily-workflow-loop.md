# Diagram: The Daily Workflow Loop

The repeating cycle covered in the [cheat sheet](../cheatsheet/git-github-cheatsheet.md) and [example walkthrough](../examples/01-daily-workflow.md).

```mermaid
flowchart TD
    A["git pull"] --> B["git checkout -b feature/name"]
    B --> C["Make changes"]
    C --> D["git add ."]
    D --> E["git commit -m '...'"]
    E --> F["git push origin feature/name"]
    F --> G["Open Pull Request"]
    G --> H{"Review feedback?"}
    H -- "Changes requested" --> C
    H -- "Approved" --> I["Merge"]
    I --> J["Delete branch"]
    J --> A
```

Every step supports one goal: keep work isolated, traceable, and mergeable. If a step gets skipped — especially the pull at the start or the review before merge — this is usually where problems start.
