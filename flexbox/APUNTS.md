# Flexbox

Flexbox organitza els fills directes d'un contenidor en **una dimensió**: una fila o una columna.

```css
.contenidor {
  display: flex;
  flex-direction: row; /* valor inicial */
}
```

| Propietat | S'aplica a | Serveix per a |
| --- | --- | --- |
| `justify-content` | contenidor | Repartir els elements en l'eix principal |
| `align-items` | contenidor | Alinear-los en l'eix transversal |
| `gap` | contenidor | Separar elements sense marges |
| `flex-wrap: wrap` | contenidor | Fer que els elements baixen de línia |
| `flex: 1` | element fill | Fer-lo créixer i ocupar una part igual de l'espai |
| `order` | element fill | Canviar-ne l'ordre visual |

La capçalera de l'exemple usa `justify-content: space-between`; la galeria usa `flex-wrap` i `flex: 1`.
