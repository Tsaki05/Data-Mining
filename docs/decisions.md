# Registre de decisions

Cada decisió del projecte, amb el seu perquè. És la base de les seccions de preprocessing
i d'avaluació de la memòria.

Estat: ✅ presa · ⏳ pendent · 🔁 revisada

| ID | Data | Decisió | Justificació | Temari | Estat |
|---|---|---|---|---|---|
| D01 | 2026-11-10 | Dataset: *US 2023 Civil Flights, delays, meteo and aircrafts* (Kaggle) | Aprovat pel professor. Més de 20 columnes i més de 1.000 files, amb dades heterogènies | Enunciat | ✅ |
| D02 | 2026-11-11 | Entorn: Python 3.13 local + entorn virtual + JupyterLab | JupyterLite (al navegador) té un límit de memòria de 2 GB i no pot carregar 6,7 M de files | — | ✅ |
| D03 | 2026-11-10 | Join vols + meteorologia per (aeroport, data), una vegada per a l'origen i una altra per a la destinació (left join, molts a un) | La meteorologia és diària per aeroport. Cal conservar una fila per vol | L2 (joins i granularitat) | ✅ |
| D04 | | Definició del target (proposta: `arr_delay ≥ 15` min) | Definició oficial del Departament de Transport dels EUA | T3 | ⏳ |
| D05 | | Moment de la predicció i ús de la meteorologia (del mateix dia o del dia anterior) | Determina quines variables són fuita de dades | T1 | ⏳ |
| D06 | | `deptime_label` i `flight_duration`: programades o reals? | Si són reals, són fuita de dades. Es comprova a `01_auditoria_join` | L1 | ⏳ |
| D07 | | Fer servir `airports_geolocation.csv` (distància exacta, estat) | Enriquiment del dataset | L2 | ⏳ |
| D08 | | Tipus de partició train/test (temporal, per dies o aleatòria) | Depèn de l'evolució temporal de la taxa de retard | T3 | ⏳ |
| D09 | | Mida de la mostra de treball | SVM i k-NN no són viables amb 6,7 M de files. Es justificarà amb una corba d'aprenentatge | L2 | ⏳ |
