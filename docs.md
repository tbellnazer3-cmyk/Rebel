# docs.md — Documentación Técnica

## Rebel Ltda. — Sitio Web

> Este archivo es actualizado por Claude Code al final de cada sesión de trabajo.

---

## Estado del proyecto

| Sección          | Estado        | Notas |
|------------------|---------------|-------|
| Estructura base  | ✅ Completo   | index.html, css/styles.css, js/main.js |
| Navbar           | ✅ Completo   | Fijo, blur al scroll, hamburguesa mobile — 3 links activos |
| Hero             | ✅ Completo   | Dos columnas, stats, grilla 2×2 de productos destacados |
| Marcas           | ✅ Completo   | Franja blanca con 6 marcas y país de origen |
| Catálogos        | ✅ Completo   | catalogos.html — 7 tarjetas con PDFs reales |
| Productos        | ✅ Completo   | productos.html + 5 páginas individuales |
| Videos           | 🚫 Eliminado  | Removido del navbar por decisión del cliente (2026-04-14) |
| Contacto         | ✅ Completo   | contacto.html — formulario + info con emails reales |
| Footer           | ✅ Completo   | Logo REBEL LTDA., teléfono, WhatsApp, emails reales |
| WhatsApp flotante| ✅ Completo   | En todas las páginas — botón verde fijo esquina inferior derecha |
| Responsivo       | ✅ Completo   | Mobile 375px y tablet 900px revisados |
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
| `skills/navbar.html` | Snippet del navbar (sin Videos, logo REBEL LTDA.) |
| `skills/hero.html` | Snippet del hero |
| `skills/catalog-card.html` | Tarjeta de catálogo PDF |
| `skills/product-page.html` | Template de página individual de producto |
| `skills/footer.html` | Snippet del footer con datos reales |

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

### Logo
`REBEL LTDA.` con el punto final en rojo (`#C8200A`) como acento visual. Font-size 1.45rem, letter-spacing 0.18em en navbar; 1.2rem en footer.

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

### Videos — eliminado (2026-04-14)
El link "Videos" fue eliminado completamente del navbar en las 9 páginas. El CSS de `.nav-disabled` también fue removido. Si en el futuro el cliente entrega material de video, se debe crear `videos.html` y agregar el link nuevamente al navbar.

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

**Cierre sesión 1 (2026-04-12):**
- Repositorio GitHub creado: https://github.com/tbellnazer3-cmyk/Rebel
- Push exitoso a rama `main`

### Sesión 2 — Prompts 6 + ajustes finales (2026-04-14)

**Prompt 6 — Revisión final:**
- CSS: colapso tablet (900px) para product-page-layout y contact-layout
- CSS: 1 columna mobile explícita para productos-grid, padding reducido
- Footer: teléfono (+56 2 2672 8216) y WhatsApp (+56 9 9874 2476) en las 9 páginas
- `loading="lazy"` en las 10 imágenes de producto
- Copyright 2025 → 2026

**Bugs corregidos:**
- Botón "Ver productos" en hero: `#productos` → `productos.html`
- CTA "Contáctanos" en 5 páginas de producto: `index.html#contacto` → `contacto.html`

**Ajustes finales del cliente:**
- Logo actualizado: `REBEL.` → `REBEL LTDA.` en navbar y footer de las 9 páginas
- CSS: font-size y letter-spacing del logo ajustados (1.75rem/0.35em → 1.45rem/0.18em)
- Videos eliminado definitivamente del navbar en las 9 páginas
- CSS de `.nav-disabled` y tooltip eliminados
- Emails corregidos: `contacto@rebel.cl` → `ventas@rebel.cl` + `jbell@rebel.cl` en footer y contacto.html
- skills/navbar.html y skills/footer.html actualizados con todos los cambios

**Cierre sesión 2 (2026-04-14):**
- Sitio completo — v1 lista para publicar
- Push exitoso a https://github.com/tbellnazer3-cmyk/Rebel — rama main

### Sesión 3 — Formulario de contacto (2026-04-14)

**Formspree conectado:**
- `contacto.html`: `action="#"` → `action="https://formspree.io/f/mojyvkpz"`
- Removido atributo `novalidate` — validación HTML5 activa
- Los mensajes del formulario ahora llegan al email configurado en Formspree

**Cierre sesión 3 (2026-04-14):**
- Push exitoso a https://github.com/tbellnazer3-cmyk/Rebel — rama main

### Sesión 4 — Contenido real de productos (2026-06-18)

**Descripciones reales ingresadas en los 5 productos:**
- `drill-out.html` — descripción + 7 características técnicas
- `insertos-autofrenos.html` — descripción + Línea Autofreno como bloque independiente + 7 características + normas
- `nes-external.html` — descripción + 4 características + aplicaciones frecuentes
- `nes-internal.html` — descripción (Studsaver) + 5 características + aplicaciones frecuentes
- `re-grip.html` — descripción + 7 características

**Cierre sesión 4 (2026-06-18):**
- Push exitoso a https://github.com/tbellnazer3-cmyk/Rebel — rama main

---

## Datos de contacto reales

| Campo | Valor |
|-------|-------|
| Teléfono | +56 2 2672 8216 |
| WhatsApp | +56 9 9874 2476 |
| Email ventas | ventas@rebel.cl |
| Email directo | jbell@rebel.cl |
| Ciudad | Santiago, Chile |
| Fundación | 1980 |

---

## Variables de entorno (.env)

> El archivo `.env` nunca se sube a GitHub. Está en `.gitignore`.

```
# Agregar cuando corresponda
# CONTACT_EMAIL=ventas@rebel.cl
# WA_NUMBER=56998742476
```

---

## Pendientes del cliente

1. ~~Contenido real de cada página de producto~~ ✅ Completado (2026-06-18)
2. Dirección física exacta para la página de Contacto
3. ~~Configurar formulario de contacto con Formspree~~ ✅ Conectado (2026-04-14)
4. Activar dominio personalizado rebel.cl en GitHub Pages

---

## Próximos pasos

### Activar rebel.cl en GitHub Pages
1. En el repositorio GitHub → Settings → Pages
2. Source: rama `main`, carpeta `/ (root)`
3. Custom domain: ingresar `rebel.cl`
4. En el registrador de dominio, agregar registro DNS tipo CNAME apuntando a `tbellnazer3-cmyk.github.io`
5. Activar "Enforce HTTPS"

### Configurar formulario de contacto (Formspree) ✅
Endpoint conectado: `https://formspree.io/f/mojyvkpz`
Los mensajes llegan al email configurado en la cuenta Formspree del cliente.

---

## Problemas conocidos

_Ninguno._
