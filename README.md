# 🔬 Algoritmo Diagnostico IgG4-RD

Supporto istopatologico ragionato per sospetta malattia IgG4-correlata (IgG4-Related Disease).

## 📋 Descrizione

Strumento web per patologi che guida la valutazione istologica di biopsie e resezioni sospette per IgG4-RD. Non è un calcolatore diagnostico, ma un **supporto decisionale** che aiuta a:

- Riconoscere il pattern morfologico corretto (fibrosi storiforme + flebite obliterante + plasmacitosi)
- Decidere **quando** richiedere IHC per IgG4/IgG
- Interpretare i risultati IHC nel contesto morfologico e per sede
- Evitare gli errori più comuni (overcall e undercall)
- Generare testo strutturato per il referto, calibrato per sede e tipo di campione

> **"Prima il pattern, poi il contesto, poi l'IgG4."**

## 🎯 Funzionalità

### Step 0 — Pre-screening Patologico
Verifica dei principali **red flag patologici / mimics** che rendono improbabile IgG4-RD come diagnosi primaria del campione. I criteri ACR/EULAR 2019 sono classificativi e multi-dominio: questo step non li sostituisce, identifica solo le esclusioni patologiche maggiori.

### Step 1 — Selezione Organo
- **14 organi/tessuti** con criteri organo-specifici
- Distinzione **biopsia vs resezione** con cut-off differenziati
- Warning dedicato per linfonodo ("territorio minato")
- Badge **`low-evidence`** per sedi a bassa robustezza nosologica (meningi, cute, prostata, aorta)
- Badge **`numerical caution`** per rene (entità riconosciuta, cut-off ≥10/HPF fragile)

### Step 2 — Valutazione Morfologica EE
- Checklist interattiva con **criteri pesati organo-specifici**
- Flebite obliterante: tipica vs suggestiva
- Warning per forme **burnt-out/paucicellulari**
- Nota sulla **variabilità inter-osservatore**
- Diagnosi differenziali organo-specifiche

### Step 3 — Interpretazione IHC
- Calcolo automatico **ratio IgG4/IgG**
- Cut-off orientativi differenziati per biopsia/resezione
- Warning critico: **IgG4+ elevate ≠ IgG4-RD**
- Gestione casi borderline e incompleti

### Step 4 — Genera Referto ✨
- **Tre livelli refertativi** in base a sede + IHC:
  - Livello 1: "compatibile nel corretto contesto" (sedi classiche, IHC coerente)
  - Livello 2: "suggestivi ma non diagnostici" (sedi non classiche o IHC borderline)
  - Livello 3: testo cautelare dedicato (linfonodo, sedi low-evidence, numerical caution)
- Pulsante **copia negli appunti**
- Possibilità di **modifica** prima di copiare

## ⚠️ Warning Implementati

| Warning | Sede | Scopo |
|---------|------|-------|
| **IgG4+ ≠ IgG4-RD** | Globale | Evita l'equazione errata "tante IgG4 = diagnosi" |
| **Territorio minato** | Linfonodo | Diagnosi di esclusione estrema; referto sempre livello 3 |
| **low-evidence** | Meningi, cute, prostata, aorta | Robustezza nosologica ridotta |
| **numerical caution** | Rene | Entità riconosciuta, cut-off ≥10/HPF fragile |
| **Forme burnt-out** | Globale | Non escludere IgG4-RD se paucicellulare ma pattern tipico |
| **Biopsie** | Globale | Il ratio ha priorità sul conteggio assoluto |

## 📊 Cut-off Orientativi IgG4+/HPF

| Organo | Resezione | Biopsia | Ratio | Note |
|--------|-----------|---------|-------|------|
| Pancreas | ≥50 | ≥10 | ≥40% | Deshpande 2012, ICDC 2011 |
| Vie biliari | ≥50 | ≥10 | ≥40% | Nakazawa 2012 |
| Ghiandole salivari | ≥100 | ≥50 | ≥40% | Geyer 2010 |
| Retroperitoneo | ≥50 | ≥20 | ≥40% | Spesso fibrotico |
| Orbita / Gh. lacrimale | ≥50 | ≥20 | ≥40% | Sogabe 2012 |
| Linfonodi | ≥100 | ≥50 | ≥40% | ⚠️ Diagnosi di esclusione; DD linfoma/Castleman |
| Rene | ≥10 ⚠️ | ≥10 ⚠️ | ≥40% | Numerical caution; cut-off molto basso |
| Meningi | ≥10 ⚠️ | ≥10 ⚠️ | ≥40% | Low-evidence; spesso paucicellulare |
| Polmone | ≥50 | ≥20 | ≥40% | Wang 2018 |
| Aorta | ≥30 | ≥10 | ≥40% | Low-evidence; DD arteriti |
| Tiroide | ≥50 | ≥20 | ≥40% | DD Hashimoto, Riedel |
| Cute | ≥50 | ≥20 | ≥40% | Low-evidence; raro isolato |
| Prostata | ≥50 | ≥20 | ≥40% | Low-evidence; DD adenocarcinoma |

> I valori sono **cut-off orientativi**, non soglie diagnostiche validate prospetticamente.  
> ⚠️ = cut-off particolarmente basso o robustezza ridotta.

## 🚀 Utilizzo

### Online
[https://infingardo.github.io/IgG4/](https://infingardo.github.io/IgG4/)

### Locale
Scarica `index.html` e aprilo nel browser. Nessuna dipendenza, nessun server richiesto.

## 📚 Riferimenti Principali

- **Wallace ZS et al.** ACR/EULAR 2019 Classification Criteria for IgG4-RD. *Arthritis Rheumatol* 2020;72(1):7-19. [PubMed 31796497](https://pubmed.ncbi.nlm.nih.gov/31796497/)
- **Deshpande V et al.** Consensus statement on the pathology of IgG4-related disease. *Mod Pathol* 2012;25(9):1181-1192. [PubMed 22596100](https://pubmed.ncbi.nlm.nih.gov/22596100/)
- **Kamisawa T et al.** IgG4-related disease. *Lancet* 2015;385(9976):1460-1471. [PubMed 25481618](https://pubmed.ncbi.nlm.nih.gov/25481618/)
- **Cheuk W, Chan JK.** Lymphadenopathy of IgG4-related disease. *Semin Diagn Pathol* 2012;29(4):226-234. [PubMed 23068302](https://pubmed.ncbi.nlm.nih.gov/23068302/)
- **Raissian Y et al.** Diagnosis of IgG4-related tubulointerstitial nephritis. *J Am Soc Nephrol* 2011;22(7):1343-1352. [PubMed 21719792](https://pubmed.ncbi.nlm.nih.gov/21719792/)

## ⚠️ Disclaimer

Questo strumento è destinato **esclusivamente a uso educativo e di supporto diagnostico** per professionisti sanitari qualificati.

**NON è:**
- Un sistema diagnostico validato
- Un sostituto del giudizio clinico
- Un criterio classificativo ufficiale

**Lo score morfologico:**
- È un sistema empirico, non validato prospetticamente
- I pesi derivano da letteratura e consenso esperto (Deshpande 2012, Zen 2012)
- **NON va riportato in diagnosi**

La diagnosi di IgG4-RD richiede sempre:
- Correlazione clinico-patologica
- Criteri ACR/EULAR 2019 completi
- Discussione multidisciplinare

## 🔄 Changelog

### v3.0.0 (Marzo 2026)
**Revisione concettuale e architetturale completa**

*Concettuale:*
- 🏷️ Step 0 ribattezzato "Pre-screening Patologico" — rimossa l'etichetta fuorviante "Entry Criteria ACR/EULAR 2019"
- 📝 Nota esplicita: ACR/EULAR 2019 sono criteri classificativi multi-dominio, non un engine istologico
- ⚠️ Esclusioni step 0 → "major pathological red flags / mimics"; rimosso determinismo assoluto (coesistenza IgG4-RD in altra sede non esclusa)
- 🔵 "Soglia diagnostica" → "cut-off orientativo" in tutto il file
- 🏷️ Badge **`low-evidence`** (meningi, cute, prostata, aorta) e **`numerical caution`** (rene) — tassonomia distinta
- 🧠 Rene: rimosso da low-evidence; `numericalCaution: true` con nota dedicata. L'entità è riconosciuta, il problema è il cut-off ≥10/HPF
- 📄 **Tre livelli refertativi**: livello 1 per sedi classiche + IHC coerente; livello 2 per sedi non classiche/borderline; livello 3 per linfonodo e low-evidence
- 🚨 Linfonodo: referto livello 3 fisso, mai "compatibile" standalone; testo sempre con cautela esplicita su Castleman/linfomi

*Architetturale JS:*
- 🐛 Bug fix: `resetAfterOrgan()` → separato in `resetDependentSections()` + `resetOrganSelection()` — il selettore organo non si svuotava più all'atto della selezione
- 🐛 Bug fix: validazione igg4Count: `!igg4Count` → `igg4Input === '' || isNaN(igg4Count)` — lo 0 è ora accettato come input valido
- 🐛 Bug fix: ratio null-safe (`parseFloat` solo se iggTotal > 0)
- 🗑️ Dead code rimosso: `lowEvidenceOrgans` (array duplicava verità già nel dataset)
- 🏷️ `classicOrgans` → `level1EligibleOrgans` (nome descrittivo della funzione logica)

*Bibliografico:*
- 🔗 PMID Wallace et al. corretto: 31793274 → **31796497**

### v2.0.0 (Gennaio 2025)
- ✨ Genera Referto con copia negli appunti
- 📖 Sezione About IgG4-RD per patologi
- 🚨 Warning critico IgG4+ ≠ IgG4-RD
- ⚠️ Warning linfonodo e forme burnt-out
- 📊 Disclaimer metodologico ampliato

### v1.0.0 (Novembre 2024)
- Release iniziale
- 14 organi con criteri specifici
- Distinzione biopsia/resezione
- Calcolo ratio IgG4/IgG
- Bibliografia interattiva

## 👤 Autore

**Filippo Bianchi** — Patologo  
ASST Fatebenefratelli-Sacco, Milano

GitHub: [@infingardo](https://github.com/infingardo)

---

*"Il vetrino non mente, il reagente sì."*
