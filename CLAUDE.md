# Mi Libro del Mundial 2026

Aplicación interactiva infantil para aprender sobre el Mundial 2026. Hosted on GitHub Pages.

## Live URL
https://nicofm5.github.io/libro-mundial

## Stack
- Single-file SPA: `index.html` (~2700 lines, todo el HTML/CSS/JS embebido)
- Firebase Realtime Database + localStorage (multi-user con login)
- jsPDF (CDN v2.5.1) para generar el certificado PDF
- Sin build step. Cualquier cambio se ve haciendo refresh del index.

## Estructura de actividades
- **30 estrellas totales** distribuidas en 8 juegos
- Modal "SOS CAMPEÓN DEL MUNDO" se dispara cuando `S.stars >= TOTAL_STARS` (una vez por sesión, vía sessionStorage)

## File paths críticos
- Source de la app: `./index.html`
- **Preview mirror**: `C:\Users\Nicolas\Documents\web-natalia-agullo\index.html` — copiar después de cada edit con `cp` para que el servidor de preview lo vea
- Imágenes: `./img/`

## Workflow de Pull Requests

GitHub CLI (`gh`) está instalado vía winget en `~/AppData/Local/Microsoft/WinGet/Packages/GitHub.cli_*/bin/gh.exe`. Un `~/.bashrc` configurado en el sistema:
1. Agrega `gh` al PATH
2. Auto-popula `GH_TOKEN` desde Git Credential Manager (el PAT almacenado tiene scope `repo`, suficiente para PRs en repos personales)

Esto significa que en cualquier sesión nueva de bash, `gh pr create` funciona sin pasos previos.

### Cuando el usuario pide `/create-pr`:

**SI los cambios todavía no se commitearon a main:**
```bash
git checkout -b feature/short-description
git add <files>
git commit -m "..."
git push -u origin feature/short-description
gh pr create --title "..." --body "..."
```

**SI los cambios ya están en main** (caso común porque GitHub Pages auto-deploya): no se puede crear PR retroactivo sin reescribir historia (rompe el sitio live). Explicar al usuario que los commits ya están desplegados y proponer trabajar en feature branches a partir de ahora.

### Buenas prácticas para futuras sesiones

- Si el usuario pide cambios y se espera que pasen por PR, **NO commitear directo a main**. Crear feature branch primero.
- Si el usuario quiere ver cambios live inmediatamente sin PR, commit directo a main funciona (Pages auto-deploya en ~1 min).
- Preguntar al usuario al inicio de la sesión si el flujo es directo-a-main o vía-PR cuando no esté claro.

## Notas técnicas del index.html

- `TEAMS_48`: 48 selecciones agrupadas por letra de grupo (A-L)
- `FIXTURE_MATCHES`: 72 partidos fase de grupos con horarios Argentina (UTC-3), fuente Infobae
- `GOLEADORES_ROUNDS`: 7 mundiales con Bota de Oro + 3 distractores cada uno (figuras reales del mismo Mundial). Fotos vía URLs de Wikipedia/Commons
- `ACTIVITIES`: array que define el grid del home. `game:true` = suma estrellas; `game:false` = informativa
- Estado del usuario: `S` (global), persistido en Firebase + localStorage
- `defaultState()`: cuando agregues un juego nuevo, agregá su entrada de estado acá
