# Titolo della Tesi

**Analysis of Air Quality in the Urban Area of Turin: Focus on Nitrogen Oxides and Particulate Matter**

Master’s Degree Thesis in Physics of Complex Systems (A.Y. 2023/2024)

---

## Descrizione

Questo repository contiene il codice e la documentazione associati alla mia tesi di laurea magistrale, svolta sotto la supervisione dei Prof. Sofia Fellini e Luca Ridolfi. L'obiettivo dello studio è analizzare la qualità dell'aria nell’area urbana di Torino dal 2000 al 2022, con un focus su:

* Ossidi di azoto (NO, NO₂, NOₓ)
* Particolato (PM10, PM2.5)

Il lavoro comprende:

* **Estrazione e pulizia** dei database ARPA Piemonte
* **Analisi di copertura** e **gap analysis** delle serie temporali
* **Analisi statistica** (trend lineari e scomposizione stagionale con STL)
* **Confronto** tra diverse metodologie di misura di PM
* **Prova preliminare** di simulazione con il modello SIRANE

---

## Struttura del repository

```
tesi/
├── docs/            # Documentazione e PDF della tesi
│   └── tesi.pdf
├── src/             # Codice sorgente
│   ├── data/        # Script per preprocessing e caricamento dati
│   ├── analysis/    # Script per analisi statistiche e visualizzazioni
│   ├── models/      # Esempi di utilizzo del modello SIRANE
│   └── utils/       # Funzioni di utilità generale
├── data/            # Dati di esempio (campioni ridotti)
│   └── sample.csv
├── results/         # Output: grafici, tabelle, report
├── .gitignore       # File da ignorare (dati grezzi, ambienti virtuali, ecc.)
└── README.md        # Descrizione del progetto
```

---

## Prerequisiti

* Python 3.8+
* Pacchetti Python (installabili con `pip`):

  ```bash
  pip install -r requirements.txt
  ```

---

## Dati

I dataset completi non sono inclusi nel repository a causa delle loro dimensioni. Per riprodurre l'analisi:

1. Scarica i dati da ARPA Piemonte: [https://aria.ambiente.piemonte.it/#/qualita-aria/dati](https://aria.ambiente.piemonte.it/#/qualita-aria/dati)
2. Posiziona i file CSV in `src/data/raw/`

*Note:*

* `data/raw/` è ignorata da Git e contiene i dati grezzi.
* In `data/processed/` sono presenti piccoli campioni di dati per testare il codice.

---

## Esempio di esecuzione

```bash
# Pulizia dati
python src/data/preprocess.py --input src/data/raw/ --output src/data/processed/

# Copertura e gap analysis
python src/analysis/coverage_analysis.py --data src/data/processed/

# Trend analysis e visualizzazioni
python src/analysis/trend_analysis.py --data src/data/processed/ --output results/

# Simulazione SIRANE
python src/models/run_sirane.py --config src/models/config.toml
```

---

## Autore

Pierpaolo Careddu – [pier.car.pier@gmail.com](mailto:pier.car.pier@gmail.com)

Per domande o contributi, apri una *issue* o invia una *pull request*.

