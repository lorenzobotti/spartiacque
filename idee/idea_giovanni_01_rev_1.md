## Implementazione Hardware e Software

### 1. **Controllo dei LED**

Per creare l'effetto di profondità, utilizzerai una striscia di LED RGB o un array di LED indirizzabili (ad esempio **WS2812** o **SK6812**). Questi LED saranno disposti dietro il televisore per simulare la profondità, e il loro colore cambierà in base all'immagine visualizzata. Ogni LED potrà essere controllato individualmente.

### 2. **Interfaccia di Controllo**

Una periferica hardware (come una **manopola rotante**, **leva**, o **bottone**) permetterà allo spettatore di interagire con il sistema. Un **encoder rotativo** o un **potenziometro** permetterà di spostare l'occhio e influire sull'effetto delle linee nel cubo.

### 3. **Microcontrollore**

Un microcontrollore come l'**ESP32** o un **Raspberry Pi Pico** sarà utilizzato per controllare sia i LED che l'interazione con la periferica di controllo. L'ESP32 è particolarmente adatto per questo tipo di progetto grazie alle sue dimensioni compatte e al supporto per la connettività Wi-Fi (per l'invio dei dati all'host).

### 4. **Alimentazione**

Poiché i LED RGB possono consumare una quantità significativa di energia, sarà necessario un alimentatore adeguato per supportare sia i LED che il microcontrollore.

## Implementazione Software

### 1. **Rendering dell'Occhio e del Cubo in Tempo Reale**

TODO Giovanni

### 2. **Controllo dei LED**

La posizione dell'occhio nel cubo influenzerà quali parti dell'immagine sono visibili, e di conseguenza i LED cambieranno colore per riflettere questa visibilità. Da capire se fare un sensore "stupido" che riceve solo le coordinate e il colore dei led, o se invece riceve qualche tipo di info multimediale e si occupa lui di capire come trasformare questo dato in coordinate e colori.

Si possono usare librerie come **Adafruit NeoPixel** (native per ESP32) per il controllo dei LED. 

### 3. **Interazione con la Periferica Hardware**

La manopola o la leva invieranno segnali al microcontrollore, che invierà questi dati all'host. Avendo questa informazione già nel micro, potrebbe essere sufficiente per capire come aggiornare i LED di conseguenza senza bisogno di info da parte dell'host (pensiamoci).

### 4. **Comunicazione tra Hardware e Software**

Se decidiamo ESP32, possiamo decidere di comunicare con sia via **seriale** che **WIFI** .

## Proposta di Aggiunta: Effetto di Profondità nei LED

Oltre alla gestione dell'immagine, possiamo creare un effetto di profondità nei LED dietro al televisore, variando l'intensità luminosa dei LED in base alla posizione dell'occhio. Quando l'occhio si sposta, l'area visibile dovrebbe cambiare, e i LED dovrebbero "rispondere" a questa modificabilità, dando un'impressione ancora più profonda dell'immagine.

## Componenti Necessari

- **LED**: WS2812, SK6812 (strisce LED RGB indirizzabili)
- **Microcontrollore**: ESP32, Arduino, Raspberry Pi
- **Software di Rendering**: (presumo) OpenGL, three.js, Processing
- **Sensori di Input**: Encoder rotativo, potenziometro, joystick
- **Alimentazione**: Adattatore di alimentazione per LED e microcontrollore
- **Librerie di Controllo**: Adafruit NeoPixel, P5.js, OpenGL

## Conclusioni

Questo progetto offre una fusione di hardware e software per creare un'esperienza interattiva unica, dove l'utente può manipolare in tempo reale un'immagine 3D e osservare come l'effetto di profondità venga simulado dai LED dietro il televisore. Il risultato finale sarà un'installazione che combina arte visiva e interattività, ispirata alla filosofia del solipsismo.