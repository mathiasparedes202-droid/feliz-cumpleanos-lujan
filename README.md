# 🎂 Feliz Cumpleaños, Luján

Una página hecha a mano para celebrar a alguien muy especial. Todo el sitio es un
solo archivo (`public/index.html`): no necesita instalación ni servidor.

**En vivo:** https://feliz-cumpleanos-lujan.mathiasparedes202.workers.dev
**Repo:** https://github.com/mathiasparedes202-droid/feliz-cumpleanos-lujan

## Cómo abrirla

1. Hacé doble clic en `public/index.html` (se abre en tu navegador).
2. Para compartirla, mandale el link de Cloudflare de arriba: funciona en cualquier
   celular sin instalar nada.

## Qué incluye

- **Portada** con su nombre, globos y corazones flotando.
- **Carta** con el mensaje principal.
- **Pastel interactivo**: se soplan las velitas una por una (o todas con el botón) y
  explota el confeti. Después se pueden volver a encender.
- **Galería**: tres marcos tipo polaroid. Las fotos que se cargan **quedan guardadas
  en el navegador** (se comprimen automáticamente para que entren bien).
- **Sección de Spotify** (opcional, ver abajo).
- **Regalo sorpresa**: un sobre que se abre con un mensaje final.
- **Música**: melodía de cumpleaños sintetizada, se prende y apaga con el botón de
  abajo a la derecha. También arranca al abrir el regalo.
- Funciona en celular y computadora, y respeta la opción de "reducir movimiento".

## Personalización

Abrí `public/index.html` con cualquier editor de texto y buscá `PERSONALIZÁ ACÁ`.
Todo el contenido está en un solo objeto:

```js
const CONFIG = {
  nombre: 'Luján',
  intro: '...',             // frase de la portada
  spotify: '',              // link de Spotify (opcional)
  carta: [ '...', '...' ],  // párrafos de la carta
  razones: [ { ico: '🥰', titulo: '...', texto: '...' }, ... ],
  secreto: '...',           // mensaje del regalo
  firma: '...',
  firmaRegalo: '...'
};
```

Cambiá solo lo que está entre comillas y guardá.

## Música de Spotify

Pegá el link de la playlist (o de la canción) en `spotify`:

```js
spotify: 'https://open.spotify.com/track/6xQwzsTwW0GFeYfADodNsc',
```

- Con eso aparece la sección **"Nuestra banda sonora"** con el reproductor, y un
  botón nuevo en la portada.
- Acepta links normales de Spotify y también el formato `spotify:playlist:ID`.
- Si lo dejás vacío (`''`), la sección no aparece y queda solo la melodía del navegador.
- El reproductor necesita internet y que ella tenga sesión de Spotify para escuchar
  la canción completa (si no, se escucha un fragmento).

## Fotos

- **Desde la página**: tocá un marco → elegí una foto. Se recorta y se guarda en el
  navegador; al volver a abrir la página siguen ahí. La ✕ quita la foto.
- **Importante**: se guardan en *ese* dispositivo/navegador. Si querés que las fotos
  viajen dentro del archivo (para que las vea ella en su celular), decime y las
  incrusto en el HTML.
- **Fijas en el archivo**: también se pueden incrustar a mano (base64) si preferís.

## Música

La melodía se genera con el navegador (Web Audio), así que no hace falta ningún
archivo de audio. Empieza solo cuando tocás el botón de música o abrís el regalo
(los navegadores no permiten audio automático sin un clic).

## Publicar cambios en Cloudflare

El sitio se publica desde la carpeta `public/`. Después de editar algo:

```powershell
git add -A
git commit -m "cambios"
git push
npx wrangler deploy
```

- Sitio: https://feliz-cumpleanos-lujan.mathiasparedes202.workers.dev
- Proyecto de Cloudflare: `feliz-cumpleanos-lujan`
- La configuración está en `wrangler.jsonc` (publica solo lo que está en `public/`).
