# Diagram: Merge Conflict Resolution Flow

The decision process from [Exercise 2](../exercises/02-simulate-a-merge-conflict/README.md) and the [worked example](../examples/04-resolving-a-merge-conflict.md), as a flowchart.

```mermaid
flowchart TD
    A["Conflict detected"] --> B["git status<br/>(see which files)"]
    B --> C["Open the conflicted file"]
    C --> D["Read both versions<br/>between the markers"]
    D --> E{"Do you understand<br/>both changes?"}
    E -- "No" --> F["Ask the person<br/>who wrote the other change"]
    F --> D
    E -- "Yes" --> G{"Which is correct?"}
    G -- "Keep yours" --> H["Remove markers,<br/>keep your version"]
    G -- "Keep theirs" --> I["Remove markers,<br/>keep their version"]
    G -- "Combine both" --> J["Remove markers,<br/>write the merged version"]
    H --> K["git add filename"]
    I --> K
    J --> K
    K --> L["Test before committing"]
    L --> M["git commit"]
```

The one rule that matters most here: never guess. If you don't understand both sides of the conflict, that's a two-minute conversation, not a coin flip.
