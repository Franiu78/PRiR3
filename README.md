# PRiR3 - Temat 3 - Zadanie 1 

To rozwiazanie realizuje **Zadanie 1**: rownolegle przetwarzanie obrazu w Pythonie.

Program:
- wczytuje obraz,
- dzieli go na fragmenty,
- przetwarza kazdy fragment w osobnym procesie (`multiprocessing.Pool`),
- stosuje wlasna implementacje filtru krawedziowego Sobela (NumPy),
- scala wynik i zapisuje obraz wyjsciowy.

## Wymagania

- Python 3.9+
- biblioteki: `pillow`, `numpy`

## Instalacja

W katalogu projektu uruchom:

```bash
python -m pip install --upgrade pip
pip install pillow numpy
```

Jesli na Twoim systemie jest `python3`, uzyj:

```bash
python3 -m pip install --upgrade pip
python3 -m pip install pillow numpy
```

## Uruchomienie

Podstawowe:

```bash
python task1_parallel_image.py input.jpg output.png
```

Pelna wersja z parametrami:

```bash
python task1_parallel_image.py input.jpg output.png --workers 4 --fragments 8
```

Parametry:
- `input` - plik wejsciowy obrazu,
- `output` - plik wyjsciowy,
- `--workers` - liczba procesow w puli (domyslnie: liczba rdzeni CPU),
- `--fragments` - liczba fragmentow obrazu (domyslnie 0, czyli tyle co `workers`).

## Co jest zaimplementowane

- Podzial obrazu na poziome fragmenty.
- Rownolegle przetwarzanie fragmentow przez `Pool.map`.
- Wlasny filtr Sobela oparty o NumPy (bez gotowych funkcji filtrujacych).
- Scalanie fragmentow do jednego obrazu wynikowego.
