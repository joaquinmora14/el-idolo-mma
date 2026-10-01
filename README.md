# El Ídolo: MMA

**Del gimnasio del barrio al cinturón de la UFC en seis minutos.** Armá la carrera de un peleador
de MMA: una carta de mejora por año, decisiones sin vuelta atrás y peleas que se ganan jugando
minijuegos.

Inspirado en el modo carrera **El Ídolo** de [Potrero](https://www.potrerofutbol.ar/el-idolo),
llevado a las artes marciales mixtas.

**Todo el juego es un único archivo HTML.** Sin build, sin dependencias, sin servidor.

---

## Cómo jugar

Abrí `index.html` en cualquier navegador (en el celular se juega de diez).

- **Arrancar mi carrera**: armás tu peleador (país, categoría, estilo y personalidad).
- **Desafío del día**: todos arrancan con el mismo peleador y la misma suerte. Al final copiás tu
  resultado en cuadraditos, como en Wordle, y lo comparás con tus amigos.

Una carrera completa dura **unos 6 minutos**: de los 22 años al retiro, entre 12 y 15 temporadas, y **todas las peleas se juegan**. A los 33 te preguntan si seguís; a los 38 se termina.

Se juega en el celular y en la compu (en pantalla ancha se arma en columnas; con la tecla F, pantalla completa). Tiene **modo oscuro**: sigue al del sistema y se cambia con el botón de la luna.

---

## Qué hace divertido a un juego así (y qué decidimos)

Investigué El Ídolo (Potrero), Copero, 7-0 y los juegos diarios tipo Wordle:

| Lo que funciona | Cómo lo aplica este juego |
|---|---|
| **Partidas cortas e impredecibles**, fáciles de compartir. Copero: una carrera en menos de 2 minutos; El Ídolo: unos 5. | Apuntamos a **5 o 6 minutos**, como El Ídolo: menos que eso y la carrera pierde historia (rival, ofertas, retiro); más, y deja de dar ganas de jugar "una más". Todas las peleas se juegan, así que las de la temporada usan **versiones cortas** de los minijuegos; el nocaut, el round y el cara a cara avanzan solos. |
| **Decisiones simples con consecuencias** (El Ídolo tiene más de 300 eventos). | 49 eventos y 6 momentos especiales (ofertas que no vuelven, Serie de Contendientes, título con dos semanas de aviso, doble cinturón, corte de contrato). Se muestra *qué* se juega con íconos, pero no el signo. |
| **Los momentos grandes se juegan.** En El Ídolo las finales se definen con minijuegos y antes elegís si ir con instinto o con técnica. | **No hay peleas simuladas**: cada temporada jugás una pelea de cartelera (corta) y la pelea del año; los títulos de la UFC, al mejor de tres. Contra mejores rivales, más difícil. El bocón y el guerrero eligen antes de cada pelea grande **con técnica** (habilidad) o **al instinto** (suerte). |
| **Identidad desde el arranque** (El Ídolo 2.1: elegís qué clase de jugador sos y cambia toda la carrera). | 4 personalidades que cambian las reglas. |
| **Un rival de toda la carrera.** | Tu rival sube, gana títulos, se cruza con vos en clásicos y al final se compara tu carrera con la suya. Con el resto no te cruzás siempre: el juego recuerda tus últimos rivales y nadie (salvo tu rival y los campeones) te toca más de dos veces. Si alguien te gana, sube en el ranking. |
| **Un motivo para volver mañana** (Wordle: un desafío por día y un resultado que se comparte sin spoilers). | Desafío del día con semilla fija y resultado en cuadraditos: verde ganaste, rojo perdiste, amarillo título. |
| **Que cada golpe se sienta** ("juice": congelar un instante el golpe, sacudir la pantalla, onomatopeyas). | Hit-stop en los golpes buenos, sacudón, flash, onomatopeyas de historieta (¡PAF!, ¡CRAC!) y la cara del rival que reacciona a cada golpe. |

---

## Diseño: menos "hecho por IA"

Las páginas generadas por IA se parecen entre sí: degradé violeta, la fuente Inter, modo oscuro con
brillos neón, tarjetas redondeadas con sombra difusa, emojis en lugar de íconos, rayas largas (—) en
todo el texto y títulos en mayúsculas con letra de máquina.
([925 Studios](https://www.925studios.co/blog/ai-slop-design-tells),
[TeneX](https://tenex.studio/en/blog/ai-slop-ui-8-signes/),
[10 tells of a slop UI](https://hereticpleb.vercel.app/blog/10-tells-of-slop/))

Este juego va en contra de eso con una dirección de arte concreta: **afiche de velada de barrio + diario deportivo**.

- Papel y tinta: fondo crema con grano, tinta negra, un rojo y un mostaza. Sin degradés ni brillos;
  las sombras son duras, como de imprenta.
- Tipografías con carácter: Alfa Slab One (titulares), Big Shoulders (carteles), Archivo (texto) y
  Courier Prime (letra de máquina).
- Íconos dibujados a mano en SVG en lugar de emojis.
- **Retratos generados en tinta** con semitono para cada peleador, entrenador, periodista, abuela o
  influencer. Tu rival te pone cara de enojado, le duele cuando le pegás y queda noqueado si lo terminás.
- Los **120 peleadores del plantel de la UFC y las leyendas** tienen rasgos parecidos a los reales:
  peinado, barba, color de piel, tatuajes, orejas de luchador (el gorro de Khabib, la barba colorada de
  Conor, el pelo turquesa de O'Malley, el sombrero de Cerrone…). Están en `const LOOKS = {`.
- **Modo oscuro como "edición nocturna"**: fondo carbón, tinta crema, el mismo rojo y mostaza y las
  mismas sombras duras; las caras quedan como fotos impresas. Nada de neón ni brillos.
- El menú es un afiche con entradas; las cartas son figuritas; el cierre de año es la tapa de un diario;
  el final es una placa.
- Hay un script de auditoría que recorre todas las pantallas y busca brillos, degradés, emojis, rayas
  largas y botones píldora.

---

## Cómo es una temporada

1. **Pretemporada**: elegís **1 de 3 cartas** de mejora (comunes, raras, épicas y legendarias).
2. **Evento** (a veces): una decisión rápida. Un influencer te desafía, tu abuela te pide que dejes, la UFC te llama…
3. **Pelea de cartelera**: un minijuego corto contra un rival de tu nivel en el ranking.
4. **La previa**: qué pasó con tu decisión, cómo te fue en la pelea de cartelera y el cartel de la pelea grande.
5. **La pelea del año**: se define con **minijuegos** (al mejor de tres si es por un título de la UFC).
6. **El diario**: titular, foto, resultado, ranking, plata y qué hizo tu rival.

Del circuito regional (LUX, LFA, Cage Warriors, FFC) al nivel mundial (PFL, Bellator, ONE) y a la
**UFC**, con atajo opcional por la **Serie de Contendientes**. Si perdés tres seguidas, te cortan el contrato.

### Las 4 personalidades

| | Cómo cambia el juego |
|---|---|
| **Cabulero** | Siempre al instinto: ruleta, dados, cartas y mano a mano. Tus stats deciden el tamaño de tus chances. Tenés **amuletos** para volver a jugar un round (y ganás más al subir de liga o salir campeón). |
| **Habilidoso** | Siempre con técnica, y elegís entre **4 cartas** por pretemporada. |
| **Bocón** | **Cara a cara** antes de cada pelea grande: una respuesta picante te da ventaja; un papelón, desventaja. Plata y fama x1,5, pero las derrotas te destrozan en redes. |
| **Guerrero** | Mentón de hierro: en los minijuegos **nunca te finalizan** y cuando vas abajo **te agrandás**. La hinchada te ama, pero el cuerpo declina antes. |

### Los 13 minijuegos

**Con técnica** (dependen de tu stat contra la del rival):

| Juego | Qué hacés |
|---|---|
| **La Zona** | La bola gira alrededor del rival: tocá cuando pase por lo amarillo (el rojo es perfecto). |
| **Patada a la cabeza** | La mira va y viene sobre un rival que se mueve: tocá en el centro del blanco. |
| **Bloqueá** | Golpes por tres carriles: tocá el del guante rojo. Los rayados son amagues. |
| **Cerrá la llave** | Mantené apretado y soltá cuando la aguja esté en lo amarillo. Si llegás a lo rayado, se escapa. |
| **Cadena de lucha** | Memorizá la cadena de movimientos y repetila. |
| **Ta-te-ti de la jaula** | Tres en línea contra un rival que juega mejor o peor según su nivel. |
| **El duelo** *(nuevo)* | Cara a cara y quietos: cuando aparece ¡YA!, pegá antes que él. Si te adelantás en un amague, perdés el cruce. |
| **Combo** *(nuevo)* | De ritmo: jab, cross y gancho bajan por tres carriles; tocá cada uno cuando cruza la línea roja. |
| **Ground & pound** *(nuevo)* | Lo tenés en el piso: pegale a los huecos rojos de su guardia, no a la guardia rayada. |

**Al instinto** (suerte; tus stats deciden el tamaño de tus chances):

| Juego | Qué hacés |
|---|---|
| **La ruleta** | Porciones de nocaut, ganás, perdés y te duermen, del tamaño de tus chances. |
| **Mano a mano** | Los penales del MMA: elegís dónde pegar y qué cubrir. Sus ojos a veces te avisan… y a veces te engañan. |
| **Las cartas** | Mirá las cartas, se dan vuelta y se mezclan: elegí dos. |
| **Los dados** | Sacá el número marcado o más. Doble seis es nocaut; doble uno, mejor no saberlo. |

Un minijuego **perfecto** termina la pelea por nocaut, sumisión o TKO. Antes de cada round se
explica la dificultad ("Nivel difícil · Tu golpe: 64 · el suyo: 70") y tus primeras peleas grandes
son más amables.

---

## Cómo se probó y balanceó

- **Bot de carrera** (`index.html?bot=0.6`): juega carreras enteras al instante. Con cientos de
  carreras se ajustaron crecimiento, ranking, ofertas y puntaje.
- **Humano simulado**: un script que *mira la pantalla* y toca con errores de timing reales
  (±30/55/90 ms) y tiempos de reacción de 340-530 ms para medir cada minijuego. En dificultad pareja,
  un jugador promedio gana 6 o 7 de cada 10 rounds; en "difícil", 3 o 4.
- **Partidas completas por la interfaz**, con tiempos de lectura de una persona real, jugando todas
  las peleas: 6,0 minutos con el guerrero y 6,4 con el habilidoso (unas 25 peleas), sin errores.
- **Bot calibrado con el humano simulado**: con un jugador promedio, cinturón de la UFC en 1 de cada
  3 o 4 carreras; con uno muy bueno, en 2 de cada 3; con uno flojo, muy de vez en cuando.
- **Capturas en celular y compu, claro y oscuro**, sin desbordes de 320 a 1920 px de ancho.

Parámetros útiles para probar: `?bot=0.8&persona=cabulero&retire=34` (el bot también acepta
`style`, `wc`, `cc` y `daily=1`).

---

## Estructura y cómo modificarlo

Todo está en `index.html`, en bloques comentados: **estilos**, **datos**, **herramientas** (azar con
semilla, sonido sintetizado con WebAudio, efectos), **arte** (íconos, retratos, onomatopeyas),
**motor de carrera**, **motor de pelea + minijuegos** y **pantallas**.

| Qué querés cambiar | Buscá en el archivo |
|---|---|
| Nombres de organizaciones | `const ORGS = {` |
| Dificultad y bolsas por nivel | `const TIERS = [` |
| Roster de la UFC | `const UFC_ROSTER = {` |
| Personalidades | `const PERSONAS = {` |
| Cartas de mejora | `const CARDS = [` |
| Eventos de decisión | `const EVENTS = [` |
| Frases del cara a cara | `const TRASH = [` |
| Leyendas de la comparación final | `const LEGENDS = [` |
| Un minijuego | `MG.zona = `, `MG.duelo = `, etc. |
| Íconos y retratos | `const ICONS = {`, `function portrait(` |
| Paleta y tipografías | `:root{` (arriba de todo) |

La partida se guarda sola en el navegador (`localStorage`) y el salón de la fama guarda tus 10 mejores carreras.

---

## Nota sobre nombres y marcas

- Los nombres de organizaciones (**UFC, Bellator, PFL, ONE, Cage Warriors, LFA, LUX**) son
  **marcas registradas de sus dueños**. Este proyecto no está afiliado ni autorizado por ninguna,
  ni por Potrero.
- Los peleadores del roster y de las comparaciones finales son **versiones alteradas** de nombres de
  personas reales.
- Para un proyecto personal o de aprendizaje normalmente no hay problema. Si lo publicás de forma
  masiva o le sacás rédito económico, conviene cambiar esos nombres por propios (están juntos en
  `ORGS`, `UFC_ROSTER` y `LEGENDS`).

---

## Licencia

Código bajo licencia MIT (ver `LICENSE`). La licencia cubre el código, no las marcas ni los nombres
de terceros mencionados arriba.
