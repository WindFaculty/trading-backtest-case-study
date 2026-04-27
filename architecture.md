# Architecture

## System Goal

The platform is built as a local-first trading research tool. It should make strategy configuration, backtest execution, chart inspection, and optimizer workflows feel connected inside one desktop environment.

## Main Components

### React UI

The UI handles chart screens, strategy forms, optimizer controls, and result views. It is responsible for making workflows easy to inspect and repeat.

### Python Backend

The Python layer coordinates application workflows, validates requests, prepares data for computation, and manages communication between the UI, storage, and compute layer.

### SQLite Storage

SQLite stores local project data such as strategy settings, backtest run metadata, optimizer configuration, and result references.

### C++ Compute Layer

The C++ layer is reserved for performance-critical work such as repeated backtest loops, optimizer calculations, and other computation-heavy routines.

## Data Flow

1. The user configures a strategy or optimizer run in the React UI.
2. The UI sends the request to the Python workflow layer.
3. Python validates and prepares data.
4. Python calls the C++ runtime for heavy computation when needed.
5. Results are stored locally and returned to the UI.
6. The UI renders charts, summaries, and comparison views.

## Design Direction

- Keep product workflow code readable and easy to change.
- Move expensive repeated calculations into the compute layer.
- Store enough metadata to make runs repeatable.
- Design result views around comparison, not just one-off execution.
