# Rebel Ltda. — Sitio Web

Rediseño moderno del sitio web de **Rebel Ltda.**, empresa industrial chilena fundada en 1980. Importación y distribución de herramientas de precisión para mantención de maquinaria.

---

## Objetivo

Reemplazar el sitio WordPress del año 2013 por un sitio estático moderno, minimalista y profesional. Mismas funciones que el sitio actual (catálogos, productos, videos, contacto), con diseño completamente actualizado.

---

## Stack

- **HTML5 + CSS3 + JavaScript** puro — sin frameworks
- **Google Fonts:** Barlow Condensed (títulos) + Barlow (cuerpo)
- **Hosting:** por definir (sugerido: Netlify o GitHub Pages)
- **Control de versiones:** GitHub

---

## Identidad visual

| Elemento     | Valor                        |
|--------------|------------------------------|
| Rojo         | `#C8200A`                    |
| Gris oscuro  | `#0e0e0e`                    |
| Blanco       | `#ffffff`                    |
| Estilo       | Minimalista, moderno, industrial |
| Tipografía   | Barlow Condensed + Barlow    |

---

## Estructura del proyecto

```
rebel-web/
├── index.html          # Página principal
├── README.md           # Este archivo
├── CLAUDE.md           # Instrucciones para Claude Code
├── docs.md             # Documentación técnica (actualizar cada día)
├── css/
│   └── styles.css      # Estilos globales
├── js/
│   └── main.js         # Scripts globales
├── catalogos/          # PDFs de catálogos por marca
│   ├── recoil.pdf
│   ├── sutton.pdf
│   └── ...
├── img/                # Imágenes, logos, íconos
├── skills/             # Snippets reutilizables (ver CLAUDE.md)
└── workflows/          # SOPs del proyecto (ver CLAUDE.md)
```

---

## Secciones del sitio

1. **Navbar** — Logo REBEL + links: Catálogos, Productos, Videos, Contáctanos
2. **Hero** — Frase corta, descripción breve, 3 stats (44+ años, 6 marcas, 100% stock), botones CTA
3. **Marcas** — Franja blanca con las 6 marcas representadas
4. **Catálogos** — Tarjetas descargables por marca (PDF)
5. **Productos** — Grilla de 6 productos con descripción
6. **Videos** — Sección con thumbnails de YouTube (reemplaza videos viejos)
7. **Contáctanos** — Botón WhatsApp + formulario de correo
8. **Footer** — Logo, datos de contacto, año

---

## Marcas representadas

| Marca           | País      | Productos principales                          |
|-----------------|-----------|------------------------------------------------|
| Recoil          | Australia | Insertos de rosca, recuperación de roscas      |
| Sutton          | Australia | Brocas HSS, machos de mano y máquina           |
| Ducarbo         | Dinamarca | Brocas de carburo de tungsteno                 |
| Warren & Browne | Australia | Llaves de torque, repuestos originales         |
| YG-1            | Corea     | Brocas y machos HSS cobalto, nitruro titanio   |
| AVK             | USA       | Remaches tuerca y perno                        |

---

## Cómo correr el proyecto localmente

```bash
# Opción 1 — con Python
python -m http.server 8000

# Opción 2 — con Node.js
npx serve .

# Luego abrir en el browser:
# http://localhost:8000
```

---

## Referencia

- Sitio actual: [rebel.cl](https://rebel.cl)
- Diseño de referencia: prototipo aprobado en conversación inicial (fondo oscuro, rojo #C8200A, franja de marcas en blanco)
