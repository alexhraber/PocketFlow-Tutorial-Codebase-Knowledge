# Tutorial: PocketFlow

PocketFlow is a *Python framework* for building modular workflows and AI agents.
It allows you to define complex processes by connecting individual **Nodes**, which represent *atomic tasks* like calling an LLM or searching the web.
A **Flow** then *orchestrates* these Nodes, guiding the execution sequence based on **Actions** (string identifiers) returned by each Node.
Data is passed between Nodes and managed throughout the workflow execution via a **Shared State** (a Python dictionary).
PocketFlow also offers advanced features like **Batch Processing** for efficiently handling collections of items, and **Asynchronous Processing** for non-blocking operations crucial for I/O-bound tasks.
Additionally, it demonstrates an **A2A (Agent-to-Agent) Communication Framework** to wrap PocketFlow agents, enabling them to communicate with other systems using a standardized JSON-RPC protocol.


**Source Repository:** [https://github.com/The-Pocket/PocketFlow](https://github.com/The-Pocket/PocketFlow)

```mermaid
flowchart TD
    A0["Node (`BaseNode`, `Node`, `AsyncNode`)
"]
    A1["Flow (`Flow`, `AsyncFlow`)
"]
    A2["Shared State (`shared` dictionary)
"]
    A3["Actions / Transitions
"]
    A4["Batch Processing (`BatchNode`, `BatchFlow`, `AsyncParallelBatchNode`)
"]
    A5["Asynchronous Processing (`AsyncNode`, `AsyncFlow`)
"]
    A6["A2A (Agent-to-Agent) Communication Framework
"]
    A1 -- "Orchestrates Nodes" --> A0
    A0 -- "Accesses Shared State" --> A2
    A0 -- "Returns Action" --> A3
    A1 -- "Uses Action for dispatch" --> A3
    A4 -- "Specializes Node (batch)" --> A0
    A4 -- "Specializes Flow (batch)" --> A1
    A5 -- "Specializes Node (async)" --> A0
    A5 -- "Specializes Flow (async)" --> A1
    A6 -- "Executes Flow" --> A1
    A6 -- "Initializes Shared State" --> A2
```

## Chapters

1. [Shared State (`shared` dictionary)
](01_shared_state___shared__dictionary__.md)
2. [Node (`BaseNode`, `Node`, `AsyncNode`)
](02_node___basenode____node____asyncnode___.md)
3. [Actions / Transitions
](03_actions___transitions_.md)
4. [Flow (`Flow`, `AsyncFlow`)
](04_flow___flow____asyncflow___.md)
5. [Asynchronous Processing (`AsyncNode`, `AsyncFlow`)
](05_asynchronous_processing___asyncnode____asyncflow___.md)
6. [Batch Processing (`BatchNode`, `BatchFlow`, `AsyncParallelBatchNode`)
](06_batch_processing___batchnode____batchflow____asyncparallelbatchnode___.md)
7. [A2A (Agent-to-Agent) Communication Framework
](07_a2a__agent_to_agent__communication_framework_.md)


---

Generated by [AI Codebase Knowledge Builder](https://github.com/The-Pocket/Tutorial-Codebase-Knowledge)