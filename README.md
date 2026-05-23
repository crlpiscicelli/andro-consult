# ANDRO·CONSULT

**CDSS per Iperandrogenismo e PCOS**  
Parte della suite [GINOS](https://ginos-cdss.it) — GINecologia e OSTetricia / Gynecology Informatics Network for Operative Support

> Sviluppato da **Dr. Carlo Piscicelli** — Specialista in Ostetricia e Ginecologia

---

## Descrizione

ANDRO·CONSULT è un sistema di supporto decisionale clinico (CDSS) per la valutazione strutturata dell'iperandrogenismo femminile e della Sindrome dell'Ovaio Policistico (PCOS).

Implementa l'**International PCOS Guideline 2023** (ESHRE/NHMRC/AE-PCOS Society) e i **Criteri di Rotterdam 2003/2023**.

---

## Funzionalità

- **6 fasi sequenziali**: Anamnesi → Esame Obiettivo → Laboratorio → Ecografia → Diagnosi Differenziale → Sintesi & Terapia
- **Score clinici interattivi**: mFG (9 siti, soglie etnia-specifiche), Ludwig, GAGS (interfaccia visiva a bottoni)
- **Calcolatori automatici**: BMI (obesità Grado I/II/III), circonferenza vita, FAI, HOMA-IR, ratio LH/FSH
- **Calcolatore volume ovarico** integrato (formula ellissoide, guida alle misure)
- **Algoritmo Rotterdam** con fenotipizzazione A/B/C/D e modalità adolescente
- **Diagnosi differenziale strutturata** con auto-flag su 6 condizioni (CAH-NC, iperprolattinemia, ipotiroidismo, Cushing, tumore secernente, IAH)
- **Stratificazione rischio metabolico/CV** (basso / moderato / elevato)
- **Generazione AI di 4 documenti** (lettera paziente, consulenza collega, richiesta esami, piano terapeutico) — modificabili nel browser, con copia e stampa/PDF
- **Profilo medico configurabile** — intestazione personalizzata su tutti i documenti
- **Salvataggio/caricamento sessione JSON** per follow-up e controllo esami
- **20+ modali informativi** con contenuto clinico e fonti bibliografiche
- **Tooltip Rotterdam** cliccabili con spiegazione completa dei 3 criteri

---

## Stack tecnico

- HTML/CSS/JavaScript monopagina — nessuna dipendenza esterna (solo Google Fonts)
- Proxy serverless Vercel (`api/claude.js`) per chiamate sicure all'API Anthropic
- Chiave API gestita come variabile d'ambiente Vercel (`ANTHROPIC_API_KEY`)
- Sessioni persistenti via JSON locale

---

## Deploy

Il progetto è deployato su Vercel con deploy automatico ad ogni push su `main`.

```
andro-consult/
├── api/
│   └── claude.js          # proxy serverless Anthropic API
├── andro-consult.html     # app principale
├── andro-consult-guide.html  # guida e linee guida
└── vercel.json            # routing
```

**Variabile d'ambiente richiesta su Vercel:**

| Nome | Valore |
|------|--------|
| `ANTHROPIC_API_KEY` | `sk-ant-...` |

---

## Linee guida di riferimento

| Documento | Ente | Anno |
|-----------|------|------|
| International Evidence-Based Guideline for PCOS | ESHRE/NHMRC/AE-PCOS Society | 2023 |
| Revised Rotterdam Criteria | ESHRE/ASRM | 2003/2023 |
| Evaluation and Treatment of Hirsutism | Endocrine Society | 2018 |
| ADA Standards of Medical Care in Diabetes | ADA | 2024 |
| WHO Medical Eligibility Criteria for Contraceptive Use | WHO | 2015 |
| Global Acne Grading System (GAGS) | Doshi et al. | 1997 |
| Ferriman-Gallwey Score | Ferriman & Gallwey / Hatch | 1961/1981 |

---

## Disclaimer

Strumento di supporto decisionale clinico. Non sostituisce il giudizio del medico.  
Non validato come dispositivo medico ai sensi del Reg. EU 2017/745 (MDR) né come sistema AI ad alto rischio ai sensi del Reg. EU 2024/1689 (AI Act).

---

*Suite GINOS · [ginos-cdss.it](https://ginos-cdss.it)*
