# 🇮🇹 Osservatorio ANBI Risorse Idriche - Mappa Interattiva

Una dashboard interattiva per il monitoraggio settimanale delle risorse idriche e del rischio idrogeologico in Italia. Il progetto visualizza lo stato delle regioni (siccità, alluvioni, criticità) attraverso una mappa cromatica interattiva.

![Anteprima Dashboard](https://github.com/davideformatlab/anbi/raw/main/foto%20esempio%20mappa.png)

## 🚀 Funzionalità Principali

* **Mappa Interattiva (Leaflet.js):** Visualizzazione vettoriale delle regioni italiane.
* **Codice Colore Semantico:**
    * 🟦 **Blu:** Eccesso idrico / Alluvioni.
    * 🟥 **Rosso:** Siccità estrema.
    * 🟧 **Arancione:** Warning / Attenzione.
    * ⬜ **Grigio:** Dati non disponibili.
* **Interazione "Click-to-View":** Cliccando su una regione si apre un popup dettagliato. La mappa si sposta automaticamente (`AutoPan`) per garantire la leggibilità del testo senza "uscire" dallo schermo.
* **Pannello Istruzioni:** Un box informativo (chiudibile) guida l'utente nell'uso della mappa.
* **Responsive Design:** Layout adattivo che si trasforma su smartphone (sidebar in alto/basso, controlli touch ottimizzati).
* **Sidebar Informativa:** Colonna laterale con contesto strategico, dati aggregati e pulsante di reset della vista.

## 🛠️ Tecnologie Utilizzate

* **HTML5 & CSS3:** Layout Flexbox moderno.
* **JavaScript (ES6):** Logica applicativa senza framework pesanti.
* **[Leaflet.js](https://leafletjs.com/):** Libreria open-source per mappe interattive mobile-friendly.
* **GeoJSON:** Dati vettoriali per i confini regionali (Fonte: OpenPolis).

## 📦 Installazione e Uso

Non sono necessari build tool o installazioni complesse (npm, node, ecc.). È un sito statico puro.

1.  **Clona il repository:**
    ```bash
    git clone [https://github.com/davideformatlab/anbi.git](https://github.com/davideformatlab/anbi.git)
    ```
2.  **Apri il progetto:**
    Fai doppio click sul file `index.html` per aprirlo nel tuo browser predefinito.

## ⚙️ Personalizzazione dei Dati

I dati delle regioni sono contenuti in un oggetto JavaScript all'interno del file `index.html`. Per aggiornare il report settimanale, modifica la costante `dataRegions`:

```javascript
const dataRegions = {
    "Lombardia": {
        title: "Titolo del Popup",
        desc: "Descrizione dettagliata dell'evento idrico...",
        type: "flood" // Opzioni: 'flood', 'drought', 'warning'
    },
    // ... altre regioni
};
