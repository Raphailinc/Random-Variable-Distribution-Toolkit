# Random Variable Distribution Toolkit

Генерация и анализ распределения случайной величины вида `X = asin(sqrt(U/2))`, где `U ~ U(0, 1)`. Есть два генератора равномерных чисел: стандартный NumPy и детерминированный middle-square. Поддерживается расчёт хи-квадрат статистики и (при наличии SciPy) p-value.

## Быстрый старт
```bash
python -m venv .venv
. .venv/bin/activate
pip install -r requirements.txt
python -m random_variable_distribution -n 5000 -b 14 -g numpy --seed 42
```

Пример вывода:
```
Generator: numpy
Samples: 5000, bins: 14
Mean: 0.497506, Std: 0.187628
Chi-square: 8.1487, p-value: 0.8338
First 8 samples: 0.671391, 0.487528, 0.714459, 0.631672, 0.218739, 0.773208, 0.664802, 0.677597
Bin counts (observed): 32, 84, 159, 210, 286, 348, 390, 400, 465, 510, 500, 520, 556, 540
Bin counts (expected): 31.4, 93.9, 155.2, 214.6, 271.2, 324.5, 373.6, 418.1, 457.3, 490.7, 518.0, 538.8, 552.8, 559.8
```

## Основные функции
- `generate_uniform(size, method="numpy", seed=None, k=8)`: равномерные числа (`method` — `numpy` или `middle-square`).
- `transform_sample(uniforms)`: применяет обратную функцию `asin(sqrt(u/2))`.
- `expected_probabilities(num_bins)`: теоретические вероятности по интервалам на `[0, π/4]`.
- `analyze_distribution(...)`: полный цикл генерации, биннинга и расчёта хи-квадрат; возвращает `SampleSummary` с chi-square, p-value, средним и σ.

Запуск как модуля: `python -m random_variable_distribution --help`.

## Тесты
```bash
pytest
```

## Идеи развития
- Добавить больше генераторов (LCG, криптографический).
- Вывести результаты в CSV/JSON.
- CLI-опция для сохранения гистограмм.
