# Data-Mining
Data Mining project to develop various algorithms designed to predict delays in commercial flights
=======
# Predicció de retards de vols — Projecte de Mineria de Dades (MIDA)

Classificació binària: predir si un vol domèstic dels EUA (2023) arribarà endarrerit,
a partir de les dades del vol, de l'avió i de la meteorologia dels aeroports.

## Estructura del repositori

```
├── data/
│   ├── raw/         CSV originals de Kaggle (NO es pugen a GitHub)
│   ├── interim/     taules intermèdies generades pels notebooks (NO es pugen)
│   └── processed/   dades preprocessades finals (NO es pugen; s'entreguen a part)
├── notebooks/       un notebook per fase, numerats per ordre d'execució
├── docs/
│   ├── decisions.md registre de decisions i la seva justificació (base de la memòria)
│   └── qui_fa_que.md registre de feina per membre (taula "Who did what")
├── requirements.txt versions exactes de les llibreries
└── README.md
```

## Notebooks

| Notebook | Fase | Responsable |
|---|---|---|
| `01_auditoria_join.ipynb` | Comprensió de les dades i join vols + meteo | |
| `02_eda.ipynb` | Anàlisi exploratòria (només sobre el train) | |
| `03_preprocessing.ipynb` | Neteja, partició i pipeline | |
| `04_model_naive_bayes.ipynb` | Naive Bayes | |
| `04_model_knn.ipynb` | k-NN | |
| `04_model_arbre.ipynb` | Arbre de decisió | |
| `04_model_svm.ipynb` | SVM | |
| `04_model_ensembles.ipynb` | Voting, Bagging, Random Forest, AdaBoost | |
| `05_comparacio.ipynb` | Avaluació final, McNemar i intervals de confiança | |

## Posada en marxa (Windows, un cop per ordinador)

1. Instal·lar Python 3.13 (Python Install Manager de la Microsoft Store → `py install 3.13`)
   i Git (`winget install --id Git.Git -e --source winget`).
2. Clonar aquest repositori a `C:\MIDA`:
   ```powershell
   git clone https://github.com/USUARI/NOM-REPO.git C:\MIDA
   cd C:\MIDA
   ```
3. A PowerShell, dins de `C:\MIDA`:
   ```powershell
   py -3.13 -m venv .venv
   .venv\Scripts\Activate.ps1
   pip install -r requirements.txt
   ```
4. Descarregar el dataset de Kaggle i extreure els CSV a `data\raw\`:
   https://www.kaggle.com/datasets/bordanova/2023-us-civil-flights-delay-meteo-and-aircraft
5. Obrir Jupyter amb `jupyter lab` i executar els notebooks per ordre.

## Normes de treball

- **Abans de començar a treballar:** `git pull` per baixar els canvis dels altres.
- **Quan acabis una tasca:** `git status` → `git add <fitxers>` → `git commit -m "què has fet"` → `git push`.
- **Cada notebook té un responsable.** Si n'has de tocar un altre, avisa abans: dos canvis
  alhora al mateix notebook generen conflictes difícils de resoldre.
- **Les dades no es pugen mai** (ja ho impedeix el `.gitignore`).
- **Si instal·les una llibreria nova**, actualitza `requirements.txt` i avisa la resta perquè
  facin `pip install -r requirements.txt`. A PowerShell, genera'l així (amb `>` Windows
  PowerShell el desa en UTF-16 i Git el tracta com un fitxer binari):
  ```powershell
  pip freeze | Out-File -Encoding utf8 requirements.txt
  ```
- **Totes les decisions** (què eliminem, com imputem, quins paràmetres provem…) s'apunten a
  `docs/decisions.md` amb el seu perquè.
- **`random_state=42`** a tot arreu on hi hagi aleatorietat.
- Abans de l'entrega: *Kernel → Restart Kernel and Run All Cells* a cada notebook.
>>>>>>> f5d4284 (Estructura inicial del projecte)
