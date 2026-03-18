# Behavioral Health Informatics — Parkinson's Disease Detection

Description
Behavioral Health Informatics project for PD (Parkinson's Disease) vs non-PD classification using smartwatch data (motion sensors) and clinical questionnaires. The goal is to identify predictive digital biomarkers using machine learning techniques (Random Forest) and interpretability methods (SHAP).


Which smartwatch-derived digital biomarkers are most predictive of Parkinson disease?



feature iniziali→missing filter→correlation filter→39→ANOVA + MI ranking→25



DA FARE: Controllare la feature selection e capire come mai le domande dei quastionari sono così influenti e pure altezza e peso e non le info da parte degli acceleromentri.





Rimuove alcuni canali/task con regex Time|LiftHold|PointFinger|TouchIndex:
elimina tutti i canali Time
elimina completamente i task LiftHold, PointFinger, TouchIndex
Definisce i canali da processare: solo quelli con Accelerometer.
Applica detrending gravitazionale all’accelerometro:
x - l1_trend_filter(x, vlambda=50) su ogni canale accel.

questa parte qui è interessante, perchè se non erro noi non la facciamo. Potrebbe essere utile prendere spunto per selezionare solo le varibili più importanti anche per noi?






Sì, può essere utile come idea di feature/task selection, ma non copiarla “alla cieca”.

Quello script fa una selezione a priori basata su dominio clinico:
rimuove canali Time (ok, non informativi per classificazione),
esclude task specifici (LiftHold, PointFinger, TouchIndex),
applica detrending solo all’accelerometro.
Questo è diverso dalla tua selezione attuale (correlation + ANOVA + MI), che è data-driven dopo l’estrazione feature.
Quindi la scelta migliore è combinarle:

Regole sensate a priori (es. togliere Time, valutare task meno utili).
Selezione statistica sul train (come già fai).
Ablation test: confronta performance con/without quei task/canali.
Se il risultato migliora o resta uguale con meno task, hai un modello più robusto e semplice.
Quello che eviterei è eliminare task solo perché lo fanno gli autori, senza verificare nel tuo setup.

Se vuoi, ti preparo una mini-griglia di esperimenti (3 run) per decidere in modo oggettivo quali task tenere.