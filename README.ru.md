# Random Variable Distribution Toolkit

[![CI](https://github.com/Raphailinc/Random-Variable-Distribution-Toolkit/actions/workflows/ci.yml/badge.svg)](https://github.com/Raphailinc/Random-Variable-Distribution-Toolkit/actions/workflows/ci.yml)

[English](README.md) · [Русский](README.ru.md)

Учебный проект теории вероятностей для X = asin(sqrt(U / 2)), где U равномерна на [0, 1).

## Возможности

- Генерация выборок с seed и применение обратного преобразования.
- Сравнение наблюдаемых частот с теоретическими вероятностями интервалов.
- Вывод сводных характеристик и статистики хи-квадрат.

## Локальный запуск

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python -m random_variable_distribution -n 5000 -b 14 -g numpy --seed 42
```

## Проверки

```bash
python -m pytest
```

## Условия запуска и границы проекта

Носитель преобразованной величины — [0, π/4]. NumPy и метод середины квадратов доступны для сравнения; второй генератор предназначен для обучения.
