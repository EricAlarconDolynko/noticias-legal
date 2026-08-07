# noticias-legal

Repositorio de soporte para la app **NoticIAs Al Momento** registrada en TikTok for Developers (Content Posting API + Login Kit). Sirve dos cosas:

1. Hostea la página de **Términos de Servicio y Política de Privacidad** que exige el registro de la app (`index.html`, publicada vía GitHub Pages en [ericalarcondolynko.github.io/noticias-legal](https://ericalarcondolynko.github.io/noticias-legal/)).
2. Guarda un **ejemplo real** de lo que produce el pipeline (carpeta `demo/`), para dejar constancia de cómo funciona la app más allá del texto del formulario de TikTok.

## Qué es NoticIAs Al Momento

Es una herramienta de automatización personal, de un solo usuario, que:

1. Trae titulares recientes de medios reconocidos por RSS público (BBC Mundo, Infobae, France 24 Español) — nunca scraping de HTML, solo los feeds que los propios medios publican para consumo externo.
2. Usa un modelo de lenguaje corriendo localmente (Ollama) para priorizar cuáles son las noticias más relevantes del momento, escribir un guion de locución fiel a la fuente y extraer las entidades (personas, lugares, organizaciones) que aparecen.
3. Genera la narración con una voz sintética local (Piper, TTS open-source) y arma el video: fondo en loop, imágenes ilustrativas con licencia libre verificada (Wikipedia/Wikimedia Commons, con atribución automática), subtítulos, música de fondo.
4. Arma el empaquetado por red social: caption y miniatura para TikTok, caption formateado para Instagram.
5. Antes de publicar nada, contrasta el guion generado contra el título/resumen original de la fuente para marcar automáticamente cualquier dato (nombre, fecha, cifra) que no esté verificado ahí — el video pasa por revisión humana antes de subirse.

La publicación en sí se hace vía la Content Posting API de TikTok, autorizada con Login Kit sobre la cuenta del propio desarrollador — sin acceso a ninguna otra cuenta.

## Carpeta `demo/`

Ejemplo real generado por el pipeline (noticia sobre la toma de posesión presidencial en Colombia, 6 de agosto de 2026):

| Archivo | Contenido |
|---|---|
| `ejemplo-noticia.mp4` | Video final: narración + subtítulos + imágenes + música |
| `ejemplo-miniatura.jpg` | Miniatura generada (imagen representativa + banner con el tema) |
| `ejemplo-caption-tiktok.txt` | Caption formateado para TikTok |
| `ejemplo-creditos.txt` | Créditos de las imágenes usadas (autor + licencia de cada una) |

## Licencias de contenido usadas por el pipeline

- Fuentes de noticias: RSS público de cada medio, siempre con atribución a la fuente original.
- Imágenes: solo de Wikipedia/Wikimedia Commons con licencia libre verificada (CC0, dominio público, CC-BY, CC-BY-SA) — nunca fotos de agencias de prensa con copyright. Cada imagen usada queda documentada con autor y licencia.
- Música y video de fondo: CC0 o contenido propio del desarrollador.
