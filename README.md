# RED III Screening Tool 🌱

Strumento di screening per la conformità alla Direttiva Europea **RED III** (Renewable Energy Directive), pensato per operatori di impianti di biometano e biogas che vogliono valutare la propria posizione normativa e pianificare le azioni necessarie per accedere a incentivi, Garanzie di Origine (GO) e mercati regolamentati.

---

## ✨ Funzionalità principali

- **Screening guidato** — questionario strutturato per raccogliere dati sull'impianto, gli obiettivi e la maturità documentale
- **Esito immediato** — calcolo automatico di:
  - Impatto normativo (Basso / Medio / Alto)
  - Maturità compliance (Buona / Intermedia / Critica)
  - Livello di rischio complessivo
- **Punti di attenzione** — rilevamento automatico di criticità con priorità e suggerimenti operativi
- **Roadmap personalizzata** — piano d'azione a step (0–30 / 30–90 / 90–180 giorni) generato dinamicamente dai risultati del questionario
- **Sommario stampabile** — export del report per condivisione interna

---

## 🛠️ Stack tecnologico

| Tecnologia | Utilizzo |
|---|---|
| [Next.js](https://nextjs.org/) (App Router) | Framework React full-stack |
| TypeScript | Tipizzazione statica |
| Tailwind CSS | Styling |
| `localStorage` | Persistenza locale dei risultati |

---

## 📁 Struttura del progetto

```
app/
├── screening/       # Questionario di screening
│   └── page.tsx
├── result/          # Esito e analisi del rischio
│   └── page.tsx
├── roadmap/         # Piano d'azione personalizzato
│   └── page.tsx
├── manuale/         # Metodologia e documentazione
└── components/
    ├── BackToHome.tsx
    ├── BackToResult.tsx
    └── PrintableSummary.tsx
```

---

## 🚀 Getting started

### Prerequisiti

- Node.js >= 18
- npm / yarn / pnpm

### Installazione

```bash
git clone https://github.com/tuo-utente/red3-screening.git
cd red3-screening
npm install
```

### Avvio in sviluppo

```bash
npm run dev
```

Apri [http://localhost:3000](http://localhost:3000) nel browser.

### Build di produzione

```bash
npm run build
npm start
```

---

## 🔍 Come funziona

1. L'utente compila il **questionario di screening** (stato impianto, obiettivi, maturità LCA, tracciabilità feedstock, certificazioni, monitoraggio metano, ecc.)
2. Le risposte vengono salvate in `localStorage` e passate alla pagina **Result** via query param
3. L'algoritmo calcola:
   - **Impatto normativo** in base agli obiettivi (incentivi, vendita, clienti, GO)
   - **Maturità compliance** tramite punteggio sui 6 domini chiave
   - **Rischio finale** con aggiustamento basato sul livello di confidenza dichiarato
4. La pagina **Roadmap** genera un piano d'azione ordinato per fasi e owner

---

## 📋 Domini di compliance valutati

| Dominio | Descrizione |
|---|---|
| Feedstock dimostrabile | Capacità di dimostrare l'origine delle materie prime |
| Tracciabilità feedstock | Registri e contratti di fornitura |
| LCA / GHG | Calcolo del ciclo di vita delle emissioni |
| Soglia GHG confermata | Rispetto della riduzione minima Art. 29 RED III |
| Status certificazione | Schema volontario (ISCC, REDcert, 2BSvs) |
| Mass balance | Sistema di contabilizzazione e riconciliazione |
| Monitoraggio CH₄ (LDAR) | Rilevamento perdite di metano |

---

## 📄 Licenza

Distribuito sotto licenza MIT. Vedi `LICENSE` per i dettagli.
