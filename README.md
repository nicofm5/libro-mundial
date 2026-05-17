# ⚽ Mi Libro del Mundial 2026 — Web App Interactiva

Aplicación web para niños de 1° y 2° grado basada en el libro físico del Mundial 2026.

## Cómo abrir

### Opción 1 — Sin servidor (más fácil)
Doble clic en `index.html`. Funciona directamente en Chrome, Edge o Firefox.

> **Nota:** Google Fonts requiere internet. Sin conexión, el texto sigue siendo legible con fuentes de sistema.

### Opción 2 — Servidor local con Python
```bash
# En la carpeta del proyecto:
python -m http.server 8080
# Abrir: http://localhost:8080
```

### Opción 3 — Con Node.js / npx
```bash
npx serve .
# O: npx http-server -p 8080
```

## Actividades incluidas (15 en total)

| # | Actividad | Tipo | Estrellas |
|---|-----------|------|-----------|
| 1 | 📝 Mi Portada | Formulario | — |
| 2 | 🌎 Países Anfitriones | Tarjetas con flip | — |
| 3 | 🔢 ¿Cuántos Equipos? | Informativa | — |
| 4 | 📋 El Fixture | Grupos interactivos | — |
| 5 | 🔍 El Intruso | **Juego** (4 rondas) | ⭐⭐⭐ |
| 6 | 👕 Grandes Selecciones | **Quiz** (6 camisetas) | ⭐⭐⭐ |
| 7 | ⭐ ¿Quién es este Jugador? | **Quiz** (12 jugadores) | ⭐⭐⭐⭐⭐ |
| 8 | 🔤 Rompecabezas de Sílabas | **Puzzle táctil** (12 países) | ⭐⭐⭐⭐ |
| 9 | 🏟️ Las Sedes | Tarjetas con flip | — |
| 10 | 🏆 Los Campeones | **Quiz** (8 campeones) | ⭐⭐ |
| 11 | 📅 ¿En qué año ganó? | **Matching** | ⭐⭐⭐ |
| 12 | 🤝 Unir Jugadores | **Matching** | ⭐⭐⭐ |
| 13 | ⚽ Mi Equipo Ideal | Formulario | — |
| 14 | 🗓️ Eliminatorias | Bracket rellenable | — |
| 15 | 🎉 ¡La Gran Final! | Registro del campeón | — |

## Características técnicas

- **SPA** — Single HTML file, sin dependencias externas
- **Mobile-first** — Optimizada para tablets y celulares (hitboxes 52px+)
- **LocalStorage** — El progreso se guarda automáticamente
- **Sin backend** — Funciona offline (sin las fuentes de Google)
- **Gamificación** — Sistema de estrellas, confetti y sonidos al acertar
- **Accesibilidad** — Fuentes grandes (mín. 18px), botones gigantes, feedback inmediato
