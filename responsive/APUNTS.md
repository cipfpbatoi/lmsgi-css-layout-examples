# Disseny responsive

Una web responsive adapta la presentació a l'amplària disponible. Aquest exemple és **mobile first**: el CSS inicial és per a mòbil i les media queries hi afigen millores.

```css
/* Estil base: mòbil */
.rutes { grid-template-columns: 1fr; }

/* A partir de 700 píxels */
@media (min-width: 700px) {
  .rutes { grid-template-columns: repeat(2, 1fr); }
}
```

| Concepte          | Exemple del projecte                                          |
|-------------------|---------------------------------------------------------------|
| Meta viewport     | Permet que el mòbil use l'amplària real de pantalla           |
| `min-width`       | Aplica estils des d'una amplària mínima                       |
| `clamp()`         | Fa que el títol cresca sense superar uns límits               |
| Unitats relatives | `%`, `fr`, `rem` i `vw` s'adapten millor que els píxels fixos |
| Imatge fluïda     | `background-size: cover` ompli el bloc sense deformar-la      |
