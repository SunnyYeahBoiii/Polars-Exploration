# Polar Exploration

This is the folder for storing my diary in polar exploration. 
All information is from [Polars's docs](https://docs.pola.rs/#key-features).

## Polar's Philosopy - Concept

The goal of Polars is to provide a lightning fast DataFrame library that:
- Utilizes all available cores on your machine - **Multithread**.
- Optimizes queries to reduce unneeded work/memory allocations - **Query Optimizer**.
- Handles datasets much larger than your available RAM.
- A consistent and predictable API - **Consistency**.
- Adheres to a strict schema (data-types should be known before running the query) - **Schema Driven**.

Polars is written in Rust which gives it C/C++ performance and allows it to fully control performance-critical parts in a query engine.

The above is the philosopy of Polars, which is quite interesting. In fact, for some reason, this kinda reminds me of SQL databases.

## Chapters
- [Getting Started](./Chapter%201%20-%20Getting%20Started/)
- [Concepts](./Chapter%202%20-%20Concepts/)