# CSS Grid

Grid distribueix elements en **dues dimensions**: files i columnes.

```css
.tauler {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}
```

| Propietat | Serveix per a |
| --- | --- |
| `grid-template-columns` | Definir columnes; `1fr` és una fracció de l'espai disponible |
| `gap` | Separar files i columnes |
| `grid-template-areas` | Dibuixar una disposició amb noms |
| `grid-area` | Assignar un element a un nom d'àrea |
| `minmax(220px, 1fr)` | Donar una mida mínima i fer una columna flexible |

El tauler mostra que repetir `principal` en el dibuix fa que ocupe un rectangle més gran.
