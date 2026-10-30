# Banderas de hinchada por club

Si un club tiene imagen acá, la hinchada (local y visitante) la usa en las
banderas que flamean y en los trapos colgados del alambrado. Si no tiene,
sigue con el dibujo de colores de siempre.

## Qué mandar

| Archivo | Para qué | Tamaño | Proporción |
|---|---|---|---|
| `<club>.png` | Bandera de mano (y trapo, si no hay uno propio) | 384 × 256 px | 3:2 apaisada |
| `<club>-trapo.png` | Trapo largo (opcional) | 1024 × 128 px | 8:1 apaisada |

- **Fondo**: lleno, sin transparencia (es tela). Nada importante pegado a
  los bordes: se recorta un poco.
- **Diseño**: colores planos y formas grandes. Se ve chico y pixelado:
  textos de pocas letras y bien gruesos.
- **Formato**: PNG o WebP (`<club>.webp`). Menos de 60 kB cada uno.
- **Nombre**: el mismo slug que `public/kits/` (`boca`, `river`,
  `san-lorenzo`, `newells`, `estudiantes-rio-cuarto`…).
- **Contenido**: sin escudos oficiales, marcas ni caras (regla del juego).
  Colores, rayas, frases de aliento: sí.

## Cómo darla de alta

Sumar la entrada a `manifest.json` (así el juego no pide archivos que no
existen):

```json
["boca", "boca-trapo", "river.webp"]
```

Sin extensión = `.png`. Con `.webp`, se pone la extensión.
