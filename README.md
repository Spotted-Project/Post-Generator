# Post configurations
E' possibile generare in modo automatizzato immagini, con set di colori e configurazioni diverse.
Funziona sia con testo che con immagini.

Il programma genera immagini ottimizzate per i social impostati.
Restituendo un immagine che rispetta formati, dimensioni e compressione ottimale per garantire la miglior qualità dell'immagine possibile.

## I colori
I colori devono essere dichiarati come array di tuple di 3 elementi.

Il programma sceglierà automaticamente un elemento dall'array in modo random.
```
# (BACKGROUND, COLORE_PRIMARIO, COLORE_TESO)

[
    (RED_200, RED_800, BLACK),
    (BLUE_200, BLUE_200, BLACK),
]
```

I colori sono tutti quelli disponibili nelle palette di [google material design](https://material.io/resources/color/#!/?view.left=0&view.right=0).
Seguire i consigli del tool per ottimizzare la scelta colori.

Piu informazioni sul [sitema colori di google](https://material.io/design/color/the-color-system.html#tools-for-picking-colors)

## Dimensione del testo
Il testo viene formattato automaticamente con una dimensione corretta.
Dato che ogni testo ha il suo space schema, non è possibile configurare il font dinamicamente.
Il font è quello che è e non può essere cambiato.

<img src="assets/1.jpeg" alt="drawing" width="450"/>
<img src="assets/2.jpeg" alt="drawing" width="450"/>

## Posizione del testo
Il testo può essere genarato i 3 modi
- Centrato nell'immagine `text_align: "center"`
- Allineato a Destra `text_align: "right"`
- Allineato a Sinistra `text_align: "left"`

<img src="assets/3.jpeg" alt="drawing" width="450"/>
<img src="assets/4.jpeg" alt="drawing" width="450"/>

## Logo
Il logo può essere settato in 2 modi:
- come sfondo
- in uno dei 4 angoli (superiore, inferiore, destra, sinistra).
  - `logo_position: "left-down"`
  - `logo_position: "left-up"`
  - `logo_position: "right-down"`
  - `logo_position: "right-up"`
- al centro sopra ed al centro sotto
  - `logo_position: "center-down"`
  - `logo_position: "center-up"`

<img src="assets/7.jpeg" alt="drawing" width="450"/>
<img src="assets/5.jpeg" alt="drawing" width="450"/>
<img src="assets/6.jpeg" alt="drawing" width="450"/>

## Quote
Le virgolette del quote sono rimovibili, o sostituibili con un ummagine diversa ad esempio per diversificare annunci da spottate.

Le immagini sono predefinite
- `top_image: "quotation-marks"`

## Rectangle
E' possibile contornare un post con un rettangolo di dimensione fissa

- `rectangle: true`
- `rectangle: false`

<img src="assets/10.jpeg" alt="drawing" width="450"/>
<img src="assets/10a.jpeg" alt="drawing" width="450"/>

## Colorazione del logo
Il logo viene automaticamente settato dello stesso colore del testo (colorization disattivata).
Oppure del colore del colore secondario (colorization attiva).
- `colorize_logo: false`
- `colorize_logo: true`

### Requisiti file.png del logo:
- Deve avere una **dimensione di 1024x1024** in formato png con sfondo trasparente.
- Il logo deve essere **bianco #FFFFFF (255, 255, 255)** per poter usare la colorization 
(le parti non bianche non sono soggette a colorization, usare questo a propio vantaggio).
La colorization evita la necessità di avere 2 versioni di logo, una chiara (per gli sfondi scuri) ed una scura (per gli sfondi chiari)

Il sigolo file:
- logo-name.png

`logo: "img/logo/logo-name.png"`

<img src="assets/8.jpeg" alt="drawing" width="450"/>
<img src="assets/9.jpeg" alt="drawing" width="450"/>

## Extra
Su richiesta possiamo implementare altre cose più specifiche.

# Some Examples

<img src="assets/8.jpeg" alt="drawing" width="450"/>
<img src="assets/11.jpeg" alt="drawing" width="450"/>
<img src="assets/12.jpeg" alt="drawing" width="450"/>
<img src="assets/13.jpeg" alt="drawing" width="450"/>
<img src="assets/14.jpeg" alt="drawing" width="450"/>

## Configurations
```
    "pavlov": {
            "logo": "img/icons/pavlov.png",
            "operators": ["123", "456", "789"],
            "name_tag": "pavlov-bot",
            "images": {
                "meme": {
                    "image_scale": [1, 1],
                    "colorize_logo": false,
                    "logo_position": "auto"
                }
            },
            "text": {
                "spot": {
                    "top_image": "quotation-marks",
                    "text_align": "center",
                    "line_position": null,
                    "colorize_logo": true,
                    "logo_position": "center",
                    "rectangle": false
                }
            }
        },
```