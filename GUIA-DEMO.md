# Guia de demostració: CSS Layout

Guió per a dues hores de classe. L'objectiu és que l'alumnat **observe un canvi, propose una explicació i només després veja la regla CSS**. Obriu cada `index.html` amb Live Server i manteniu oberts el navegador i `styles.css` en paral·lel.

## Abans de començar (5 min)

1. Obriu l'inspector del navegador (`F12`) i activeu el mode de dispositiu adaptable.
2. Expliqueu que HTML aporta l'estructura i CSS decideix la presentació.
3. Modifiqueu `background` o `border-radius` de `.boto` per comprovar que desar el fitxer actualitza el navegador.

## 1. Flexbox — repartir i alinear (35 min)

Obriu `flexbox/index.html` i `flexbox/styles.css`.

| Pas | Canvi temporal al CSS | Què cal mirar / explicar |
| --- | --- | --- |
| 1 | En `.capcalera`, desactiveu `display: flex`. | Marca, menú i botó tornen al flux normal, un davall de l'altre. `display: flex` afecta els fills directes. |
| 2 | Torneu a activar-lo. Canvieu `justify-content: space-between` per `center`, `flex-start` i `space-around`. | L'alineació es mou horitzontalment perquè la direcció inicial és `row`: és l'eix principal. |
| 3 | En `.capcalera`, canvieu `align-items: center` per `flex-start` i `flex-end`. | Ara es mouen en vertical: és l'eix transversal. |
| 4 | En `.hero`, afegiu `flex-direction: column`. | Els eixos s'intercanvien: `justify-content` passa a actuar verticalment. |
| 5 | En `.targetes`, desactiveu `flex-wrap: wrap` i feu estreta la finestra. | Les targetes intenten cabre en una fila. En tornar a activar `wrap`, baixen a una fila nova. |
| 6 | En `.destacada`, canvieu `flex-grow: 2` per `0`, `1` i `3`. | `flex-grow` reparteix l'espai lliure; 2 són dues parts del creixement. |

**Idea clau:** Flexbox és adequat per a elements ordenats en una direcció principal, com una capçalera o una fila de targetes.

## 2. Grid — dibuixar un tauler (35 min)

Obriu `grid/index.html` i `grid/styles.css`.

| Pas | Canvi temporal al CSS | Què cal mirar / explicar |
| --- | --- | --- |
| 1 | En `.tauler`, desactiveu `display: grid`. | Els articles recuperen el flux vertical normal. Grid s'activa en el contenidor. |
| 2 | Torneu a activar-lo, però canvieu `repeat(3, 1fr)` per `repeat(2, 1fr)`. | `fr` reparteix l'espai disponible en fraccions iguals. |
| 3 | Poseu `grid-template-columns: 2fr 1fr 1fr`. | La primera columna rep dues parts de l'espai i les altres una. |
| 4 | Desactiveu `grid-template-areas`. | Les targetes es col·loquen per ordre, encara que conserven tres columnes. |
| 5 | Restaureu les àrees i llegiu la regla com un plànol: `principal principal tecnologia`. | Un nom repetit ocupa diverses cel·les. `grid-area` connecta l'article amb el plànol. |
| 6 | Intercanvieu `agenda` i `tecnologia` dins de `grid-template-areas`. | La posició canvia sense tocar l'HTML. |
| 7 | Feu la finestra més estreta de 650 px i torneu-la a eixamplar. | La media query substitueix el plànol de tres columnes per una única columna. |

**Idea clau:** Grid és especialment útil quan files i columnes són igual d'importants, com en un tauler o una plantilla de pàgina.

## 3. Responsive — una pàgina, diverses amplàries (30 min)

Obriu `responsive/index.html` i `responsive/styles.css`. Activeu el mode de dispositiu adaptable del navegador.

| Amplària / pas | Què cal mirar / explicar |
| --- | --- |
| 375 px | Estat base: botó de menú visible, navegació oculta i una targeta per fila. És *mobile first*. |
| 599 → 600 px | Apareix `nav` i desapareix `.menu-boto`. Mostreu `@media (min-width: 600px)`: s'aplica des d'eixa amplària cap amunt. |
| 699 → 700 px | `.rutes` passa d'una a dues columnes. Compareu `1fr` amb `repeat(2, 1fr)`. |
| 949 → 950 px | La graella passa a tres columnes: és el mateix HTML amb una disposició diferent. |
| Qualsevol amplària | Observeu el títol. `clamp(2.5rem, 10vw, 5.5rem)` permet que cresca, però fixa un mínim i un màxim. |
| Qualsevol amplària | Canvieu temporalment `.contenidor { width: min(1100px, 90%); }` per `width: 100%`. | Es veu per què es combinen un màxim i un percentatge: el contingut no queda enganxat a les vores ni excessivament ample. |

**Idea clau:** responsive no és crear tres webs; és aplicar millores progressives sobre una sola estructura.

## Tancament (10 min)

Abans de fer cadascun d'aquests canvis, demaneu una predicció: «Què passarà si canviem `space-between` per `center`?», «Què passarà si repetim `principal` tres vegades?» i «Quin aspecte tindrà la pàgina a 699 px?». Feu el canvi i contrasteu la predicció amb el resultat.
