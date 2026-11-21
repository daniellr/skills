---
name: "branding"
description: "Diseño de identidad de marca y design sprint para cualquier tipo de marca, nueva o existente: apps, productos físicos, servicios, locales, marcas personales, eventos o clientes. Se activa con frases como \"haz el branding de X\", \"design sprint\", \"ayúdame con la identidad de marca\", \"definamos la paleta\", \"necesito brand guidelines\", \"diseñemos la marca\". Cubre nombre, audiencia, descubrimiento, brand guidelines, paleta, tipografía, logo y design system. Es el primer paso recomendado antes de arrancar un proyecto nuevo."
---

# SKILL — Branding

> **Instrucción para Claude:** Leer este skill completo cuando el usuario pide trabajar la identidad de un proyecto. Este skill es un wizard iterativo paso a paso. **No generar todo de una vez.** Cada sub-paso tiene un Input y un Output. Presentar el Output, esperar feedback, y avanzar al siguiente solo cuando el usuario confirme o ajuste.

> **Regla anti-slop:** todo Output de este wizard que sea visual o de copy pasa por el skill `anti-slop` antes de presentarse. Cada paso dice qué secciones del catálogo revisar. El chequeo es un sub-paso más: no se salta, y su resultado se muestra en una línea al final del Output ("Anti-slop: 0 señales" o qué se encontró y cómo se resolvió). Si el skill `anti-slop` no está cargado, cargarlo antes del primer Output de nombres o de copy (el Paso 1b, o el Paso 3 si no hay naming). Si no está instalado, decírselo al usuario una vez (se instala desde el mismo repo que este skill) y seguir el wizard sin ese chequeo, en vez de inventar el catálogo.

---

# Tipos de proyecto que cubre

Sirve para cualquier tipo de marca, nueva o existente: apps y productos digitales, productos físicos (skincare, ropa, alimentos), servicios y marketplaces, locales y restaurantes, marcas personales, organizaciones, eventos y marcas para clientes externos.

El flujo es el mismo para todas. Lo que cambia según dónde vive la marca son los sub-pasos condicionales:

- **Apps:** ícono en capas y pantallas clave. Van marcados con 📱 y se omiten si la marca no vive en una app.
- **Producto o espacio físico:** variantes para empaque, letrero e impresión, con su tamaño mínimo impreso.

---

# Detectar tipo de proyecto

El tipo se infiere de la descripción del Paso 1 y de dónde vive la marca (pregunta 6 del Paso 2). No se pregunta aparte: si después del Paso 2 sigue sin estar claro, se pregunta en una línea.

Esto determina si se ejecutan los sub-pasos 📱 y los de producto o espacio físico.

---

# Estructura general

```
Paso 0   El nombre
    ↓ output: Cerrado, provisional o sin nombre, y el camino a seguir
Paso 1   Descripción libre
    ↓ output: Audiencia + anti-audiencia + feeling
Paso 1b  Naming (solo si no hay nombre o se quiere revisar el provisional)
    ↓ output: Territorios de nombre + nombre elegido o de trabajo
Paso 2   Descubrimiento
    ↓ output: Voz (personaje), color, referencias, competencia, dónde vive, qué se conserva
Paso 3   Brand Guidelines
    ↓ output: Description, positioning, pillars, tone of voice, core message
Paso 4   Moodboard → Paleta + Tipografía
    ↓ output: Colores, tipografía, principios visuales
Paso 5   Logo
    ↓ output: Tipo de logo + brief + logo final + reglas + 📱 app icon (si app)
Paso 6   Design System
    ↓ output: Documento consolidado (+ tagline, si corresponde)
Paso 7   📱 Pantallas clave (solo apps)
    ↓ output: Mockups de 3-5 pantallas
```

**Regla de iteración:** cada paso muestra un Output → pregunta si hay algo que ajustar → solo avanza con confirmación. La cadena no se rompe.

---

# Paso 0 — El nombre

Lo primero es una sola pregunta:

> "¿El proyecto ya tiene nombre? Puede estar cerrado, ser provisional o no existir todavía."

Si el nombre vino en el mensaje con que se pidió el branding, la pregunta se hace igual, como confirmación: "¿[Nombre] está cerrado o todavía se puede mover?".

Según la respuesta:

- **Cerrado** → Paso 1. El nombre es un insumo fijo y el diagnóstico del logo (Paso 5a) lo usa tal cual.
- **Provisional** → Paso 1. Al cerrar el Paso 1, ofrecer una lectura corta del nombre contra la audiencia y contra `anti-slop` (sección 10). Si el usuario quiere revisarlo, Paso 1b; si no, se sigue con ese nombre.
- **Sin nombre** → preguntar si quiere ayuda para elegirlo ahora. Si sí, Paso 1 y después Paso 1b. Si no, se trabaja con un nombre de trabajo entre corchetes ([Marca]) y el wordmark queda pendiente; todo lo demás avanza.

Los nombres no se proponen todavía: sin saber para quién es la marca, salen genéricos.

---

# Paso 1 — Descripción libre

El usuario describe el proyecto en lenguaje natural. Puede ser desordenado o breve. Claude **no interrumpe ni pide más info** — trabaja con lo que hay. Si ya lo contó al pedir el branding, esa es la descripción y no se le vuelve a pedir.

**Output — tres bloques:**

1. **Quién es esta persona** — no un segmento demográfico, sino un retrato. Qué hace, cómo piensa, qué relación tiene con el problema o categoría que cubre el producto. Suficiente detalle para que el usuario diga "sí, exacto".

2. **Cómo se debería sentir al usarla / consumirla** — no la experiencia de onboarding ni el UI, sino el estado emocional que la marca debe evocar. Sensaciones concretas, no adjetivos sueltos.

3. **Para quién definitivamente no es** — 3-4 perfiles excluidos con justificación breve. Esto fuerza decisiones de diseño.

El retrato no usa arquetipos ni segmentos de manual ("millennials urbanos conscientes", "el Explorador"). Lleva detalles que solo calzan con este producto: qué objetos usa, qué dice, qué le molesta. Esos detalles son la materia prima de todo lo que viene después; sin ellos, el resto sale promedio.

→ Presentar los tres bloques y preguntar si hay algo que ajustar antes de continuar.

---

# Paso 1b — Naming (condicional)

Solo si en el Paso 0 no había nombre y el usuario quiere ayuda, o si quiere revisar el provisional. Se hace con el Paso 1 ya confirmado.

**Input — un solo mensaje con estas preguntas, todas saltables:**

1. ¿Qué tipo de nombre te gustaría? Mostrar los tipos con un ejemplo conocido de cada uno, para no depender de la jerga:
   - **Descriptivo:** dice lo que hace (Booking, Pizza Hut). Se entiende al tiro, pero cuesta diferenciarlo y registrarlo.
   - **Evocativo:** sugiere una idea o una sensación sin decirla (Amazon, Patagonia). Es el más versátil.
   - **Inventado:** una palabra nueva (Kodak, Häagen-Dazs). Fácil de registrar, pero parte vacío y hay que cargarlo de significado.
   - **De persona o de lugar:** un nombre propio, real o inventado (Ford, Tiffany & Co.). Cálido y con historia; amarra la marca a esa persona o a ese lugar.
   - **Prestado:** una palabra de otro idioma o de otro mundo (Uber, Volvo). Suena distinto y se recuerda, pero hay que revisar qué significa en su idioma de origen.
   - **Compuesto:** dos palabras o raíces juntas (Facebook, Netflix). Dice dos cosas a la vez; si las dos son palabras comunes, cuesta registrarlo.
2. Nombres de otras marcas que te gustan, de cualquier rubro, y qué tienen.
3. Restricciones: en qué idiomas tiene que funcionar, largo, si necesita dominio o @ libres, si va en una tienda de apps.
4. Palabras o ideas que no quieres.

**Output:**

- 2-3 **territorios** (direcciones de nombre distintas entre sí, ligadas al retrato del Paso 1), con 3-5 nombres cada uno.
- Cada nombre con su historia en una línea: de dónde sale y qué cuenta.
- Las pruebas rápidas de cada nombre: se dice en voz alta y se deletrea por teléfono sin explicarlo, y no significa algo malo en los idiomas pedidos.
- Lo que queda por verificar fuera del chat, marcado como pendiente y nunca dado por bueno: dominio, @ en redes, nombre en la tienda de apps si aplica y registro de marca (en Chile, INAPI).

**Chequeo anti-slop:** sección 10 (naming), más la prueba del prompt vecino: si el nombre le calza igual a cualquier competidor, se descarta.

→ El usuario elige uno, pide otra vuelta o sigue con un nombre de trabajo. El naming no bloquea: se puede cerrar más tarde, antes del brief del logo.

---

# Paso 2 — Descubrimiento

Antes de escribir guidelines, levantar lo que el usuario ya trae en la cabeza, como hacen las agencias en el discovery. Va encima del Paso 1.

**Input — un solo mensaje con estas preguntas.** Todas se pueden saltar y "no sé" es una respuesta válida. No se pregunta de a una.

1. **La voz.** Si la marca fuera un personaje, real o ficticio, ¿quién sería? Y lo más importante: qué tomas de él y qué no. Ejemplo: en Cornershop era Michael Scott, por el humor de chiste de papá, lo buena persona y lo gran vendedor que era; no su torpeza.
2. **Color.** Colores que te gustaría ver y colores que no quieres por ningún motivo, con la razón si la hay.
3. **Marcas que admiras**, de cualquier rubro, y qué les admiras.
4. **Referencias sueltas:** una foto, un lugar, una tienda, una película, un disco, una frase, un objeto. Lo que sea.
5. **Competencia:** quiénes son los vecinos directos y qué hacen que no quieres repetir.
6. **Dónde va a vivir la marca**, en orden de importancia: app, web, redes, empaque, letrero, local, uniforme, vehículo.
7. **Qué hay que conservar**, si algo ya existe: logo, colores, nombres de productos, una tradición. O "nada".

**Cómo se usan las respuestas:** son insumo, no decisiones tomadas. Cada una tiene su destino:

| Respuesta | Se usa en |
|---|---|
| Personaje | Tone of voice (Paso 3) |
| Colores | Paleta (Paso 4b) |
| Marcas y referencias | Moodboard (Paso 4a) y referentes del brief del logo (Paso 5b) |
| Competencia | Positioning (Paso 3) y clichés del rubro |
| Dónde vive | Tipo de proyecto, diagnóstico del logo (Paso 5a) y design system |
| Qué se conserva | Restricción para todo lo que sigue |

Cuando una preferencia choca con la audiencia del Paso 1 o con `anti-slop`, se dice ahora, con la razón y una alternativa. La decisión final es del usuario.

**Output:** una síntesis corta, una línea por respuesta, con la voz escrita como "Habla como [personaje]: sí [rasgos], no [rasgos]", y al final **Tensiones**: los choques encontrados, o "ninguna".

**Chequeo anti-slop:** si las referencias apuntan a un cúmulo conocido (secciones 1, 2 y 21), decirlo en la síntesis.

→ Presentar y esperar confirmación.

---

# Paso 3 — Brand Guidelines

Se construyen **encima de los Pasos 1 y 2**, no en paralelo ni desde cero.

**Output — estructura fija:**

- **Description** — qué es el producto/marca, 2-3 oraciones sin jerga ni superlativos
- **Positioning** — a quién le habla, qué problema resuelve, por qué este y no otro (frente a la competencia del Paso 2)
- **Brand Pillars** — exactamente 3, cada uno con nombre y definición breve. Cada pilar pasa la **prueba del contrario** (un competidor podría defender lo opuesto con sentido) y trae una conducta concreta que lo demuestra
- **Tone of voice** — parte del personaje del Paso 2: "Habla como [personaje]: sí [rasgos], no [rasgos]". Después, 3 adjetivos + tabla de qué diría vs qué nunca diría (con frases que diría ese personaje) + **10 palabras prohibidas** para esta marca (las del rubro y las de IA que más tienten en este caso)
- **Core Message** — la idea central que todo el diseño y copy debe reforzar

El tagline no va acá: se propone al consolidar el design system (Paso 6), con la marca ya vista entera.

**Chequeo anti-slop:** secciones 11 (identidad verbal), 12–14 (copy en el idioma de la marca) y la prueba del logo tapado sobre description, positioning y core message.

→ Presentar y esperar confirmación antes de avanzar.

---

# Paso 4 — Moodboard → Paleta + Tipografía

Dos momentos:

## 4a — Términos de búsqueda para moodboard

Claude genera 8-12 términos de búsqueda agrupados por categoría, basados en las brand guidelines y en las marcas y referencias del Paso 2 (los términos las complementan, no las repiten). Las categorías se ajustan según el tipo de proyecto:

**Para apps / productos digitales:**
- UI/Producto, Tipografía, Paleta/Color, Marca/Identidad

**Para marcas físicas (ej. skincare, ropa):**
- Empaque/Packaging, Tipografía, Paleta/Color, Fotografía/Editorial, Texturas/Materiales

**Para servicios/marketplaces:**
- Editorial/Web, Tipografía, Paleta/Color, Identidad

**Siempre, para cualquier tipo:** 2-3 términos **fuera del rubro** (señalética, archivos, objetos, oficios, diseñadores con nombre). Pinterest y Dribbble muestran el promedio de la categoría: sirven tanto para ver qué evitar como para inspirarse.

→ El usuario busca en Cosmos / Pinterest / Dribbble (5-10 min), comparte 3-5 referencias o describe lo que le gustó. Si no quiere hacer moodboard, Claude propone directamente basado en el feeling — no es bloqueante.

## 4b — Paleta + Tipografía

Con las referencias del usuario (o sin ellas), Claude propone lo de abajo. La paleta parte de los colores que pidió y de los que vetó en el Paso 2: si uno pedido choca con la audiencia o con `anti-slop`, se dice con la razón, se propone una alternativa y el usuario decide.

**Paleta de colores** — 5-8 colores máximo con tabla: Rol | Hex | Uso | Por qué. La columna "Por qué" liga cada color a algo del proyecto; "se ve limpio" no cuenta.

**Tipografía** — máximo 2 familias:
- Display/Headings: define el carácter
- Body: sans-serif neutra o del sistema
- Escala completa: H1, H2, H3, Body, Caption, Micro con tamaños y pesos
- Máximo 2 pesos
- Las fuentes que el catálogo marca como default (Inter, Geist, Montserrat, Poppins, Space Grotesk, Instrument Serif, Fraunces, Playfair, JetBrains Mono para etiquetas) solo entran con una razón escrita

**Principios visuales** — 5-7 reglas sobre fondos, jerarquía, color, espaciado, elementos estructurales. Adaptar al medio (digital vs físico). Cada regla se tiene que poder verificar mirando ("sombra dura sin blur", no "padding generoso").

**Chequeo anti-slop:** secciones 1 (color), 2 (tipografía) y 21 (la segunda ola), más la prueba del prompt vecino sobre la combinación paleta + tipografía.

→ Presentar y esperar confirmación.

---

# Paso 5 — Logo

**Claude no diseña el logo** (ni SVGs ni mockups propios de logo). Lo diseñan Claude Design o Figma Make a partir del brief de Claude, y el usuario cierra en Figma. Antes del brief se decide qué tipo de logo es.

## 5a — Tipo de logo

| Tipo | Qué es | Conviene cuando | Ojo |
|---|---|---|---|
| **Wordmark** | Solo el nombre, con letras dibujadas o modificadas (Coca-Cola, Google) | El nombre es corto, distintivo y fácil de leer | Con un nombre largo o genérico se pierde; con una fuente gratis sin tocar es blanding (`anti-slop`, sección 9) |
| **Monograma** | Las iniciales (HBO, IBM) | El nombre es largo o difícil | Al principio unas iniciales dicen poco |
| **Símbolo pictórico** | Un objeto reconocible (Apple) | El objeto cuenta algo propio de la marca | A una marca nueva le cuesta que se asocie; nada de íconos de concepto de stock (`anti-slop`, sección 9) |
| **Símbolo abstracto** | Una forma sin referente (Nike, Pepsi) | Hay tiempo y presencia para repetirlo hasta cargarlo de significado | Es el terreno de orbes, nudos y destellos (`anti-slop`, sección 9) |
| **Mascota o ilustrativo** | Un personaje (Michelin, KFC) | La voz es cercana y el personaje puede hablar por la marca | Cuesta mantenerlo consistente; nada de mascota-blob (`anti-slop`, sección 16) |
| **Emblema o sello** | El nombre dentro de una forma (Starbucks, Harley-Davidson) | Se busca oficio, tradición o pertenencia | Texto e imagen no se separan: achica mal y sufre como ícono o avatar |
| **Combinado** | Wordmark + símbolo, juntos o por separado (Adidas, Lacoste) | Hace falta flexibilidad entre usos grandes y chicos | Son dos piezas que diseñar y mantener |

**Diagnóstico.** Cuatro preguntas; la mayoría se responde con lo que ya hay (el nombre del Paso 0 o 1b, dónde vive del Paso 2, la voz del Paso 3). Solo se pregunta lo que falte:

1. ¿El nombre es corto y se defiende solo, o es largo, genérico o descriptivo?
2. ¿Dónde se va a ver más: chico (ícono de app, avatar, favicon, etiqueta) o grande (letrero, empaque, fachada)?
3. ¿Va a aparecer seguido sin el nombre al lado (ícono, bordado, sello en el empaque)?
4. ¿La voz pide un personaje que hable, o una firma sobria?

**Output:** un tipo recomendado como protagonista, con su razón en 2-3 líneas ligadas a las respuestas, y la alternativa más cercana con lo que se gana y lo que se pierde. **El usuario elige con libertad.** Si elige otro tipo, se sigue con ese; si tiene un costo real (un emblema que va a vivir como ícono de app, por ejemplo), se dice una vez y no se insiste.

Sea cual sea el protagonista, el sistema entrega **wordmark + isotipo**: el isotipo es la versión reducida para avatar, favicon, ícono o sello. Si el protagonista es el wordmark, el isotipo sale de él (una inicial o un detalle de las letras). El tipo define cuál de los dos manda y de qué naturaleza es el símbolo.

→ Presentar la recomendación y esperar la elección antes del brief.

## 5b — Conceptos y brief

Claude apoya con:

- Dirección conceptual basada en los pillars y en el tipo elegido: 3-5 conceptos, cada uno con la historia de dónde sale y qué cuenta
- Si el nombre sigue provisional o de trabajo, el brief lo dice y el wordmark se pide como exploración
- **El brief para Claude Design / Figma Make.** Siempre pide **wordmark + isotipo** y trae: contexto en tres líneas, el tipo de logo elegido y por qué, los conceptos, referentes con nombre (diseñadores, no tendencias; suman las marcas del Paso 2 cuando aplican), reglas de construcción (módulo, trazo, correcciones ópticas, wordmark dibujado y no escrito con una fuente), color, la sección **"Clichés que hay que evitar"** con sus dos listas (del diseño hecho por IA y del rubro, formato en `anti-slop`) y qué entregar: grilla superpuesta, lockups sobre los fondos de la marca, versión a una tinta e invertida, prueba a 16 px y, si es app, el ícono a 1024 px, 60 pt y 29 pt
- **La revisión de cada vuelta** contra anti-slop (secciones 9, 17 y 21, más la prueba de tamaño) antes de que el usuario elija

**Output:**

- Concepto elegido con mockup
- Reglas: colores, safe zone, tamaño mínimo, lo que NO hacer
- Variantes: light/dark, con/sin ícono, horizontal/vertical

**📱 Si es app:** el ícono se entrega en capas para Icon Composer. Seguir [`apps.md`](apps.md), sección 1.

**Si vive en un producto o espacio físico:** variantes para empaque, letrero e impresión (impresión vs digital), y reglas de tamaño mínimo impreso.

**El logo no bloquea los pasos siguientes** — se puede iterar después.

---

# Paso 6 — Design System

Consolidar todo en un documento único:

1. Nombre y su historia (Paso 0 o 1b)
2. Brand Guidelines (Paso 3), con la voz y su personaje
3. Logo: tipo, piezas y reglas (Paso 5)
4. Color Palette (Paso 4)
5. Typography (Paso 4)
6. Visual Principles (Paso 4)
7. Brand Elements — dots, líneas, patrones, texturas, fotografías de referencia
8. **Tagline** — opcional. Se propone ahora, con la marca vista entera, solo si hay un uso real a la vista (empaque, ficha de la tienda, campaña); si no, queda pendiente. Una línea, sin signos de exclamación, sin "el mejor" y sin las fórmulas de tagline del catálogo ("X para cada Y", "X, reimagined", "Todo en un solo lugar", paralelos tipo "Diseñado para…, hecho para…"), y pasa la prueba del logo tapado
9. **Lo que no hacemos** — obligatoria. Dos listas: los tics del diseño hecho por IA con más riesgo en este proyecto (sacados del catálogo `anti-slop`, con valores concretos) y los clichés del rubro. Es la sección que Claude Code y las herramientas de diseño leen antes de tocar UI.

Para apps, agregar también: spacing scale (grid de 8pt), iconografía, estados de componentes (vacío, cargando, error, sin conexión).

**📱 Marca que vive en una app:** seguir [`apps.md`](apps.md), sección 2.

Si vive en un producto o espacio físico, agregar: lineamientos de empaque y señalética, fotografía de producto, do's & don'ts visuales.

**Dónde vive el documento:** en el repo del proyecto, típicamente en `docs/design-system.md` o `brand/identity.md` según la naturaleza del repo (proyecto de código o proyecto de marca).

---

# Paso 7 — 📱 Pantallas clave (solo apps)

Mockups de 3-5 pantallas principales en el chat (HTML) o en Figma. Antes de empezar, leer [`apps.md`](apps.md), sección 3: qué pantallas van, cómo se arman y su chequeo anti-slop.

Cada mockup se muestra, se discute, se ajusta. **Desde este punto se puede arrancar Claude Code**: el design system y las pantallas dan suficiente contexto para empezar a construir.

Si el proyecto no es app, este paso se omite.

---

# Reglas operativas

- **Iteración paso a paso, no generar todo de una.** Cada Output espera confirmación antes de avanzar.
- **Trabajar encima de lo anterior.** Cada paso usa los anteriores: el Paso 3 usa el 1 y el 2, el 4 usa el 2 y el 3, etc. No reabrir decisiones ya cerradas a menos que el usuario lo pida.
- **Moodboard no es bloqueante.** Si el usuario no quiere buscar referencias, proponer directamente.
- **Logo no bloquea pasos siguientes.** Se puede tener un logo provisional y seguir con design system y pantallas.
- **Nombre no bloquea.** Sin nombre cerrado se trabaja con uno de trabajo; solo el wordmark espera.
- **Preguntas en un solo mensaje.** Las del Paso 1b y las del Paso 2 van juntas, numeradas y saltables, no de a una.
- **Claude recomienda, el usuario decide.** En nombre, colores y tipo de logo, Claude da su recomendación con la razón y la alternativa. Si el usuario elige otra cosa, se sigue con eso y el costo real se dice una sola vez.
- **Tipo de proyecto determina sub-pasos condicionales.** Si no es app, omitir 📱.
- **Output adaptativo, no rígido.** Si una sección no aplica al caso real (ej. paywall en una app gratuita, fotografía de producto en una app pura), omitirla.
- **Anti-slop en cada Output visual o de copy.** El chequeo del paso no se salta, y todo brief para una herramienta de diseño lleva la sección "Clichés que hay que evitar".
- **Idioma:** el del usuario. Si escribe en español, español chileno (tú/tienes) en toda la conversación y entregables. Nombres técnicos y referencias internacionales pueden quedar en inglés.

---

# Anti-patrones a evitar

- **Adelantar pasos.** No proponer nombres antes del Paso 1. No proponer paleta antes de cerrar audiencia y descubrimiento. No proponer logo sin pillars ni tipo de logo elegido. No proponer tagline antes del design system.
- **Branding genérico.** Cada output debe reflejar al proyecto específico, no aplicar a "cualquier app de productividad" o "cualquier marca de skincare".
- **Adjetivos sueltos en tone of voice.** "Confiable, moderno, cercano" no significa nada. Acompañar con tabla de qué diría vs qué nunca diría.
- **Más de 8 colores en la paleta.** Forzar decisión.
- **Más de 2 familias tipográficas.** Misma regla.
- **Saltar el "para quién no es".** Es la sección que más fuerza decisiones de diseño. Es obligatoria.
- **Arreglar "se ve hecho por IA" saltando a la segunda ola.** Cuando el usuario dice que algo se ve "Claude made", la salida fácil es crema con serif, diagramación de diario o monoespaciada para etiquetas. Eso es otro cúmulo de IA (anti-slop, sección 21). El arreglo sale del mundo del producto, no de la lista de antídotos.
- **Mockups de fantasía en la presentación.** Tarjetas flotando, tote bags, letreros en fachadas. Se muestra la marca donde de verdad va a vivir.
- **Claude dibujando el logo.** El rol de Claude en el Paso 5 es el brief y la crítica.
- **Tomar las preferencias del Paso 2 como decisiones cerradas, o pasarlas por alto.** Son insumo: se usan, y si chocan con la audiencia se dice.

---

# Handoff a otros skills

Al cerrar el branding, Claude debería ofrecer el siguiente paso según el contexto:

- Si el branding es parte del arranque de un proyecto nuevo → continuar con el skill de arranque de proyectos si está instalado (repo, archivos, dominio, infra, App Store, lanzamiento)
- Si era branding standalone para refrescar una marca existente → cerrar con el design system entregado en el repo del proyecto
- Si el usuario quiere implementar las pantallas → arrancar Claude Code con el design system + mockups como contexto

---

# Notas

- El Design Sprint completo toma 1-2 sesiones de conversación
- Para clientes externos, el output puede empacarse como entregable independiente en el repo del cliente
- Las decisiones de marca se documentan en el repo del proyecto (por ejemplo en un `CONTEXT.md`)
- Si el proyecto ya tiene branding parcial (ej. logo pero no paleta), arrancar desde el sub-paso que falte, no desde cero
