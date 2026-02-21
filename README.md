# 🔬 Algoritmo Diagnostico IgG4-RD

Algoritmo interattivo per la valutazione istologica della malattia IgG4-correlata (IgG4-Related Disease).

## 📋 Descrizione

Strumento web per patologi che guida la valutazione istologica di biopsie e resezioni sospette per IgG4-RD. Non è un calcolatore diagnostico, ma un **supporto decisionale** che aiuta a:

- Decidere **quando** richiedere IHC per IgG4/IgG
- Interpretare i risultati IHC nel contesto morfologico
- Evitare gli errori più comuni (overcall e undercall)
- Generare testo strutturato per il referto

## 🎯 Funzionalità

### Step 0 - Criteri di Esclusione
Verifica degli entry criteria ACR/EULAR 2019 prima di procedere:
- Neoplasia maligna nota
- Infezione attiva
- Granulomi ben formati
- Necrosi prominente
- Infiltrato neutrofilico
- Clonalità B dimostrata

### Step 1 - Selezione Organo
- **14 organi/tessuti** con criteri organo-specifici
- Distinzione **biopsia vs resezione** con soglie differenziate
- Warning specifici per organi problematici (linfonodo, rene)

### Step 2 - Valutazione Morfologica EE
- Checklist interattiva con **criteri pesati**
- Flebite obliterante sfumata (tipica vs suggestiva)
- Warning per forme **burnt-out/paucicellulari**
- Nota sulla **variabilità inter-osservatore**
- Diagnosi differenziali organo-specifiche

### Step 3 - Interpretazione IHC
- Calcolo automatico **ratio IgG4/IgG**
- Soglie differenziate per biopsia/resezione
- Warning critico: **IgG4+ elevate ≠ IgG4-RD**
- Gestione casi borderline e incompleti

### Step 4 - Genera Referto ✨ NEW
- **Testo strutturato** pronto per il referto
- 4 template: compatibile, borderline, non compatibile, incompleto
- Pulsante **copia negli appunti**
- Possibilità di **modifica** prima di copiare

## ⚠️ Warning Implementati

Il tool include diversi livelli di warning per prevenire errori diagnostici:

| Warning | Scopo |
|---------|-------|
| **IgG4+ ≠ IgG4-RD** | Evita l'equazione errata "tante IgG4 = diagnosi" |
| **Linfonodo** | Ricorda che è diagnosi di esclusione estrema |
| **Rene (soglia ≥10)** | Alto rischio di falsi positivi |
| **Forme burnt-out** | Non escludere IgG4-RD se paucicellulare ma pattern tipico |
| **Biopsie** | Il ratio ha priorità sul conteggio assoluto |

## 📊 Tabella Soglie IgG4+/HPF

| Organo | Resezione | Biopsia | Ratio |
|--------|-----------|---------|-------|
| Pancreas | ≥50 | ≥10 | ≥40% |
| Vie biliari | ≥50 | ≥10 | ≥40% |
| Ghiandole salivari | ≥100 | ≥50 | ≥40% |
| Linfonodi | ≥100 | ≥50 | ≥40% |
| Rene | ≥10 ⚠️ | ≥10 ⚠️ | ≥40% |
| Meningi | ≥10 ⚠️ | ≥10 ⚠️ | ≥40% |
| Polmone | ≥50 | ≥20 | ≥40% |
| Aorta | ≥30 | ≥10 | ≥40% |
| Orbita | ≥50 | ≥20 | ≥40% |
| Retroperitoneo | ≥50 | ≥20 | ≥40% |
| Tiroide | ≥50 | ≥20 | ≥40% |
| Cute | ≥50 | ≥20 | ≥40% |
| Prostata | ≥50 | ≥20 | ≥40% |

⚠️ = soglia molto bassa, alto rischio falsi positivi

## 🚀 Utilizzo

### Online
Visita: `https://infingardo.github.io/IgG4/`

### Locale
Scarica `index.html` e aprilo nel browser. Nessuna dipendenza, nessun server richiesto.

## 📚 Riferimenti Principali

- **Wallace ZS et al.** ACR/EULAR 2019 Classification Criteria for IgG4-RD. *Arthritis Rheumatol* 2020;72(1):7-19. [PubMed](https://pubmed.ncbi.nlm.nih.gov/31793274/)

- **Deshpande V et al.** Consensus statement on the pathology of IgG4-related disease. *Mod Pathol* 2012;25(9):1181-1192. [PubMed](https://pubmed.ncbi.nlm.nih.gov/22596100/)

- **Kamisawa T et al.** IgG4-related disease. *Lancet* 2015;385(9976):1460-1471. [PubMed](https://pubmed.ncbi.nlm.nih.gov/25481618/)

- **Cheuk W, Chan JK.** Lymphadenopathy of IgG4-related disease. *Semin Diagn Pathol* 2012;29(4):226-234. [PubMed](https://pubmed.ncbi.nlm.nih.gov/23068302/)

Riferimenti organo-specifici disponibili nella sezione Bibliografia del tool.

## ⚠️ Disclaimer

Questo strumento è destinato **esclusivamente a uso educativo e di supporto diagnostico** per professionisti sanitari qualificati.

**NON è:**
- Un sistema diagnostico validato
- Un sostituto del giudizio clinico
- Un criterio classificativo ufficiale

**Lo score morfologico:**
- È un sistema empirico, non validato prospetticamente
- I pesi derivano da letteratura e esperienza, non da regression model
- **NON va riportato in diagnosi**

La diagnosi di IgG4-RD richiede sempre:
- Correlazione clinico-patologica
- Criteri ACR/EULAR 2019 completi
- Discussione multidisciplinare

## 🔄 Changelog

### v2.0.0 (Gennaio 2025)
- ✨ **Genera Referto**: testo strutturato con copia negli appunti
- 🚨 Warning critico IgG4+ ≠ IgG4-RD
- ⚠️ Warning aggressivo per linfonodo
- 📝 Flebite obliterante sfumata (tipica vs suggestiva)
- 🔥 Warning forme burnt-out/paucicellulari
- 📊 Nota variabilità inter-osservatore
- 📋 Disclaimer metodologico ampliato

### v1.0.0 (Novembre 2025)
- Release iniziale
- 14 organi con criteri specifici
- Distinzione biopsia/resezione
- Calcolo ratio IgG4/IgG
- Bibliografia interattiva

## 🤝 Contributi

Contributi, segnalazioni di bug e suggerimenti sono benvenuti. Apri una issue o una pull request.

In particolare, sono graditi:
- Segnalazioni di errori nei criteri o nelle soglie
- Suggerimenti per nuovi organi/sedi
- Feedback sull'usabilità clinica
- Traduzioni

## 📄 Licenza

MIT License

## 👤 Autore

**Filippo Bianchi** — Patologo  
ASST Fatebenefratelli-Sacco, Milano

GitHub: [@infingardo](https://github.com/infingardo)

---

*"Non stiamo insegnando cos'è l'IgG4. Stiamo insegnando quando NON fidarsi dell'IgG4."*
