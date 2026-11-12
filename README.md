# 🎂 Feliz Cumpleaños, Luján

Una página hecha a mano para celebrar a alguien muy especial. Es un solo archivo
(`index.html`): no necesita instalación ni servidor. Se abre con doble clic.

## Cómo abrirla

1. Hacé doble clic en `index.html` (se abre en tu navegador).
2. Para que la vea ella, se la podés mandar por WhatsApp (como archivo), por mail,
   o subirla a cualquier hosting gratis (GitHub Pages, Netlify, etc.).

## Qué incluye

- **Portada** con su nombre, globos y corazones flotando.
- **Carta** con el mensaje principal.
- **"Lo que amo de ti"**: seis tarjetas con razones (incluye el tereré 🧉).
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

Abrí `index.html` con cualquier editor de texto y buscá `PERSONALIZÁ ACÁ`.
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
spotify: 'https://open.spotify.com/playlist/37i9dQZF1DXcBWIGoYBM5M',
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
