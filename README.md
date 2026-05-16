# usainbluntmx.github.io — Sitio Personal de Richi

> **Diseño:** Minimalista cyberpunk sobrio
> **Inspiración:** mcgee.cat (estructura) + jistro.xyz (card + social grid) + anthonysurfermx.com (terminal aesthetic)
> **Stack:** HTML + CSS + vanilla JS (sin frameworks, sin dependencias)

## Arquitectura

```
usainbluntmx.github.io/
├── index.html      (ESP - página principal)
├── en.html         (ENG - versión en inglés)
├── 404.html        (página 404 opcional)
└── README.md       (esta documentación)
```

**Sin build step.** Sin npm. Sin node_modules. Sin React. Sin frameworks i18n.

## Paleta

| CSS Var         | Color    | Propósito          |
|-----------------|----------|--------------------|
| `--bg`          | `#0A0A0A` | Fondo principal    |
| `--surface`     | `#111111` | Tarjeta About      |
| `--border`      | `#1A1A1A` | Separadores/grid   |
| `--text`        | `#E0E0E0` | Texto principal    |
| `--accent`      | `#00FFAA` | Verde neón (único) |

Un solo color de acento (verde terminal/neón). Sin azules, sin naranjas, sin secondarios.

## Influencias y decisiones de diseño

### De mcgee.cat:
- **HTML estático** — sin frameworks, carga instantánea
- **Multi-idioma con hreflang** — un archivo por idioma, no un framework i18n
- **Una sola columna** — máxima legibilidad, sin navegación compleja
- **Links en contexto** — no hay "Links" page, los enlaces están en el flujo
- **Mínimo absoluto** — sin hero, sin footer legal, sin newsletter, sin dark mode toggle

### De jistro.xyz:
- **Card/about pattern** — tarjeta con border-radius, fondo surface, contenido centrado
- **Social links como grid** — cada link es una celda clickeable con icono SVG + texto + handle
- **Jerarquía** — identidad → tagline → ubicación → about → enlaces
- **Ubicación como dato de identidad** — "🇲🇽 México" al mismo nivel que "Full Stack Developer"

### De anthonysurfermx.com:
- **Terminal aesthetic sobria** — command prompt ($ ~/whoami), cursor parpadeante
- **Paleta oscura de 4 colores** — fondo negro, texto gris, un solo acento
- **Headers como comandos UNIX** — `// ENLACES` como label de sección
- **Cero border-radius en social grid** — solo en la tarjeta About se permite radio
- **Sin imágenes decorativas** — todo es texto + SVGs inline

## Cyberpunk sobrio: qué significa

Cyberpunk sin ser estridente:
- ✅ Fondo negro absoluto
- ✅ Acento verde neón único (sin azules/magentas/amarillos)
- ✅ Línea de glow sutíl (box-shadow en glow-line) 
- ✅ Cursor parpadeante estilo terminal
- ❌ Sin gradientes neón estridentes
- ❌ Sin animaciones excesivas
- ❌ Sin glitch effects
- ❌ Sin imágenes cyberpunk decorativas

## Multi-idioma

- `index.html` = español (por defecto)
- `en.html` = inglés
- Switcher en la parte superior izquierda
- Etiquetas `hreflang` correctas en el `<head>`
- `x-default` apunta a español

Las traducciones se manejan con un JSON inline y `data-i18n` attributes. Sin peticiones HTTP adicionales, sin async loading.

## Responsive

- Desktop: grid de 2 columnas en social links
- Mobile (<640px): grid colapsa a 1 columna
- `clamp()` en el h1 para escalar tipo entre 1.5rem y 2rem
- Padding se reduce en mobile

## Cómo modificar

**Para cambiar contenido:**
1. Editar el objeto `i18n` en el script
2. Las claves (`tagline`, `about`, etc.) están mapeadas a `data-i18n` attributes
3. El HTML base está en español, el script inyecta inglés

**Para redes sociales:**
1. Editar los `<a>` en `.social-grid`
2. Cambiar href, texto, y handle
3. El SVG del icono se asigna automáticamente por detección de dominio

## Deploy (GitHub Pages)

1. Repo: `usainbluntmx.github.io`
2. Subir `index.html`, `en.html`, `404.html`
3. Settings → Pages → Source: main branch / (root)

El sitio queda disponible en `https://usainbluntmx.github.io/`
