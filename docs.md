# docs.md — Documentación Técnica

## Rebel Ltda. — Sitio Web

> Este archivo es actualizado por Claude Code al final de cada sesión de trabajo.

---

## Estado del proyecto

| Sección          | Estado        | Notas |
|------------------|---------------|-------|
| Estructura base  | ✅ Completo   | index.html, css/styles.css, js/main.js |
| Navbar           | ✅ Completo   | Fijo, blur al scroll, hamburguesa mobile, Videos deshabilitado |
| Hero             | ✅ Completo   | Dos columnas, stats, grilla 2×2 de productos destacados |
| Marcas           | ✅ Completo   | Franja blanca con 6 marcas y país de origen |
| Catálogos        | ✅ Completo   | catalogos.html — 7 tarjetas con PDFs reales |
| Productos        | ✅ Completo   | productos.html + 5 páginas individuales |
| Videos           | 🚫 En pausa   | Cliente aún no tiene los videos nuevos listos (2026-04-12) |
| Contacto         | ✅ Completo   | contacto.html — formulario + info + WhatsApp |
| Footer           | ✅ Completo   | En todas las páginas — logo, links, teléfono, WhatsApp, email |
| WhatsApp flotante| ✅ Completo   | En todas las páginas — botón verde fijo esquina inferior derecha |
| Responsivo       | ✅ Completo   | Revisado en Prompt 6 — mobile 375px y tablet 900px |
| GitHub           | ✅ Completo   | Repositorio en github.com/tbellnazer3-cmyk/Rebel — rama main |

---

## Archivos del proyecto

### Páginas HTML (9 archivos)

| Archivo | Descripción |
|---------|-------------|
| `index.html` | Página principal — Hero + Marcas |
| `catalogos.html` | Catálogos PDF — 7 tarjetas |
| `productos.html` | Grilla de 5 productos |
| `drill-out.html` | Página individual — Drill Out |
| `insertos-autofrenos.html` | Página individual — Insertos y Autofrenos |
| `nes-external.html` | Página individual — NES External Thread Repair |
| `nes-internal.html` | Página individual — NES Internal Thread Repair |
| `re-grip.html` | Página individual — Re-Grip |
| `contacto.html` | Formulario de contacto + información |

### Estilos y Scripts

| Archivo | Descripción |
|---------|-------------|
| `css/styles.css` | Todos los estilos globales del sitio |
| `js/main.js` | Navbar scroll blur + hamburguesa mobile |

### Skills reutilizables (`skills/`)

| Archivo | Descripción |
|---------|-------------|
| `skills/navbar.html` | Snippet del navbar |
| `skills/hero.html` | Snippet del hero |
| `skills/catalog-card.html` | Tarjeta de catálogo PDF |
| `skills/product-page.html` | Template de página individual de producto |
| `skills/footer.html` | Snippet del footer (actualizado con datos reales) |

### Recursos

| Carpeta | Contenido |
|---------|-----------|
| `catalogos/` | 7 PDFs: AVK, Ducarbo, Recoil (×2), YG-1 (×2), Warren & Browne |
| `productos/` | 5 imágenes JPG de productos |

---

## Decisiones técnicas

### Stack elegido
HTML + CSS + JS puro, sin frameworks. Decisión tomada para mantener el sitio liviano, fácil de mantener y sin dependencias externas.

### Tipografía
Barlow Condensed (weight 400 — delgado y refinado) para títulos, Barlow para cuerpo. Cargada desde Google Fonts.

### Paleta de colores
- `#0e0e0e` — fondo Hero y Navbar (casi negro)
- `#080808` — fondo Footer
- `#ffffff` — secciones claras (Catálogos, Productos, Contacto)
- `#C8200A` — rojo acento Rebel
- `#111111` — texto principal sobre fondo blanco
- `#666666` — texto secundario / muted

### Estructura de páginas
Sitio multi-página (no single page app). Cada sección principal tiene su propio archivo HTML:
- `index.html` → Hero
- `catalogos.html` → Catálogos
- `productos.html` + páginas individuales → Productos
- `contacto.html` → Contacto

### Imágenes de productos
Almacenadas en `/productos/` (no en `/img/productos/` como estaba previsto originalmente).
Todas tienen `alt` descriptivo y `loading="lazy"` para performance.

### Formulario de contacto
El `<form>` en `contacto.html` tiene `action="#"` — requiere conectar con Formspree u otro servicio antes de publicar.

### Responsivo
- Tablet (≤900px): hero, product-page-layout y contact-layout colapsan a 1 columna
- Mobile (≤640px): navbar hamburguesa, secciones en 1 columna, WhatsApp solo ícono

---

## Decisiones del cliente

### Videos — en pausa (2026-04-12)
El cliente no tiene los videos nuevos listos. El link "Videos" en el navbar está visible pero deshabilitado con tooltip "Próximamente". No se creará `videos.html` hasta que el cliente entregue el material. El TODO está comentado en el navbar de todos los HTML.

---

## Sesiones de trabajo

### Sesión 1 — Prompts 1 al 5 (2026-04-12)

**Prompt 1 — Estructura base:**
- `index.html`, `css/styles.css`, `js/main.js`
- Navbar fijo con blur al scroll y menú hamburguesa
- Hero dos columnas: badge + título weight 400 + descripción + stats + grilla 2×2

**Prompt 2 — Marcas y Catálogos:**
- Franja de marcas (Recoil, Sutton, Ducarbo, Warren & Browne, YG-1, AVK)
- `catalogos.html` con 7 tarjetas usando nombres exactos de los PDFs en `/catalogos/`
- Skill: `catalog-card.html`

**Prompt 3 — Productos:**
- `productos.html` — grilla de 5 tarjetas con imágenes reales desde `/productos/`
- 5 páginas individuales con layout imagen sticky + info columna derecha
- Skill: `product-page.html`

**Prompt 4 — Videos deshabilitado:**
- Link "Videos" apagado en navbar con tooltip "Próximamente" en los 9 HTML
- Decisión del cliente: sin material de video disponible

**Prompt 5 — Contacto y Footer:**
- `contacto.html` — dos columnas, formulario completo
- Footer oscuro (`#080808`) en las 9 páginas
- Botón WhatsApp flotante (`#25D366`) en las 9 páginas
- Skill: `footer.html`

**Cierre de sesión día 1 (2026-04-12):**
- Repositorio GitHub creado: https://github.com/tbellnazer3-cmyk/Rebel
- Push exitoso a rama `main`
- GitHub Pages disponible para activar desde Settings → Pages

### Sesión 2 — Prompt 6 (2026-04-14)

**Prompt 6 — Revisión final:**

**Bugs corregidos:**
- `index.html`: botón "Ver productos" apuntaba a `#productos` (hash inexistente) → corregido a `productos.html`
- 5 páginas de producto: CTA "Contáctanos por este producto" apuntaba a `index.html#contacto` → corregido a `contacto.html`

**Responsivo mejorado (css/styles.css):**
- Tablet (≤900px): `.product-page-layout` y `.contact-layout` ahora colapsan a 1 columna
- Mobile (≤640px): `.productos-grid` colapsa explícitamente a 1 columna; `.section` padding reducido a 4rem; `.page-section` padding-top reducido

**Consistencia del footer:**
- Agregados teléfono (+56 2 2672 8216) y WhatsApp (+56 9 9874 2476) en el footer de las 9 páginas
- Copyright actualizado de 2025 a 2026
- `skills/footer.html` actualizado con los mismos datos

**Performance:**
- `loading="lazy"` agregado a las 5 imágenes en `productos.html`
- `loading="lazy"` agregado a la imagen en cada una de las 5 páginas individuales de producto

**Skills verificadas:**
- Todas las skills en `/skills/` están creadas y actualizadas

**Git — cierre sesión 2 (2026-04-14):**
- Push a https://github.com/tbellnazer3-cmyk/Rebel — rama main

---

## Datos de contacto reales

| Campo | Valor |
|-------|-------|
| Teléfono | +56 2 2672 8216 |
| WhatsApp | +56 9 9874 2476 |
| Email | contacto@rebel.cl |
| Ciudad | Santiago, Chile |
| Fundación | 1980 |

---

## Variables de entorno (.env)

> El archivo `.env` nunca se sube a GitHub. Está en `.gitignore`.

```
# Agregar cuando corresponda
# CONTACT_EMAIL=contacto@rebel.cl
# WA_NUMBER=56998742476
```

---

## Pendientes del cliente

1. Contenido real de cada página de producto (descripciones y características)
2. Videos nuevos para habilitar la sección Videos
3. Dirección física exacta para la página de Contacto
4. Confirmar email de contacto (actualmente placeholder: contacto@rebel.cl)
5. Configurar formulario de contacto con Formspree u otro servicio
6. Activar dominio personalizado rebel.cl en GitHub Pages (Settings → Pages → Custom domain)

---

## Próximos pasos

### Activar rebel.cl en GitHub Pages
1. En el repositorio GitHub → Settings → Pages
2. Source: rama `main`, carpeta `/ (root)`
3. Custom domain: ingresar `rebel.cl`
4. En el registrador de dominio, agregar registro DNS tipo CNAME: `tbellnazer3-cmyk.github.io`
5. Activar "Enforce HTTPS"

### Configurar formulario de contacto (Formspree)
1. Ir a formspree.io y crear cuenta gratuita
2. Crear nuevo formulario, copiar el endpoint (ej: `https://formspree.io/f/XXXXX`)
3. En `contacto.html`, reemplazar `action="#"` por la URL de Formspree

---

## Problemas conocidos

_Ninguno._
