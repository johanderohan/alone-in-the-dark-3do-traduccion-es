# Alone in the Dark (3DO) — Traducción al español

[![Invítame a un café en Ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/johanderohan)

Ficha del proyecto, capturas y más traducciones al castellano en **[Parches en Castellano](https://parchesencastellano.com/traducciones/3do/alone-in-the-dark)**.

Traducción al **español de España** de *Alone in the Dark* para **3DO** (Interplay, 1994), la
conversión de Infogrames e I·Motion del clásico de terror de 1992: Edward Carnby o Emily Hartwood
entran en Derceto, la mansión de Luisiana donde Jeremy Hartwood se ha quitado la vida. Se ha
traducido desde la versión estadounidense en inglés.

La traducción se distribuye como **parche**. No incluye el juego: necesitas tu propia copia
estadounidense para aplicarlo.

## Estado

Última versión: **[v1.0](../../releases/tag/v1.0)**, la primera.

| Parte | Estado |
|---|---|
| Menús, acciones, opciones y avisos | Traducidos |
| Objetos del inventario y sus estados (vacío, roto, mojado…) | Traducidos |
| Libros, cartas, diario y documentos (21 textos, 114 páginas) | Traducidos |
| Introducciones de Edward Carnby y Emily Hartwood | Traducidas |
| Pantallas de guardar y cargar partida (memoria interna de la 3DO) | Traducidas |
| Caracteres españoles | **á é í ó ú ü ñ Á É Í Ó Ú Ñ ¡ ¿ « »** |
| Revisión durante una partida | Parcial (ver abajo) |

Detalles técnicos:

- La fuente del juego no tenía sitio para letras nuevas: las letras españolas se han dibujado en
  posiciones de signos que el juego no usa, con el mismo trazo, color y sombreado que el original.
- El texto traducido se vuelve a comprimir con el mismo método que usa el juego y se coloca en el
  espacio libre del disco. Una auditoría automática comprueba cada versión: que el texto se
  descomprime igual que en la consola, que cada código de formato sigue en su sitio, que nada se
  sale de su recuadro y que el resto del disco no cambia.
- En las pantallas de guardado, el juego escribe el número de partida en una posición fija de la
  frase; se ha ajustado esa posición para que la frase en castellano sea natural.

Se quedan como en el original:

- Los logotipos y rótulos de marca (Interplay, Infogrames, el título «Alone in the Dark» de las
  pantallas de presentación y de guardado) y el aviso de copyright del arranque.
- Los créditos de la conversión a 3DO del principio (PROGRAMMING, PRODUCER…), que son un gráfico
  aparte. Los créditos del juego que salen en el libro sí están traducidos.

### Comprobaciones y trabajo pendiente

Se ha jugado en emulador desde partida nueva:

- Arranque, menú principal y elección de personaje; las introducciones completas de Edward y de
  Emily (cinco páginas cada una).
- El desván: inventario, lista de acciones, «Encuentras… / Coger» con la lámpara, avisos al usarla,
  el combate con la primera criatura, la muerte del personaje y la pantalla de fin.
- Menú de opciones, guardar en la memoria interna y cargar la partida desde el menú principal.
- El lector de documentos con títulos centrados, ilustraciones y paso automático de página, mediante
  un ensayo dirigido (textos de los libros mostrados en la pantalla de la introducción), porque en
  las pruebas jugadas no se llegó a ningún libro.

En total, unos veinte minutos de juego en tres rondas, con revisión de todas las capturas y
comparación con el juego original.

El parche se ha aplicado sobre el BIN estadounidense original y el resultado se ha comparado
byte a byte con la imagen probada.

**No se ha jugado una partida completa de principio a fin** ni se ha probado en consola real
(solo en el emulador Opera con la BIOS de la Panasonic FZ-10). La traducción se ha hecho desde el
inglés de la versión estadounidense y, como su revisión, con asistencia de IA, sin revisores
humanos independientes. Si encuentras un error, abre una incidencia con una captura.

Limitaciones conocidas:

- Las mayúsculas con tilde (Á, É…) son un píxel más bajas y algo más bajitas que el resto: la fuente
  no tiene espacio por encima de las mayúsculas. Es la misma solución que usa el original con su «é».
- No se han visto en pantalla los libros reales (solo en el ensayo dirigido), los avisos de registrar
  muebles, la pantalla para borrar partidas cuando la memoria está llena ni el final del juego.
- Por la fuente, el texto no usa «º», «ª», raya (—) ni comillas inglesas; las cantidades de dinero
  van en letra.

## Cambios

- **v1.0** (24-10-2026): primera versión.

## Cómo aplicar el parche

1. Descarga el parche `.xdelta` de la sección **[Releases](../../releases)**.
2. Consigue tu copia de **Alone in the Dark (EE. UU.)** para 3DO en formato BIN/CUE de una sola pista.
3. **Comprueba que tu copia es la correcta** antes de nada:

   | | |
   |---|---|
   | Archivo | `Alone in the Dark (USA).bin` |
   | Tamaño | 422.184.000 bytes |
   | MD5 | `192de93ff970cc04caa49d4a723a390f` |

   ```bash
   md5sum "Alone in the Dark (USA).bin"                # Linux
   md5 "Alone in the Dark (USA).bin"                   # macOS
   CertUtil -hashfile "Alone in the Dark (USA).bin" MD5   # Windows
   ```

   Si no coincide, el parche fallará o dará un resultado corrupto.
4. Aplica el parche con una de estas herramientas:
   - **Windows**: [Delta Patcher](https://github.com/marco-calautti/DeltaPatcher/releases)
   - **Linux / macOS**: `xdelta3 -d -s "Alone in the Dark (USA).bin" parche.xdelta "Alone in the Dark (ES).bin"`
5. Comprueba que el BIN resultante tiene el MD5 **`e9a7cab68efb4a7dc8c1dae7706f2779`** (v1.0).
6. Crea un CUE para el nuevo BIN, por ejemplo `Alone in the Dark (ES).cue`:

   ```
   FILE "Alone in the Dark (ES).bin" BINARY
     TRACK 01 MODE1/2352
       INDEX 01 00:00:00
   ```

7. Carga el CUE en tu emulador de 3DO (por ejemplo, el núcleo Opera de RetroArch con la BIOS de la
   Panasonic FZ-10) y empieza una partida nueva.

Aplica el parche sobre el **BIN estadounidense original**, no sobre una copia ya parcheada.

## Aviso

Este proyecto es una traducción hecha por afición, sin ánimo de lucro y sin relación alguna con
Infogrames, Interplay, The 3DO Company ni los demás titulares. Aquí no se distribuye el juego ni
ninguna parte de él: solo un parche que modifica una copia que ya tengas.

Si eres el titular de los derechos y quieres que retire esto, abre una incidencia y lo hago.
