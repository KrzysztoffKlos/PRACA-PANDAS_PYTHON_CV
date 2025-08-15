Praca w Pythonie rozszerzenie PANDAS            Krótka analiza danych

Praca polega na analizie danych samochodowych. 
Dane pochodzą z Kaggle: [Automobile Dataset](https://www.kaggle.com/datasets/tawfikelmetwally/automobile-dataset).  

Celem projektu było:
 zapoznanie się ze strukturą danych,
 obliczenie podstawowych statystyk opisowych,
 eksploracja kolumn liczbowych (np. `horsepower`, `weight`, `displacement`),
 analiza występowania marek w kolumnie `name` z prostymi regułami filtrującymi.

 Technologie
 Python 3.x
 Pandas
 NumPy
 KaggleHub (do pobrania danych)


Struktura projektu
 `PRACA_DO_CV.ipynb` → notebook z wynikami,
 `PRACA_DO_CV.py` → wersja skryptowa,
 `README.md` → opis projektu.

W notebooku zostały wykonane następujące kroki:
1. Wczytanie danych z Kaggle i podgląd pierwszych rekordów.  
2. Sprawdzenie struktury danych:
    nazwy kolumn (`df.columns`),
    liczba wierszy i kolumn (`df.shape`),
    typy danych (`df.dtypes`).
3. Statystyki opisowe:
    średnia, minimum, maksimum, mediana,
    agregacje dla `horsepower` i `displacement`,
    opis zbiorczy (`df.describe()`).
4. Eksploracja danych jakościowych:
    zliczenie liczby wystąpień modeli (`df['name'].value_counts()`),
    analiza aut marek „ford” i „toyota” z określonymi warunkami.
5. Wnioski – które marki i parametry samochodów wyróżniają się w danych.



 Przykładowe wyniki
 Największa wartość `horsepower` w zbiorze: 230  
 Najcięższy samochód (`weight`): 5140  
 Najczęściej występujące modele to samochody marek ford i chevrolet.  


 KOD uruchomienia>

import pandas as pd
from pathlib import Path
import kagglehub

csv_file = Path("data/Automobile.csv")

if not csv_file.exists():
    path = kagglehub.dataset_download("tawfikelmetwally/automobile-dataset")
    csv_file = Path(path) / "Automobile.csv"

df = pd.read_csv(csv_file)


