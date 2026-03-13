# Analiza Właściwości Elektrod Grafenowych w R 

##  Cel Projektu
Głównym celem tego projektu jest analiza danych eksperymentalnych dotyczących właściwości elektrod grafenowych. Projekt skupia się na identyfikacji kluczowych czynników fizykochemicznych i konfiguracyjnych, które mają największy wpływ na **pojemność właściwą** (`Capacitance (F/g)`) badanych materiałów.

##  Główne Wnioski
Zbudowany model uczenia maszynowego (XGBoost) posłużył do analizy ważności cech (Explainable AI / Feature Importance). Najważniejsze wnioski z analizy to:
* **Kluczowe predyktory:** Największy wpływ na pojemność właściwą mają `Potential Window (V)` oraz `Current Density (A/g)`. 
* **Wpływ konfiguracji:** Zmienna `Electrode Configuration` ma również wysoce istotne znaczenie dla końcowych osiągów elektrody.
* **Brak silnych korelacji:** Analiza macierzy korelacji wykazała brak silnych, bezpośrednich zależności liniowych pomiędzy zmiennymi numerycznymi w zbiorze, co uzasadnia użycie nieliniowych modeli (jak XGBoost).

##  Przetwarzanie Danych (Data Preprocessing)
Oryginalny zbiór danych przeszedł rygorystyczny proces czyszczenia, aby zapewnić wysoką jakość modelu:
1. **Redukcja wymiarowości:** Z początkowych 21 kolumn i 925 wierszy zbiór został zredukowany do 12 kolumn i 921 wierszy.
2. **Usuwanie braków:** Kolumny z brakami danych przekraczającymi 60% (głównie zmienne atomowe i linki do publikacji) oraz wiersze z więcej niż 4 brakami zostały usunięte.
3. **Imputacja:** * Braki w danych numerycznych zastąpiono **medianą**.
   * Braki w zmiennych kategorycznych oznaczono jako `"Unknown"`.

##  Wykorzystane Technologie i Biblioteki
Projekt został w całości zrealizowany w języku **R**, z wykorzystaniem środowiska R Markdown do generowania raportu HTML.

* **Przetwarzanie danych:** `dplyr`, `tidyr`, `stringr`, `tibble`
* **Wizualizacja:** `ggplot2`, `plotly` (wykresy interaktywne), `ggcorrplot`, `GGally`
* **Machine Learning & XAI:** `xgboost`, `caret`
* **Formatowanie raportu:** `knitr`, `kableExtra`

##  Jak uruchomić projekt lokalnie?

1. Sklonuj to repozytorium na swój dysk.
2. Upewnij się, że masz zainstalowane środowisko R oraz RStudio.
3. Plik z danymi (`data.csv`) powinien znajdować się w folderze `data/` w głównym katalogu projektu.
4. Zainstaluj wymagane biblioteki (jeśli ich nie posiadasz):
   ```R
   install.packages(c("dplyr", "tidyr", "stringr", "tibble", "ggplot2", "plotly", "GGally", "ggcorrplot", "knitr", "kableExtra", "caret", "xgboost", "here", "scales"))
