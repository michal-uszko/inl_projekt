# Ekstrakcja informacji z raportów finansowych z wykorzystaniem wyspecjalizowanego NER'a

## Zawartość 
W repozytorium umieszczono zarówno pliki z wytrenowanymi modelami (folder `output/`), jak i przetworzone
do treningu dane (`train_text_chunks_preprocessed.csv` oraz `val_text_chunks_preprocessed.csv`).

Oprócz nich znajduje się również notebook `main_notebook.ipynb` z całą logiką.

## Korzystanie z zawartości
Jeżeli chcemy tylko sprawdzić obecny model, należy załadować model przy pomocy linijki kodu `ner_custom = spacy.load(r"./output/model-best")` (sekcja **Wczytanie modelu i test na prostym zdaniu**). Aby przetestować model na całym dokumencie, należy uruchomić kod z sekcji **Test na całym dokumencie ze zbioru testowego**.

Jeżeli chcemy wytrenować model, możemy to zrobić z wykorzystaniem zapisanych danych `train_text_chunks_preprocessed.csv` oraz `val_text_chunks_preprocessed.csv` oraz pliku `base_config_pl_core.cfg`. W tym celu służy sekcja `Treningowy pipeline customowego NER'a`.  
  
WAŻNE: W notebooku nie ma kodu wczytującego przetworzone dane bezpośrednio z plików, przetwarzanie odbywa się w kodzie. Aby nie powtarzać czynności przetwarzania danych, należy więc dopisać kod wczytujące dane z CSV (np. `pd.read_csv(train_text_chunks_preprocessed.csv, sep=';')`)

## Dane
Dane do modelu pochodzą z zadania PolEval 4 2020. LINK: http://2020.poleval.pl/tasks/task4/