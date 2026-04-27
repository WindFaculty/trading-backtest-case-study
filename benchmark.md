# Benchmark Notes

## Purpose

This file tracks performance goals and benchmark scenarios for the trading backtest platform.

## Benchmark Goals

- Compare Python-only execution against C++ accelerated execution.
- Measure optimizer runtime across different parameter ranges.
- Track chart/result loading time for realistic local datasets.
- Keep benchmark scenarios repeatable.

## Suggested Scenarios

| Scenario | Dataset Size | Strategy Type | Metric |
| --- | ---: | --- | --- |
| Single backtest | TBD | Grid bot | Runtime |
| Optimizer small range | TBD | Grid bot | Runtime and best result |
| Optimizer large range | TBD | Grid bot | Runtime and memory usage |
| Result loading | TBD | Any | UI load time |

## Current Status

Formal benchmark numbers are not published yet. Add numbers only after the test dataset, machine specs, and command path are stable enough to reproduce.

## Reporting Template

| Date | Machine | Dataset | Python Runtime | C++ Runtime | Notes |
| --- | --- | --- | ---: | ---: | --- |
| TBD | TBD | TBD | TBD | TBD | TBD |
