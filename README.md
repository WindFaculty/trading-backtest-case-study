# Trading Backtest Platform Case Study

## Overview

Trading Backtest Platform is a local-first desktop platform for chart visualization, trading bot backtesting, strategy configuration, optimizer workflows, and performance-focused computation.

This repository is designed as a public case study. It documents the architecture, feature scope, performance direction, and lessons learned without requiring the private application source code to be public.

## Problem

Manual strategy testing is slow, inconsistent, and difficult to compare. Traders and developers need a repeatable way to test configurations, inspect chart behavior, and compare backtest results.

## Solution

The platform combines a React desktop UI, a Python workflow backend, SQLite local persistence, and a C++ compute layer for performance-critical backtest and optimizer work.

## Key Features

- Chart-focused workflow for reviewing trading data
- Backtest execution for comparing strategy configurations
- Strategy configuration flow for bot parameters
- Optimizer workflow for parameter search
- Local-first storage for project data and results
- C++ runtime path for compute-heavy operations

## Architecture

The system is organized around a local desktop workflow:

- React renders the main user interface and chart-oriented screens
- Python coordinates business workflows, file access, and API boundaries
- SQLite stores local configuration, runs, and result metadata
- C++ handles performance-critical computation used by backtests and optimizers

More detail is available in [architecture.md](architecture.md).

## Performance Optimization

The main optimization direction is to keep orchestration flexible in Python while moving repeated compute-heavy loops into C++.

The intended value is faster strategy comparison, more reliable optimizer runs, and a cleaner boundary between product workflow and numerical computation.

Benchmark notes are tracked in [benchmark.md](benchmark.md).

## Screenshots

Screenshots should be added after polished demo screens are exported:

- `screenshots/chart-page.png`
- `screenshots/optimizer-page.png`
- `screenshots/backtest-result.png`

## Technical Value

Python coordinates workflows, while C++ handles performance-critical computation. This gives the project room to stay productive during feature development while still supporting faster execution for heavy workloads.

## Business Value

The platform helps users research trading strategies faster and compare configurations more systematically.

## What I Learned

- How to design a local-first desktop workflow
- How to separate UI, orchestration, storage, and compute responsibilities
- How to document a private project through a public engineering case study
- How to think about performance boundaries before the system becomes too large

## Future Improvements

- Add polished screenshots and GIF demos
- Add benchmark tables from repeatable test scenarios
- Support multiple bot types
- Improve optimizer result comparison
- Add exportable reports for backtest runs
