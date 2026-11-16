---
name: "branding"
description: "Diseño de identidad de marca y design sprint para proyectos nuevos o existentes. Funciona para apps, marcas físicas (skincare, ropa, alimentos), servicios y productos digitales. Se activa con frases como \"haz el branding de X\", \"design sprint\", \"ayúdame con la identidad de marca\", \"definamos la paleta\", \"necesito brand guidelines\", \"diseñemos la marca\". Cubre audiencia, brand guidelines, paleta, tipografía, logo y design system. Es el primer paso recomendado antes de arrancar un proyecto nuevo."
---

# SKILL — Branding

> **Instrucción para Claude:** Leer este skill completo cuando el usuario pide trabajar la identidad de un proyecto. Este skill es un wizard iterativo paso a paso. **No generar todo de una vez.** Cada sub-paso tiene un Input y un Output. Presentar el Output, esperar feedback, y avanzar al siguiente solo cuando el usuario confirme o ajuste.

> **Regla anti-slop:** todo Output de este wizard que sea visual o de copy pasa por el skill `anti-slop` antes de presentarse. Cada paso dice qué secciones del catálogo revisar. El chequeo es un sub-paso más: no se salta, y su resultado se muestra en una línea al final del Output ("Anti-slop: 0 señales" o qué se encontró y cómo se resolvió). Si el skill `anti-slop` no está cargado, cargarlo al empezar el Paso 2. Si no está instalado, decírselo al usuario una vez (se instala desde el mismo repo que este skill) y seguir el wizard sin ese chequeo, en vez de inventar el catálogo.

---

# Tipos de proyecto que cubre

El skill es agnóstico al tipo de producto. Aplica a:

- **Apps** (iOS principalmente)
- **Marcas de producto físico** (ej. skincare, cosmética)
- **Marketplaces y servicios** (ej. Sotos)
- **Productos digitales no-app** (landing pages, dashboards, herramientas internas)
- **Marcas para clientes externos**

Hay sub-pasos marcados con 📱 que solo aplican a apps (app icon, mockups de pantallas). Esos se omiten si el proyecto no es app.

---

# Detectar tipo de proyecto

Antes de arrancar, inferir el tipo a partir de la descripción libre o de cómo el usuario introdujo el proyecto. Si no queda claro, preguntar:

> "¿Qué tipo de proyecto es: app, marca física, servicio/marketplace, o producto digital no-app?"

Esto determina si se ejecutan los sub-pasos 📱 al final.

---

# Estructura general

```
Paso 1  Descripción libre
    ↓ output: Audiencia + anti-audiencia + feeling
Paso 2  Brand Guidelines
    ↓ output: Description, tagline, tone, positioning, pillars, core message
Paso 3  Moodboard → Paleta + Tipografía
    ↓ output: Colores, tipografía, principios visuales
Paso 4  Logo
    ↓ output: Logo final + reglas + 📱 app icon (si app)
Paso 5  Design System
    ↓ output: Documento consolidado
Paso 6  📱 Pantallas clave (solo apps)
    ↓ output: Mockups de 3-5 pantallas
```

**Regla de iteración:** cada paso muestra un Output → pregunta si hay algo que ajustar → solo avanza con confirmación. La cadena no se rompe.

---

# Paso 1 — Descripción libre

El usuario describe el proyecto en lenguaje natural. Puede ser desordenado o breve. Claude **no interrumpe ni pide más info** — trabaja con lo que hay.

**Output — tres bloques:**

1. **Quién es esta persona** — no un segmento demográfico, sino un retrato. Qué hace, cómo piensa, qué relación tiene con el problema o categoría que cubre el producto. Suficiente detalle para que el usuario diga "sí, exacto".

2. **Cómo se debería sentir al usarla / consumirla** — no la experiencia de onboarding ni el UI, sino el estado emocional que la marca debe evocar. Sensaciones concretas, no adjetivos sueltos.

3. **Para quién definitivamente no es** — 3-4 perfiles excluidos con justificación breve. Esto fuerza decisiones de diseño.

El retrato no usa arquetipos ni segmentos de manual ("millennials urbanos conscientes", "el Explorador"). Lleva detalles que solo calzan con este producto: qué objetos usa, qué dice, qué le molesta. Esos detalles son la materia prima de todo lo que viene después; sin ellos, el resto sale promedio.

→ Presentar los tres bloques y preguntar si hay algo que ajustar antes de continuar.

---

# Paso 2 — Brand Guidelines

Se construyen **encima del resultado del Paso 1**, no en paralelo ni desde cero.

**Output — estructura fija:**

- **Description** — qué es el producto/marca, 2-3 oraciones sin jerga ni superlativos
- **Tagline** — una línea, sin signos de exclamación, sin "el mejor", y sin las fórmulas de tagline del catálogo ("X para cada Y", "X, reimagined", "Todo en un solo lugar", paralelos tipo "Diseñado para…, hecho para…")
- **Tone of voice** — 3 adjetivos + tabla de qué diría vs qué nunca diría + **10 palabras prohibidas** para esta marca (las del rubro y las de IA que más tienten en este caso)
- **Positioning** — a quién le habla, qué problema resuelve, por qué este y no otro
- **Brand Pillars** — exactamente 3, cada uno con nombre y definición breve. Cada pilar pasa la **prueba del contrario** (un competidor podría defender lo opuesto con sentido) y trae una conducta concreta que lo demuestra
- **Core Message** — la idea central que todo el diseño y copy debe reforzar

**Chequeo anti-slop:** secciones 11 (identidad verbal), 12–14 (copy en el idioma de la marca) y la prueba del logo tapado sobre description, tagline y core message.

→ Presentar y esperar confirmación antes de avanzar.

---

# Paso 3 — Moodboard → Paleta + Tipografía

Dos momentos:

## 3a — Términos de búsqueda para moodboard

Claude genera 8-12 términos de búsqueda agrupados por categoría, basados en las brand guidelines. Las categorías se ajustan según el tipo de proyecto:

**Para apps / productos digitales:**
- UI/Producto, Tipografía, Paleta/Color, Marca/Identidad

**Para marcas físicas (ej. skincare, ropa):**
- Empaque/Packaging, Tipografía, Paleta/Color, Fotografía/Editorial, Texturas/Materiales

**Para servicios/marketplaces:**
- Editorial/Web, Tipografía, Paleta/Color, Identidad

**Siempre, para cualquier tipo:** 2-3 términos **fuera del rubro** (señalética, archivos, objetos, oficios, diseñadores con nombre). Pinterest y Dribbble muestran el promedio de la categoría: sirven tanto para ver qué evitar como para inspirarse.

→ El usuario busca en Cosmos / Pinterest / Dribbble (5-10 min), comparte 3-5 referencias o describe lo que le gustó. Si no quiere hacer moodboard, Claude propone directamente basado en el feeling — no es bloqueante.

## 3b — Paleta + Tipografía

Con las referencias del usuario (o sin ellas), Claude propone:

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

# Paso 4 — Logo

**Claude no diseña el logo** (ni SVGs ni mockups propios de logo). Lo diseñan Claude Design o Figma Make a partir del brief de Claude, y el usuario cierra en Figma. Claude apoya con:

- Dirección conceptual basada en los pillars: 3-5 conceptos, cada uno con la historia de dónde sale y qué cuenta
- Variantes de naming si aún no está cerrado (pasan por anti-slop, sección 10)
- **El brief para Claude Design / Figma Make.** Siempre pide **wordmark + isotipo** y trae: contexto en tres líneas, los conceptos, referentes con nombre (diseñadores, no tendencias), reglas de construcción (módulo, trazo, correcciones ópticas, wordmark dibujado y no escrito con una fuente), color, la sección **"Clichés que hay que evitar"** con sus dos listas (del diseño hecho por IA y del rubro, formato en `anti-slop`) y qué entregar: grilla superpuesta, lockups sobre los fondos de la marca, versión a una tinta e invertida, prueba a 16 px y, si es app, el ícono a 1024 px, 60 pt y 29 pt
- **La revisión de cada vuelta** contra anti-slop (secciones 9, 17 y 21, más la prueba de tamaño) antes de que el usuario elija

**Output:**

- Concepto elegido con mockup
- Reglas: colores, safe zone, tamaño mínimo, lo que NO hacer
- Variantes: light/dark, con/sin ícono, horizontal/vertical

**📱 Si es app:** el ícono se entrega en capas para Icon Composer. Seguir [`apps.md`](apps.md), sección 1.

**Si es marca física:** variante para empaque (impresión vs digital), reglas de tamaño mínimo en empaque.

**El logo no bloquea los pasos siguientes** — se puede iterar después.

---

# Paso 5 — Design System

Consolidar todo en un documento único:

1. Brand Guidelines (Paso 2)
2. Logo y reglas (Paso 4)
3. Color Palette (Paso 3)
4. Typography (Paso 3)
5. Visual Principles (Paso 3)
6. Brand Elements — dots, líneas, patrones, texturas, fotografías de referencia
7. **Lo que no hacemos** — obligatoria. Dos listas: los tics del diseño hecho por IA con más riesgo en este proyecto (sacados del catálogo `anti-slop`, con valores concretos) y los clichés del rubro. Es la sección que Claude Code y las herramientas de diseño leen antes de tocar UI.

Para apps, agregar también: spacing scale (grid de 8pt), iconografía, estados de componentes (vacío, cargando, error, sin conexión).

**📱 Marca que vive en una app:** seguir [`apps.md`](apps.md), sección 2.

Para marcas físicas, agregar: lineamientos de empaque, fotografía de producto, do's & don'ts visuales.

**Dónde vive el documento:** en el repo del proyecto, típicamente en `docs/design-system.md` o `brand/identity.md` según la naturaleza del repo (proyecto de código o proyecto de marca).

---

# Paso 6 — 📱 Pantallas clave (solo apps)

Mockups de 3-5 pantallas principales en el chat (HTML) o en Figma. Antes de empezar, leer [`apps.md`](apps.md), sección 3: qué pantallas van, cómo se arman y su chequeo anti-slop.

Cada mockup se muestra, se discute, se ajusta. **Desde este punto se puede arrancar Claude Code**: el design system y las pantallas dan suficiente contexto para empezar a construir.

Si el proyecto no es app, este paso se omite.

---

# Reglas operativas

- **Iteración paso a paso, no generar todo de una.** Cada Output espera confirmación antes de avanzar.
- **Trabajar encima de lo anterior.** El Paso 2 usa el Paso 1, el Paso 3 usa el Paso 2, etc. No reabrir decisiones ya cerradas a menos que el usuario lo pida.
- **Moodboard no es bloqueante.** Si el usuario no quiere buscar referencias, proponer directamente.
- **Logo no bloquea pasos siguientes.** Se puede tener un logo provisional y seguir con design system y pantallas.
- **Tipo de proyecto determina sub-pasos condicionales.** Si no es app, omitir 📱.
- **Output adaptativo, no rígido.** Si una sección no aplica al caso real (ej. paywall en una app gratuita, fotografía de producto en una app pura), omitirla.
- **Anti-slop en cada Output visual o de copy.** El chequeo del paso no se salta, y todo brief para una herramienta de diseño lleva la sección "Clichés que hay que evitar".
- **Idioma:** el del usuario. Si escribe en español, español chileno (tú/tienes) en toda la conversación y entregables. Nombres técnicos y referencias internacionales pueden quedar en inglés.

---

# Anti-patrones a evitar

- **Adelantar pasos.** No proponer paleta antes de cerrar audiencia. No proponer logo sin pillars.
- **Branding genérico.** Cada output debe reflejar al proyecto específico, no aplicar a "cualquier app de productividad" o "cualquier marca de skincare".
- **Adjetivos sueltos en tone of voice.** "Confiable, moderno, cercano" no significa nada. Acompañar con tabla de qué diría vs qué nunca diría.
- **Más de 8 colores en la paleta.** Forzar decisión.
- **Más de 2 familias tipográficas.** Misma regla.
- **Saltar el "para quién no es".** Es la sección que más fuerza decisiones de diseño. Es obligatoria.
- **Arreglar "se ve hecho por IA" saltando a la segunda ola.** Cuando el usuario dice que algo se ve "Claude made", la salida fácil es crema con serif, diagramación de diario o monoespaciada para etiquetas. Eso es otro cúmulo de IA (anti-slop, sección 21). El arreglo sale del mundo del producto, no de la lista de antídotos.
- **Mockups de fantasía en la presentación.** Tarjetas flotando, tote bags, letreros en fachadas. Se muestra la marca donde de verdad va a vivir.
- **Claude dibujando el logo.** El rol de Claude en el Paso 4 es el brief y la crítica.

---

# Handoff a otros skills

Al cerrar el branding, Claude debería ofrecer el siguiente paso según el contexto:

- Si esto fue Paso 0 de un proyecto nuevo → continuar con el skill de arranque de proyectos si está instalado (repo, archivos, dominio, infra, App Store, lanzamiento)
- Si era branding standalone para refrescar una marca existente → cerrar con el design system entregado en el repo del proyecto
- Si el usuario quiere implementar las pantallas → arrancar Claude Code con el design system + mockups como contexto

---

# Notas

- El Design Sprint completo toma 1-2 sesiones de conversación
- Para clientes externos, el output puede empacarse como entregable independiente en el repo del cliente
- Las decisiones de marca se documentan en el repo del proyecto (por ejemplo en un `CONTEXT.md`)
- Si el proyecto ya tiene branding parcial (ej. logo pero no paleta), arrancar desde el sub-paso que falte, no desde cero
