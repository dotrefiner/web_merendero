# Merendero "En Construcción"

Sitio web de una sola página para un merendero comunitario. Está pensado como
**punto de partida para un taller de HTML y CSS**: usa recursos básicos,
tiene comentarios en español y no necesita frameworks, instalación ni
JavaScript.

---

## Cómo ver el sitio

1. Abrí la carpeta del proyecto.
2. Hacé doble clic en `index.html` (se abre en el navegador).
3. Para verlo como si estuviera publicado, abrí una terminal en esta carpeta y ejecutá:

   ```bash
   python3 -m http.server 8000
   ```

   Después entrá a <http://localhost:8000>.

> El mapa y las tipografías de Google necesitan internet. El resto del sitio
> funciona sin conexión porque las fotos están guardadas en `assets/`.

---

## Archivos del proyecto

```
merendero/
├── index.html          → todo el contenido y las secciones
├── styles.css          → colores, tipografías, grillas y responsive
├── assets/             → fotos, favicon e imágenes
│   ├── hero.jpg
│   ├── nosotros.jpg
│   ├── viandas.jpg
│   ├── apoyo.jpg
│   ├── comunidad.jpg
│   ├── insumos.jpg
│   └── favicon.svg
└── README.md           → esta guía
```

**No hay páginas separadas.** La navegación usa enlaces con anclas
(`#nosotros`, `#donar`, etc.) y todo el contenido vive en `index.html`.

---

## Datos que hay que reemplazar

Todos los textos y datos son de ejemplo. En el HTML están marcados con
comentarios `<!-- REEMPLAZAR: ... -->`. La lista completa:

| Dato | Dónde está | Valor actual |
|---|---|---|
| Nombre del merendero | Header, footer y textos | Merendero En Construcción |
| Historia | Sección "Nosotros" | Texto de ejemplo |
| Alias y CBU | Sección "Donar" | `merendero.enconstruccion` / ceros |
| Link de Mercado Pago | Botón de donación | URL de ejemplo |
| Teléfono / WhatsApp | Donar, contacto y footer | 11 5555-5555 |
| Correo | Donar, contacto y footer | hola@merenderoenconstruccion.org |
| Instagram y Facebook | Contacto y footer | Enlaces a la portada de cada red |
| Dirección | Ubicación, hero y footer | Obelisco, CABA (ejemplo) |
| Horarios y cómo llegar | Sección "Ubicación" | Datos de ejemplo |
| Mapa | iframe de Google Maps | Obelisco |
| Fotos | `assets/` | Fotos libres de Unsplash |

### Cómo cambiar el mapa

Buscá el bloque `<div class="map">` en `index.html` y reemplazá el `src` del
iframe por la ubicación real. Una forma sencilla es abrir Google Maps, buscar
el lugar, ir a **Compartir → Insertar un mapa** y copiar el código.

---

## Cómo personalizar el diseño

### Colores

Todos los colores están al principio de `styles.css`, dentro de `:root`:

```css
:root {
  --cream: #FBF7EE;       /* fondo general */
  --green: #2E5E45;       /* verde principal */
  --green-dark: #1D3B2C;  /* secciones oscuras */
  --green-soft: #E6EDDF;  /* fondo de "Qué hacemos" */
  --yellow: #E9B44C;      /* botones y detalles */
  --ink: #26302A;         /* texto principal */
  --muted: #5C6B60;       /* texto secundario */
}
```

Cambiar esos valores alcanza para transformar todo el sitio.

### Tipografías

Se cargan desde Google Fonts en el `<head>`:

- **Fraunces** para títulos.
- **Inter** para párrafos y navegación.

Si querés usar otras, cambiá el `<link>` en el HTML y las familias en
`styles.css` (`font-family`). Siempre conviene dejar una fuente de respaldo
como `Georgia` o `system-ui`.

### Fotos

Reemplazá los archivos de `assets/` manteniendo el mismo nombre. Si usás
otras medidas, el CSS las recorta con `object-fit: cover`; lo ideal es que
sean horizontales de al menos 1200 px (la portada, 1800 px).

### Menú hamburguesa

Funciona con HTML y CSS, sin JavaScript: un `<input type="checkbox">` oculto
y un `<label>` con las tres líneas. Cuando el checkbox se marca, el CSS
muestra el menú y convierte las líneas en una X.

**Limitación:** al tocar un enlace del menú, la página hace scroll pero el
menú queda abierto hasta que se vuelve a tocar la X. Es una buena consigna
para resolver más adelante con unas pocas líneas de JavaScript.

---

## Accesibilidad incluida

- HTML semántico (`header`, `nav`, `main`, `section`, `footer`).
- Enlace "Saltar al contenido" para navegar con teclado.
- Foco visible en todos los enlaces y botones.
- Textos alternativos en las imágenes.
- Contraste cuidado y tamaños de texto adaptables.
- Respeto por la preferencia `prefers-reduced-motion`.

Al agregar contenido, mantené estos criterios: imágenes con `alt`, títulos
en orden (`h1`, `h2`, `h3`) y enlaces con textos claros.

---

## Desafíos para el taller

1. **Cambiar la identidad:** probar otra paleta en `:root` y otro par de
   tipografías.
2. **Sumar una sección:** por ejemplo "Noticias" o "Testimonios", con su
   enlace en el menú y en el pie.
3. **Reemplazar las fotos:** usar imágenes propias del merendero, ajustando
   los `alt`.
4. **Mejorar el menú:** hacer que se cierre al elegir una sección (una pista:
   unas pocas líneas de JavaScript o el truco de `:target`).
5. **Sumar un formulario:** un formulario de contacto con `mailto:` o con un
   servicio externo.
6. **Crear una galería:** una grilla de fotos con `display: grid`.
7. **Agregar modo oscuro:** con variables de CSS y `prefers-color-scheme`.
8. **Publicar el sitio:** subirlo a GitHub Pages, Netlify o Vercel.

---

## Créditos de las fotos

Todas las imágenes son de [Unsplash](https://unsplash.com) y se usan bajo la
[Licencia de Unsplash](https://unsplash.com/license). Son fotos de ejemplo:
conviene reemplazarlas por imágenes reales del merendero.

| Archivo | Foto | Autor/a |
|---|---|---|
| `hero.jpg` | [Woman cooking in a large metal pot outdoors](https://unsplash.com/photos/-Z78G569Vdo) | Richard Saunders |
| `nosotros.jpg` | [Woman cooking over an open fire outdoors](https://unsplash.com/photos/y6IfFeYjDhc) | Theresa Ude |
| `viandas.jpg` | [People serving food from a foil tray](https://unsplash.com/photos/7_P88Qkv0gU) | Cohen Berg |
| `apoyo.jpg` | [Children learning and creating art](https://unsplash.com/photos/FxzoAr9QBKw) | Ahmadreza Rezaie |
| `comunidad.jpg` | [People around table](https://unsplash.com/photos/K4XHVhJk6kw) | Zach Reiner |
| `insumos.jpg` | [Fresh vegetables on a market stall](https://unsplash.com/photos/Zaiuy5dKeCk) | Shelley Pauls |

El mapa es un iframe de Google Maps y las tipografías pertenecen a Google
Fonts.

---

## Sitio de ejemplo

Este proyecto es una maqueta educativa. Los datos de contacto, la dirección,
las cuentas bancarias y las fotografías son ficticios o de ejemplo. Antes de
publicarlo, reemplazalos por información real y verificá que las imágenes
puedan usarse.
