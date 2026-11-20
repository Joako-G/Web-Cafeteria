# Sitio de demostración — inventario de errores plantados

> **Uso exclusivo del docente.** Este archivo está fuera de la carpeta `sitio-demo/`
> a propósito: si se copia el proyecto completo para auditarlo con IA, estas notas
> no viajan con él.

Proyecto: `sitio-demo/` — "La Molienda", cafetería. Variante 3 (Rústica Artesanal)
del boceto generado con Stitch.

## Límites respetados

El código usa únicamente contenidos de la planificación: estructura de documento,
etiquetas y atributos, jerarquía de títulos, párrafos, listas, enlaces, imágenes,
etiquetas semánticas, y CSS de vinculación, selectores, color, tipografía y
espaciado. **No hay flexbox, grid ni JavaScript.** La única propiedad agregada
respecto de la grilla original es `display: inline-block` en el menú, que ya
decidimos incorporar a la clase 7.

## Errores reales plantados

| ID | Eje de auditoría | Dónde | Qué está mal | Categoría esperada |
|---|---|---|---|---|
| E1 | 1. Estructura | `index.html`, título "Sobre nosotros" | Está marcado como `<h3>` salteando el `<h2>`. Las otras dos secciones sí usan `<h2>`, así que la jerarquía es inconsistente | Error real |
| E2 | 1. Estructura | `index.html`, imagen del croissant | La etiqueta `<img>` no tiene atributo `alt` | Error real |
| E3 | 1. Estructura | `index.html`, menú de navegación | El enlace `href="#contacto"` apunta a un `id` que no existe en el documento | Error real |
| E4 | 2. Semántica | `index.html`, bloque "Cómo llegar" | Usa `<div class="seccion">` donde corresponde `<section>` | Error real |
| E5 | 2. Semántica | `index.html`, bloque final de contacto | Usa `<div class="pie">` donde corresponde `<footer>` | Error real |
| E6 | 2. Semántica | `index.html`, los tres precios | Usa `<b>`, que es presentacional, en lugar de `<strong>` o de ningún énfasis | Mejora |
| E7 | 3. CSS | `estilos.css`, regla `h1` | Falta el punto y coma después de `letter-spacing: 7px`. La declaración se invalida y además se pierde el `margin` que viene después | Error real |
| E8 | 4. Coherencia | `estilos.css`, regla `.destacado` | La clase está declarada en la hoja de estilos y no se usa en ningún elemento del HTML | Error real |

Los errores **E4 y E5 son invisibles en el navegador**: las clases `.seccion` y
`.pie` están estilizadas para verse exactamente igual que `section` y `footer`.
Eso es deliberado y es la mejor demostración de por qué la semántica importa:
no se ve, pero está mal.

## Trampas: código correcto que la IA suele marcar como error

Son las que habilitan la categoría "falso positivo" del acta. Sin ellas, el
ejemplo no puede mostrar un rechazo fundamentado.

| ID | Dónde | Por qué está bien | Qué suele decir la IA |
|---|---|---|---|
| T1 | Las dos imágenes `separador.svg`, con `alt=""` | Es una imagen decorativa. El `alt` vacío es la práctica correcta: indica al lector de pantalla que debe ignorarla. Ponerle texto sería peor | "Falta el texto alternativo de la imagen" |
| T2 | Dirección postal en "Cómo llegar" | `<br>` dentro de un párrafo es el uso legítimo de la etiqueta: separa líneas de un mismo bloque de texto, como una dirección o una estrofa | "No uses `<br>` para maquetar, usá CSS" |
| T3 | Cada producto es un `<li>` con un `<h3>` adentro | Un encabezado dentro de un elemento de lista es válido y adecuado para un catálogo | "Deberías usar `<article>` en lugar de `<li>`" — y `<article>` no se vio en el curso, así que además corresponde al Bloque B |

**No se puede garantizar que la IA pique en las tres.** Si la auditoría sale sin
ningún falso positivo, la evidencia pasa a mostrar la contra-pregunta: repreguntar
el fundamento de un hallazgo y ver si lo sostiene o se desdice.

## Dos observaciones sobre la planificación

1. **`max-width` y `margin: 0 auto` tienen que entrar en la clase 8.** El sitio los
   usa para limitar el ancho del texto a 720 px y centrarlo. Sin eso, en una
   pantalla ancha los párrafos ocupan toda la línea y se vuelven ilegibles. Es la
   decisión de espaciado que más impacto visual tiene y hoy no figura en el
   contenido de la clase.
2. **El menú queda horizontal recién con `display: inline-block`.** Antes de esa
   propiedad, los enlaces se apilan en vertical, igual que en el boceto de Stitch.
   Conviene mostrarlo en ese orden en la clase 7: primero cómo se ve sin la
   propiedad, después con ella.

## Cómo correr la auditoría

Pegar en el prompt de auditoría el contenido completo de `sitio-demo/index.html`
y de `sitio-demo/estilos.css`, en ese orden, indicando el nombre de cada archivo.
No incluir este documento.
