# EDOCS — Podsumowanie eksperymentów

- Cel: modelowanie czasu życia narzędzi (regresja) na podstawie sygnałów i metadanych. Repozytorium obejmuje przygotowanie danych, inżynierię cech, porównania modeli klasycznych oraz prototypy sieci konwolucyjnych 1D.

Analiza i wykonane kroki
- Wczytanie danych: `Signals.npz` oraz `metadata_train.csv` i `metadata_test.csv`.
- Preprocessing i podział danych: przygotowanie zbiorów treningowych/testowych oraz ekstrakcja cech czasowych (segmentacja sygnału, statystyki, liczenie zmian, wartości ekstremalne, gęstości zmian itp.).
- Inżynieria cech: agregacje i cechy opisowe utworzone na podstawie sekwencji (np. `amount_*`, `density_*`, `num_of_*_changes`, `std_*`, `extreme_changes`).
- Modelowanie: porównanie modeli RandomForest, ExtraTrees, GradientBoosting, XGBoost, CatBoost, LightGBM; strojenie hiperparametrów przy użyciu GridSearchCV oraz ocena z wykorzystaniem cross-validation; tworzenie prostych ensemble (Voting/Stacking).
- Eksperymenty z sieciami konwolucyjnymi 1D: prototypowe implementacje w oddzielnych notatnikach.
- Ewaluacja: porównanie metryk na zbiorze testowym i wizualizacje wyników w notatnikach.

Główne wyniki (przykładowe, zaokrąglone)
- RandomForest (test R2) ≈ 0.79
- ExtraTrees (test R2) ≈ 0.83
- XGBoost / GBR (test R2) ≈ 0.83–0.84
- Ensemble (Voting) (test R2) ≈ 0.855–0.856
- Prototyp CNN 1D (test R2) ≈ 0.63

Główne pliki w repo
- `FOLDER ZGŁOSZENIOWY/podzial.ipynb` — preprocessing i podział danych
- `FOLDER ZGŁOSZENIOWY/scikit learn - 3VR.ipynb` — feature engineering i eksperymenty ze scikit-learn (funkcja `algorithm_pipeline`, GridSearchCV)
- `FOLDER ZGŁOSZENIOWY/Scikit _ best models.ipynb` — porównania i testy modeli
- `FOLDER ZGŁOSZENIOWY/1 WERSJA MODELU.ipynb`, `MULTIPLE CONVOLUTIONS.ipynb` — prototypy sieci konwolucyjnych
- `FOLDER ZGŁOSZENIOWY/Signals.npz`, `metadata_train.csv`, `metadata_test.csv` — dane wejściowe

Technologie i biblioteki
- Python (3.8+), numpy, pandas
- scikit-learn, xgboost, lightgbm, catboost
- tensorflow / keras (prototypy CNN 1D)
- matplotlib / seaborn

Zakres researchu
- Przetwarzanie sygnałów i inżynieria cech dla danych sekwencyjnych
- Strojenie modeli (GridSearchCV, cross-validation)
- Modele drzewiaste i boosting: XGBoost / LightGBM / CatBoost
- Budowa i testowanie prostych sieci konwolucyjnych 1D (Keras)
