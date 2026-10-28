# Random Variable Distribution Toolkit

[![CI](https://github.com/Raphailinc/Random-Variable-Distribution-Toolkit/actions/workflows/ci.yml/badge.svg)](https://github.com/Raphailinc/Random-Variable-Distribution-Toolkit/actions/workflows/ci.yml)

[English](README.md) · [Русский](README.ru.md)

A probability learning project for the transformed variable `X = asin(sqrt(U / 2))`, where `U` is uniform on `[0, 1)`.

## What it does

- Generate seeded samples and apply the inverse transformation.
- Compare observed bin frequencies with theoretical probabilities.
- Report sample summaries and chi-square statistics.

## Run locally

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python -m random_variable_distribution -n 5000 -b 14 -g numpy --seed 42
```

## Checks

```bash
python -m pytest
```

## Scope and implementation notes

The transformed support is `[0, π/4]`. NumPy and middle-square paths are provided for comparison; the latter is an educational generator.
