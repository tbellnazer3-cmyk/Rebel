# CLAUDE.md — Instrucciones para Claude Code

## Contexto del proyecto

Sitio web para **Rebel Ltda.**, empresa industrial chilena fundada en 1980.  
Lee el `README.md` primero para entender el proyecto completo antes de comenzar cualquier tarea.

---

## Reglas del proyecto

### 1. Skills reutilizables
Si realizas una tarea **dos o más veces**, debes extraerla como una skill reutilizable en `/skills/`.

```
skills/
├── navbar.html         # Componente de navegación
├── product-card.html   # Tarjeta de producto
├── catalog-card.html   # Tarjeta de catálogo PDF
└── footer.html         # Pie de página
```

Cada skill es un snippet autocontenido con su HTML, CSS y JS necesario. Cuando lo reutilices, impórtalo o cópialo desde ahí — nunca lo reescribas de cero.

### 2. Separar el trabajo en prompts distintos

No intentes construir todo el sitio en un solo paso. Divide el trabajo así:

| Prompt | Tarea |
|--------|-------|
| 1 | Estructura base: `index.html`, `css/styles.css`, `js/main.js`, navbar y hero |
| 2 | Sección de marcas y catálogos (con PDFs en `/catalogos/`) |
| 3 | Sección de productos (grilla de 6 tarjetas) |
| 4 | Sección de videos (thumbnails YouTube) |
| 5 | Sección de contacto + footer |
| 6 | Revisión final: responsivo, performance, links |

Al terminar cada prompt, confirma con el usuario antes de continuar al siguiente.

### 3. Actualización diaria de docs.md y GitHub

**Al final de cada sesión de trabajo**, antes de cerrar, debes:

1. Actualizar `docs.md` con lo realizado (secciones completadas, decisiones tomadas, problemas encontrados)
2. Hacer commit con mensaje descriptivo:
   ```bash
   git add .
   git commit -m "feat: descripción de lo que se hizo hoy"
   git push origin main
   ```
3. Confirmar al usuario que el push fue exitoso

---

## Configuración de GitHub (primera vez)

Si el usuario no tiene cuenta ni repositorio, guíalo paso a paso:

### Paso 1 — Crear cuenta en GitHub
1. Ir a [github.com](https://github.com)
2. Clic en **Sign up**
3. Ingresar email, contraseña y nombre de usuario
4. Verificar el email
5. Elegir el plan **Free**

### Paso 2 — Crear repositorio
1. En GitHub, clic en **New repository** (botón verde)
2. Nombre: `rebel-web`
3. Descripción: `Sitio web Rebel Ltda. — rediseño moderno`
4. Visibilidad: **Private** (recomendado mientras está en desarrollo)
5. **No** inicializar con README (ya tenemos el nuestro)
6. Clic en **Create repository**

### Paso 3 — Conectar el proyecto local
Ejecutar estos comandos en la terminal dentro de la carpeta `rebel-web/`:

```bash
git init
git add .
git commit -m "feat: inicio del proyecto rebel.cl"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/rebel-web.git
git push -u origin main
```

Reemplazar `TU_USUARIO` con el nombre de usuario de GitHub.

### Paso 4 — Verificar
Abrir `https://github.com/TU_USUARIO/rebel-web` en el browser y confirmar que los archivos están ahí.

---

## WAT Framework (Workflows, Agents, Tools)

Este proyecto usa el framework WAT para separar razonamiento de ejecución.

### Layer 1: Workflows
- Instrucciones en `workflows/` (archivos Markdown)
- Cada workflow define objetivo, inputs, herramientas, outputs y casos borde
- No crear ni sobreescribir workflows sin pedir permiso al usuario

### Layer 2: Agents (tu rol)
- Leer el workflow relevante
- Ejecutar herramientas en el orden correcto
- Manejar errores con gracia
- Preguntar cuando algo no está claro

### Layer 3: Tools
- Scripts en `tools/` para ejecución determinística
- Credenciales y API keys solo en `.env` — nunca en otro lugar
- Si un tool falla, leer el error completo, corregir y volver a probar

### Loop de mejora
Cuando algo falla:
1. Identificar qué falló y por qué
2. Corregir el tool o workflow
3. Verificar que la corrección funciona
4. Documentar el aprendizaje en `docs.md`
5. Continuar con el sistema más robusto

---

## Estructura de archivos

```
rebel-web/
├── index.html
├── README.md
├── CLAUDE.md           # Este archivo
├── docs.md             # Documentación técnica (actualizar cada día)
├── css/
│   └── styles.css
├── js/
│   └── main.js
├── catalogos/          # PDFs por marca
├── img/                # Imágenes y logos
├── skills/             # Snippets reutilizables
├── tools/              # Scripts Python de ejecución
├── workflows/          # SOPs en Markdown
└── .env                # API keys (nunca subir a GitHub)
```

**Agregar al `.gitignore`:**
```
.env
.tmp/
node_modules/
*.DS_Store
```

---

## Estilo de código

- **Indentación:** 2 espacios
- **Comentarios:** en español
- **Nombres de clases CSS:** kebab-case (ej: `product-card`)
- **Nombres de archivos:** kebab-case (ej: `catalog-card.html`)
- **Commits:** en inglés, con prefijo (`feat:`, `fix:`, `style:`, `docs:`)

---

## Diseño — reglas visuales

- Estilo: minimalista, moderno, industrial
- Fondo principal: `#0e0e0e` (oscuro)
- Acento: `#C8200A` (rojo)
- Sección de marcas: fondo `#ffffff`
- Tipografía: Barlow Condensed (títulos, uppercase) + Barlow (cuerpo)
- Sin frameworks CSS — todo CSS puro
- El sitio debe ser **100% responsivo**
- Referencia visual: prototipo aprobado por el cliente (hero oscuro, franja blanca de marcas, tarjetas de productos)

---

## Referencia

- Sitio actual: [rebel.cl](https://rebel.cl)
- README del proyecto: `README.md`
- Documentación técnica: `docs.md`
