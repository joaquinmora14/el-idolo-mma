# 🥊 El Ídolo: MMA

Simulador de carrera de MMA en el navegador, inspirado en el modo carrera de **El Ídolo** (Potrero).
Creás un peleador, elegís cómo pelea, y lo llevás desde el circuito regional hasta la élite mundial
a través de minijuegos rápidos de reacción, memoria y timing.

**Todo el juego es un único archivo HTML.** Sin build, sin dependencias, sin servidor.

---

## ▶️ Cómo jugar

Abrí `index.html` en cualquier navegador moderno. Nada más.

O jugalo online si activás GitHub Pages (ver más abajo).

---

## 🎮 Qué tiene

### Creación de personaje
- **Nacionalidad** con banderas (dibujadas en SVG, funcionan sin internet)
- **Liga de inicio** a elección (LFA, Cage Warriors, LUX, FFC)
- **Categoría de peso**, **altura** y **peso** con efectos reales
- **3 arquetipos**: Striker, Grappler, BJJ

### Físico con contrapartidas reales
Altura y peso no son decorativos: generan tres atributos que cambian cómo jugás.

| Físico | Alcance | Velocidad | Potencia |
|---|---|---|---|
| Alto y liviano | +6 | +1 | −4 |
| Alto y pesado | +6 | −7 | +6 |
| Bajo y liviano | −6 | +7 | −6 |
| Bajo y pesado | −6 | −1 | +4 |

- **Alcance** agranda las zonas de los juegos de golpear
- **Velocidad** da más tiempo en los de reacción y más empuje en los forcejeos
- **Potencia** multiplica el daño que hacés (hasta ±30%)

### Pelea posicional
La pelea fluye entre **DE PIE → CLINCH → PISO ARRIBA → PISO ABAJO**, y solo aparecen
los desafíos de la posición en la que estás. Si el rival se tira a las piernas tenés que
defender el sprawl; si fallás vas al piso y ahí solo hay juegos de piso (con la opción de
levantarte).

### 16 minijuegos
- **De pie (9)**: puntos débiles, precisión de golpe, lectura de combinación, contragolpe,
  combinación 1-2-3, entrada de derribo, defensa de derribo (flechas), defensa de striking, sprawl
- **Clinch (2)**: pelea contra la reja, control de cadera
- **Piso arriba (3)**: conexión de sumisión, cadencia del mata león, ground & pound
- **Piso abajo (2)**: escapar de la llave, levantarte

Cada uno se explica en una pantalla previa la primera vez que aparece, con el nivel de
dificultad y el motivo (*"FÁCIL — por tu mejor striking (80 vs 55)"*).

### Sistema de stats habilidad por habilidad
Lo que importa no es la valoración general sino la **habilidad puntual**: un striker con 85 de
striking domina los juegos de manos aunque su promedio sea peor que el del rival.

Hay un **presupuesto total de puntos** (150 / 204 / 252 según el nivel): pasado ese límite,
subir una stat te baja otra. No se puede ser bueno en todo.

### Carrera
- **Progresión**: circuito regional → nivel mundial (ONE, PFL, Bellator) → **UFC**
- **Serie de Contendientes**: invitación ineludible si sos campeón regional con buen récord;
  ganarla te da contrato firmable con la UFC (10k por pelear + 10k por ganar)
- **Bonos** con la estructura real 2026: $100.000 por Actuación/Pelea de la Noche,
  $25.000 por finalización (no se acumulan)
- **Firmar peleas**: elegís entre 3 ofertas con rival, ranking y bolsa distinta, con animación de firma
- **Plan de pelea** antes de cada combate, que el rival puede leerte y darte vuelta
- **Ranking estilo UFC**: quedás en el puesto del que venciste (o más arriba si fue batacazo
  o finalización) y él baja; al #1 solo se llega venciendo al #1 o #2
- **Edad**: crecés hasta los ~31 y declinás a partir de los 35
- **Roster de UFC** con 120 peleadores en 8 divisiones, con sucesión generacional
  (los veteranos se retiran, los prospectos crecen y cambian los campeones)
- **Rival de toda la carrera** que compite en paralelo
- **Tarjeta final compartible** con puntaje y rango, que se copia al portapapeles

---

## 📁 Estructura

```
.
├── index.html      # el juego completo (HTML + CSS + JS en un archivo)
├── README.md
├── LICENSE
└── .gitignore
```

---

## 🛠️ Cómo modificarlo

Todo está en `index.html`. Los bloques principales están marcados con comentarios:

| Qué querés cambiar | Buscá en el archivo |
|---|---|
| Nombres de organizaciones | `const ORGS = {` |
| Roster de la UFC | `const UFC_ROSTER = {` |
| Minijuegos disponibles | `const MINIGAME_POOL = [` |
| Precios de la tienda | `const SHOP = [` |
| Eventos entre peleas | `const EVENTS = [` |
| Categorías de peso | `const WEIGHT_CLASSES = [` |
| Paleta de colores | `:root{` (arriba de todo) |

---

## ⚠️ Nota sobre nombres y marcas

Antes de publicarlo o monetizarlo, tenelo presente:

- Los nombres de organizaciones (**UFC, Bellator, PFL, ONE, Cage Warriors, LFA, LUX**) son
  **marcas registradas de sus dueños**. Este proyecto no está afiliado ni autorizado por ninguna.
- Los peleadores del roster son **versiones alteradas** de nombres de personas reales.
- Para un proyecto personal o de aprendizaje normalmente no hay problema. Si lo publicás
  de forma masiva o le sacás rédito económico, conviene cambiar esos nombres por propios
  (están todos juntos en `ORGS` y `UFC_ROSTER`, se cambian en un minuto) o consultar con alguien
  que sepa de propiedad intelectual.

---

## 📄 Licencia

Código bajo licencia MIT (ver `LICENSE`). La licencia cubre el código, no las marcas
ni los nombres de terceros mencionados arriba.
