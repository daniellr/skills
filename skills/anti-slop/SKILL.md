---
name: "anti-slop"
description: "Catálogo de las señales que delatan diseño, marca y copy hechos por IA (color, tipografía, layouts, componentes, apps iOS, logos, naming, copy en inglés y español, imágenes, ícono de app, App Store) y qué hacer en vez. Usar antes de proponer, briefear o aprobar cualquier pantalla, landing, web, dashboard, logo, paleta, nombre, copy o asset, y al revisar lo que entregan Claude Design, Figma Make o Claude Code. Lo usa el skill branding en cada paso visual o de copy."
---

# SKILL: Anti-slop

> **Instrucción para Claude:** este skill es un catálogo de referencia, no un wizard. Se usa en tres momentos:
>
> 1. **Antes de proponer** algo visual o de copy, para no partir del default.
> 2. **Al escribir un brief o prompt** para Claude Design, Figma Make, Midjourney o Claude Code, para armar la sección de clichés (plantilla al final).
> 3. **Al revisar lo que entrega una herramienta**, antes de mostrárselo al usuario.
>
> Cuando un paso de `branding` (u otro skill que lo invoque) dice "pasa por anti-slop", es esto: las pruebas de abajo más las secciones del catálogo que correspondan. Al construir UI en código, carga también `frontend-design` si está disponible; para gráficos y dashboards, `dataviz`.

Sale del benchmark del 2026-10-10: cinco frentes (web, apps iOS, identidad, copy en inglés y español, imagen y App Store) y unas 200 fuentes. Las fuentes principales están en [`fuentes.md`](fuentes.md); no hace falta cargarlas para usar el skill.

---

# Cómo leer el catálogo

- **Lo que delata es el default sin razón.** Cualquier elección de esta lista es válida si tiene una razón ligada al proyecto. Los degradados de Mercury Weather codifican la temperatura: eso es una decisión. El mismo degradado de fondo "porque se ve moderno" es un tic.
- **Lo que delata es la acumulación.** De 1.590 landings de Show HN, el 46% tenía 0 o 1 patrones, el 32% tenía 2 o 3 y el 22% tenía 4 o más. Regla: **0–1 pasa, 2–3 se revisa, 4 o más se rehace.**
- **No perseguir lo raro.** Una lista de prohibidos solo mueve el cúmulo a otro lado (sección 21, la segunda ola). La meta es que se vea decidido. Un layout convencional bien resuelto está bien.
- **La lista envejece.** "Delve" casi desapareció del output de ChatGPT en 2025 mientras la raya pasaba de menos del 10% a más del 50% de las respuestas. Space Grotesk y Fraunces pasaron de antídoto a tic. Las estructuras duran más que las palabras. Este catálogo se revisa cada seis meses.
- **El brief del usuario manda.** Si el usuario pide algo de esta lista, se hace. El catálogo gobierna los ejes que quedaron libres.

**(fuerte)** marca las señales que delatan casi solas. Las demás delatan cuando se suman.

---

# Por qué pasa

Sirve para explicarlo en un brief o a una herramienta:

- **Convergencia al promedio.** El modelo elige lo más probable de lo que vio, y lo más probable es lo seguro: Inter, morado sobre blanco, hero centrado. Anthropic lo llama *distributional convergence*.
- **Los defaults de las herramientas entraron al entrenamiento.** El `bg-indigo-500` de Tailwind UI (Adam Wathan pidió disculpas en 2025), el kit de shadcn, Lucide. El morado llena una decisión que nadie tomó.
- **Prompt vago, resultado promedio.** "Moderno" se vuelve degradado, "premium" se vuelve fondo oscuro, "lujo" se vuelve mayúsculas espaciadas.
- **Mucho Dribbble en el entrenamiento.** Pantallas lindas sin datos reales, sin estados y sin contexto.
- **Retroalimentación.** El output de IA vuelve a la web y entrena a los modelos siguientes.
- **La segunda ola.** Las instrucciones anti-slop crean defaults nuevos: crema con serif y terracota es hoy la firma de Claude.

---

# Las pruebas

Antes de entregar cualquier cosa visual o de copy, corre las que apliquen:

1. **Logo tapado.** Pon el nombre de un competidor. Si sigue funcionando, se reescribe o se rediseña.
2. **Prompt vecino.** ¿Un prompt parecido para otro producto llegaría al mismo lugar? Si sí, ese eje quedó en default.
3. **Conteo.** Cuenta las señales del catálogo que aparecen (umbral de arriba).
4. **Razón escrita.** Cada color, fuente, radio, sombra y animación tiene una línea de por qué ligada al proyecto. "Se ve limpio" o "se ve moderno" no es razón.
5. **Prueba inversa.** Pregúntale a un chat nuevo qué herramienta hizo esto. Si lo adivina, vuelve atrás.
6. **Estados** (producto). Vacío, cargando, error, sin conexión, primer uso y mucho contenido.
7. **Tamaño** (marca e íconos). 16 px, una tinta, invertido y a tamaño letrero.
8. **Voz alta** (copy). Si no lo dirías así en una conversación, se reescribe.
9. **Pixel real.** Toda captura, mockup o número sale del producto o de datos ficticios realistas del dominio, nunca de un render inventado.

---

# Catálogo

## 1. Color

- **Índigo o violeta como primario** (fuerte). `#6366F1`, `#4F46E5`, `#8B5CF6`, `#7C3AED`, `#A855F7`: tono entre 255 y 280 en botones y links. *En vez:* un color con razón de negocio y su rampa armada desde una semilla (OKLCH).
- **Degradado morado a azul** (fuerte). `from-purple-* to-blue-*`, violeta a índigo, índigo a rosado, repetido en hero, botones y tarjetas. *En vez:* rellenos planos; como mucho un degradado con función.
- **Texto con degradado** (fuerte). `bg-clip-text text-transparent` en el H1 o en las cifras. *En vez:* un color sólido; el énfasis sale del tamaño o del peso.
- **Modo oscuro con resplandor** (fuerte). Fondo `#0A0A0A` a `#1A1A1A` o `slate-950`, sombras de color `0 0 Npx`, aurora o halo radial detrás del hero (el "look Linear"). *En vez:* profundidad con tipografía, contraste y niveles de superficie. Modo oscuro solo si el producto lo pide.
- **Neón sobre negro** (fuerte). Cian cerca de `#00D4FF`, verde o fucsia 400, cinco acentos sin un foco. *En vez:* 70-30-10: un dominante, un secundario y un acento.
- **Mancha borrosa o halo detrás de un H1 centrado** (fuerte). *En vez:* sacarlo.
- **Paletas del rubro.** Navy con azul eléctrico en fintech, seguridad y B2B. Beige y tierra apagados en wellness y beauty. Rosado millennial y oro rosa.
- **Neutros sin tocar.** `slate` o `zinc` de Tailwind, `#000` y `#FFF` puros por inercia. *En vez:* neutros teñidos con el tono de la marca, o el negro puro cuando tiene un trabajo (en un reloj de ajedrez, es el color de las piezas).
- **Gris sobre color, bajo contraste.** *En vez:* mínimo 4,5:1 en texto.
- **Puntos de estado y badges sin estado real.** "Live", "New", "Active", "Verified" pulsando. *En vez:* atarlos a un estado de verdad o usar texto.
- **Color sin significado.** Cinco o seis colores saturados al mismo volumen, o el azul de iOS por defecto. *En vez:* un acento con un solo significado. El amarillo de Halide marca lo activo; en un reloj de ajedrez, el rojo puede reservarse solo para el tiempo que se acaba.

La segunda ola del color (crema con terracota, crema con verde bosque, casi negro con acento ácido) está en la sección 21.

## 2. Tipografía

- **Inter como única fuente** (fuerte cuando se suma a otras). También Roboto, Arial, Open Sans, Lato, `system-ui` o `font-sans` sin decidir, o Geist sola.
- **Las gratis de siempre en marca.** Montserrat es la fuente gratis más parecida para el 32% de 9.563 logos estudiados, y Poppins para el 20%. Cerca del 98% de las marcas reales usa letras propias o modificadas.
- **La segunda ola tipográfica** (fuerte). Space Grotesk, Instrument Serif, Fraunces, Playfair Display, Cormorant, DM Serif; JetBrains Mono en todo lo "tech".
- **Una palabra acentuada en el titular** (fuerte). Una sola palabra en itálica serif, en color o con degradado dentro de un titular en sans ("Beautifully *Crafted*"). *En vez:* que el titular completo lleve el tratamiento.
- **Eyebrow en mayúsculas espaciadas sobre cada título** (fuerte). `text-xs uppercase tracking-widest`, más un rótulo sobre el H1 que lo repite. *En vez:* borrarlo o meter las palabras útiles en el título.
- **Mayúsculas espaciadas como "lujo"** y serif de alto contraste muy fina como atajo a "premium".
- **Cromo de plantilla en el texto** (fuerte). Metadatos unidos con punto medio ("A · B · C"), rótulos "PALABRA — fragmento", "→" al final de cada link o botón, monoespaciada para etiquetas chicas, prefijos `//`.
- **Escala tímida o plana.** 400 contra 600, saltos de 1,5×; o lo contrario, un H1 gigante centrado con el tracking apretado. *En vez:* contraste real de peso y tamaño, con una escala tipográfica de verdad.
- **Más de dos familias sin lógica, o familias mezcladas dentro de un lockup.**
- **iOS: fuente web dentro de la app** (fuerte). Inter o Roboto en vez de SF Pro o New York con estilos de texto.
- **iOS: tamaños fijos** (fuerte). `.font(.system(size: 16))` en todas partes rompe Dynamic Type.

## 3. Web y landing

- **El esqueleto del hero centrado** (fuerte). Píldora arriba ("Announcing… Read more"), H1 centrado, subtítulo, dos botones ("Get started" y "Learn more"), resplandor atrás. *En vez:* abrir con lo más característico del mundo del producto, con asimetría y el producto real a la vista.
- **Tres tarjetas de features iguales** (fuerte). `md:grid-cols-3`, ícono en cuadrado redondeado, título de dos palabras ("Seamless Integration"), una frase. *En vez:* dos a cuatro bloques de tamaños distintos, cada uno atado a un trabajo real; el ícono junto al título o ninguno.
- **El orden de secciones de stock** (fuerte). Hero, logos "Trusted by", features, testimonios, tres planes con "Most popular" al medio, FAQ en acordeón, banda de CTA centrada y footer. *En vez:* ordenar alrededor de las dudas del comprador y de su decisión.
- **Fila de métricas en el hero** (fuerte). "10,000+ teams", "99.99%", "312%". *En vez:* solo números reales, con fuente y contexto.
- **Numeración "01 / 02 / 03"** en contenido que no es una secuencia. *En vez:* numerar solo pasos y líneas de tiempo.
- **Todo centrado, grillas simétricas, el mismo `p-6` en todo.** *En vez:* cerca lo que va junto, lejos lo que se separa.
- **Logos falsos o marquesina automática** (fuerte). *En vez:* logos aprobados de clientes reales, o nada.
- **Testimonios inventados** (fuerte). "John Doe", "Jane Smith", avatares de stock. *En vez:* una cita real con nombre, o nada.
- **Bento grid.** Discutido: delata poco solo y algunas fuentes lo recomiendan para romper la simetría.
- **Pantallas de producto tratadas como landing.** Hero en el dashboard, subtítulo gris bajo cada H1, "Welcome to your Dashboard, [Name] ✨".
- **Visuales falsos.** Mascotas SVG dibujadas por el modelo, "capturas" armadas con divs. *En vez:* una captura real o un video corto en loop.
- **Huellas del generador** (fuerte). Badge "Edit with Lovable", dominio `*.lovable.app` o `*.replit.app`, `<title>Vite + React</title>`, tarjeta vacía al compartir el link.

## 4. Componentes y superficies

- **La tarjeta de shadcn de stock.** `rounded-xl border bg-card py-6 shadow-sm` con `--radius: 0.625rem` sin tocar. *En vez:* definir primario, radio, neutros y espaciado antes de construir.
- **Un solo radio para todo** (fuerte). `rounded-2xl` en todo, cada botón `rounded-full`. *En vez:* una escala chica de radios según tamaño; en iOS, radios concéntricos (el interior sigue al contenedor).
- **La misma sombra suave bajo todo.** `rgba(0,0,0,.1)` o `shadow-lg` en cada tarjeta, o borde fino más sombra ancha. *En vez:* borde o sombra, no los dos.
- **Tarjetas dentro de tarjetas** (fuerte). Una tarjeta alrededor de cada párrafo. *En vez:* agrupar con espacio, tipografía y separadores; tarjeta solo para cosas que se accionan por separado.
- **Borde de color en un lado de la tarjeta** (fuerte). 3 px o más a la izquierda o arriba, de otro color en cada tarjeta. Los diseñadores lo llaman la raya del diseño hecho por IA. *En vez:* solo si marca un estado real.
- **Glassmorphism por default.** `backdrop-blur` en tres o más superficies, `bg-white/5 border-white/10`. *En vez:* solo donde hay capas de verdad.
- **Todos los botones con el mismo peso.** *En vez:* un primario por vista; el resto, secundarios o links.
- **Fondos de grilla o de puntos decorativos, rayas.** *En vez:* una superficie lisa o una textura que sea del sistema.
- **Solo el camino feliz** (fuerte). Sin vacío, carga ni error; un spinner agregado al final; todo visible a la vez; modales para todo. *En vez:* diseñar cada estado y revelar de a poco.

## 5. Íconos y emoji

- **Emoji como íconos de interfaz** (fuerte). 🚀 ✨ ⚡ 🔥 💡 🔒 ✅ 🎯 ⭐ en navegación, títulos, features o tabs. *En vez:* un set de íconos consistente.
- **Destellos para decir "IA" o "nuevo".** En el estudio de NN/g ningún participante asoció el ícono con IA. *En vez:* una etiqueta de texto o un verbo concreto.
- **Ícono de línea fina intercambiable dentro de un cuadrado.** Lucide no es el problema; el problema es el ícono genérico en su tile.
- **SF Symbols genéricos.** `sparkles`, `bolt`, `chart.bar`, `brain` como relleno.
- **Dialectos mezclados.** Outline, relleno y emoji 3D en el mismo set. *En vez:* una grilla, un grosor de trazo y una regla de relleno.

## 6. Movimiento y háptica

- **Fade-up en cada sección** (fuerte). `initial={{opacity:0,y:20}}` con `whileInView`, `data-aos="fade-up"`, todo entrando a la vez.
- **Zoom al pasar el mouse en cada tarjeta.** `hover:scale-105`, el mismo zoom en cada imagen.
- **Rebote, pulso o shimmer en todo.** `animate-pulse`, `animate-bounce`, `transition-all`, un spring `.bouncy` en cada vista. Ojo: hay skills anti-slop que recetan springs y tab bars propias en todo; eso es la sobrecorrección y contradice la HIG.
- **Confeti en acciones rutinarias.** *En vez:* celebrar poco, solo hitos que la mayoría siente como tal, con un paso siguiente.
- **Háptica ausente o la misma en todo.** *En vez:* cada patrón con un significado, nunca el mismo para resultados opuestos, y desactivable.
- *En general:* un momento orquestado; el resto, movimiento que responde a lo que hace la persona.

## 7. Apps iOS

Las reglas de Apple para la interfaz (Liquid Glass, componentes, patrones, accesibilidad, copy) están en las Human Interface Guidelines (enlace en [fuentes.md](fuentes.md)). Esta sección cubre solo las señales de IA.

### Onboarding

- **Carrusel de tres slides** (fuerte). Ilustración, titular, puntitos y "Get Started". En el estudio de NN/g, quienes leían el tutorial no tenían más éxito y encontraban las tareas más difíciles. *En vez:* abrir en una pantalla que funciona, con defaults sensatos y tips en contexto (TipKit).
- **Muro de permisos al abrir, o pre-prompt con botón "Allow"** (fuerte). La HIG pide el permiso cuando se usa la función por primera vez. Un pre-alert lleva un solo botón "Continue", sin "Cancel" y sin dibujar la alerta del sistema; los engañosos se rechazan.
- **Cuenta o paywall antes de mostrar valor.**
- **"Welcome to X" centrado sobre un degradado.**

### Home

- **"Good morning, Alex 👋" como encabezado.** *En vez:* lo próximo real del usuario. Flighty pone la puerta de embarque y la cuenta regresiva al frente.
- **Grilla de tarjetas de stats con números fijos** (fuerte). Los prompts de dashboard de Rork piden literalmente "stat cards + progress ring + time-range selector".
- **Racha con llama y anillos de progreso como motivación por defecto.** *En vez:* una mecánica del dominio. (Not Boring) Habits cambió las rachas por 66 niveles.
- **Gráficos decorativos.** Líneas suaves sin unidades ni datos reales.

### Plataforma

- **Cinco tabs genéricas con un "+" al centro** (fuerte). Home, Explore, +, Stats, Profile. La HIG dice que las tabs son para navegar, no para acciones. *En vez:* menos tabs, etiquetas de una palabra.
- **Botón flotante tipo Material.** *En vez:* la acción principal en el extremo de la toolbar.
- **Barra de navegación o botón atrás propios** (fuerte). Rompen el gesto de volver deslizando. *En vez:* los botones estándar de atrás y cerrar.
- **Todo re-skineado, o todo como un Form de Settings sin estilo.** *En vez:* controles del sistema donde importa la predictibilidad y la autoría puesta en la pantalla firma.
- **Liquid Glass o vidrio en tarjetas de contenido** (fuerte). La HIG lo deja para la capa funcional (barras y controles), con moderación, y el vidrio transparente solo sobre foto o video.
- **Chat de IA pegado como tab o burbuja flotante.** *En vez:* herramientas directas del dominio.
- **Navegación y espaciado que cambian de pantalla en pantalla.**
- **Features que nadie pidió.** Login, perfil y menú de ajustes en una app que no los necesita.

### Paywall

- **Toggle de prueba gratis** (fuerte). Apple lo rechaza bajo la 3.1.2 por confuso.
- **Tres planes con "Most Popular" y equivalente mensual sin explicar.** El precio tiene que calzar con App Store Connect.
- **Precio tachado falso, cierre escondido o que aparece tarde.** *En vez:* precio real visible y una X visible.
- **"Unlock Premium ✨" con beneficios vagos**, lista de checks, corona, botón con degradado. La 3.1.2(c) pide decir qué recibe la persona por el precio.

### Código (lo que deja Claude Code)

- **`onTapGesture` en vez de `Button`, y botones de solo ícono sin label** (fuerte). Rompen VoiceOver.
- **APIs viejas.** `NavigationView`, `foregroundColor`, `cornerRadius`, `tabItem`.
- **Hex y tamaños escritos a mano en las vistas** en vez de tokens y estilos de texto.

## 8. Dashboards

- **Clon del `dashboard-01` de shadcn** (fuerte). Sidebar inset, header, cuatro tarjetas KPI con `bg-gradient-to-t from-primary/5`, gráfico de área interactivo y tabla. Con su copy de ejemplo: "Total Revenue $1,250.00 +12.5% Trending up this month", "Acme Inc.", `m@example.com`.
- **Chips de porcentaje y sparklines decorativas** sin eje ni línea base.
- **Solo el camino feliz** (sección 4).

## 9. Logo e identidad

### Símbolo

- **Orbe con degradado** (fuerte). Esfera de varias paradas, vacío central y rayos.
- **Nudo o espiral con un hueco al centro** (fuerte). Hay un meme viral que se ríe de cuántas marcas de IA lo comparten. *En vez:* prueba de pareidolia con gente de afuera, adolescentes incluidos.
- **Destello, asterisco o chispa** (fuerte).
- **Hexágonos y redes de nodos.**
- **Íconos de concepto de stock** (fuerte). Cohete, nube, globo, hoja, ampolleta, swoosh, anillos humanos, flecha que sube, gráfico de barras.
- **Inicial dentro de una forma** (fuerte). Letra en un círculo, un escudo o un cuadrado redondeado con degradado; monogramas intercambiables.
- **Conceptos apilados.** Varias ideas pegadas que se ven insertadas.
- **Simetría radial y centrado perfecto.** *En vez:* asimetría y tensión con intención.
- **Necesita un párrafo para explicarse.**
- **Line art botánico fino** en beauty y wellness.

### Wordmark

- **Sans de "blanding"** (fuerte). Geométrica o neo-grotesca, muchas veces en minúsculas, con el espaciado por defecto. *En vez:* letras dibujadas o modificadas, con carácter.
- **Fuente gratis sin modificar** (fuerte).
- **Trucos de letra.** A sin travesaño, E de tres barras, un punto en vez del travesaño, "oo" como infinito, x estirada. Solo si el truco es natural, simple y quiere decir algo.
- **"AI" o ".ai" en el lockup.**
- **Punto final o punto medio pegado al nombre.**

### Construcción

- **Raster en vez de vector; texto falso o letras derretidas** (fuerte).
- **Ilustración en vez de marca; brillo, 3D, glow, "inflado"** (fuerte). *En vez:* plano y funcionando en una tinta.
- **Sin correcciones ópticas.** Sin sobrepaso en las curvas, sin compensar el blanco sobre oscuro, perfecto en la grilla pero torcido al ojo, contraformas sin diseñar.
- **Falla chico o en una tinta** (fuerte).
- **Variantes que no son de la misma familia;** cada revisión regenera un diseño entero.
- **Parecido accidental con marcas existentes** (riesgo legal). Además, lo generado solo por IA no se puede proteger con copyright en EE. UU. *En vez:* guardar bocetos y ediciones como prueba de autoría humana, y buscar en registros de marca.

## 10. Naming

- **Sufijos -ly, -ify, -fy, -io** (fuerte).
- **Celestes y míticos** (fuerte). Nova, Sol, Atlas, Athena, Sage, Iris, Aria. Son los nombres que los propios chatbots eligen para sí mismos.
- **Abstracciones latinoides.** Lumen, Aura, Zen, Nexus, Vertex.
- **Portmanteaus aliterados en CamelCase** (fuerte). VirtuVerse, CogniCreate. La IA los propone aunque se le prohíba la aliteración.
- **Referencias obvias al rubro.** Turing o Lovelace para IA, y su equivalente en cada categoría.
- **"AI" en el nombre.**
- *En vez:* un nombre con una historia propia (una palabra al revés, o una palabra del oficio: en ajedrez, un *ply* es la jugada de un jugador), revisado contra App Store, dominio y registro de marca.

## 11. Identidad verbal

- **Valores de cartel** (fuerte). Innovación, integridad, confianza, calidad, pasión, cliente primero, sustentabilidad. Fallan la prueba del contrario: nadie diría lo opuesto. *En vez:* valores específicos con una conducta que los demuestra ("precios honestos, siempre").
- **Tríada de adjetivos intercambiable** (fuerte). "Cercano, moderno, profesional"; "clean, modern, bold".
- **Arquetipos de manual.** Sabio, Héroe, Explorador como ejercicio escolar; el marco de los 12 arquetipos no tiene base científica. *En vez:* usarlo solo como brújula.
- **Fórmulas de tagline** (fuerte). "X para cada Y", paralelos tipo "Diseñado para el confort, hecho para el estilo", "X, reimagined", "The future of X is here", "Built for Y", "Todo en un solo lugar", "Build faster. Ship smarter."
- **Lenguaje de magia.** "Sin esfuerzo", *effortless*, tono de oráculo.
- **Voice doc sin frases reales**, sin lista de palabras prohibidas y sin ejemplos.
- **El paquete genérico completo** (fuerte como conjunto). Símbolo abstracto que podría significar cualquier cosa, sans de buen gusto, paleta contenida y palabras intercambiables.

## 12. Copy en inglés: vocabulario y fórmulas

- **Vocabulario LLM académico** (fuerte cuando se junta). Delve, tapestry, intricate, pivotal, underscore, showcase, realm, testament, foster, crucial.
- **Adjetivos de hype** (fuerte). Seamless, intuitive, innovative, robust, cutting-edge, next-gen, game-changing, end-to-end. *En vez:* el comportamiento ("syncs in 2 s", "works offline").
- **Verbos inflados** (fuerte). Unlock, elevate, empower, harness, leverage, streamline, revolutionize, transform, supercharge, unleash. *En vez:* el verbo real del usuario (track, pause, split).
- **Aperturas de época** (fuerte). "In today's fast-paced world", "In the digital age", "In an era where".
- **Esquivar el "is".** Serves as, stands as, plays a vital role, a testament to.
- **Folleto.** Vibrant, nestled, in the heart of, rich heritage, breathtaking.
- **"Whether you're a beginner or a pro…"** *En vez:* escribirle a una persona.
- **Deriva de 2025.** Core, modern, quietly, deeply, fundamentally.
- **Headlines de plantilla** (fuerte). "The AI-powered X for modern Y", "Your all-in-one X", "Not a feature. A platform."

## 13. Copy en español (Chile)

- **Calcos motivacionales** (fuerte). "Desbloquea tu potencial", "Lleva tu X al siguiente nivel", "Eleva tu experiencia", "Potencia tu…", "Empodérate". *En vez:* un verbo concreto dicho como se dice acá: "Ordena tus gastos en 2 minutos".
- **"Descubre" como verbo por defecto** de titulares y botones. *En vez:* nombrar la acción.
- **Adjetivos vacíos** (fuerte). Integral, robusto, innovador, holístico, disruptivo, ecosistema, sinergia; "de manera fluida", "sin complicaciones", "sin fisuras".
- **Muletillas de locutor** (fuerte en textos largos). "Es importante destacar que", "Cabe señalar", "En este sentido", "En el mundo actual", "En definitiva", "En resumen". *En vez:* borrar y partir por el punto.
- **Verbos de oficina.** Utilizar, implementar, optimizar, gestionar, llevar a cabo, fomentar, "juega un papel fundamental". *En vez:* usar, hacer, armar, ordenar.
- **"No solo… sino también…"** (fuerte). *En vez:* decir la segunda mitad sola.
- **Gerundio de remate** (fuerte, y además error gramatical). "…, garantizando una experiencia fluida". *En vez:* cerrar la frase y empezar otra.
- **Calcos de interfaz.** "Aplicar ahora" (en Chile se postula). "Obtener" está bien como botón de Apple, pero "Obtén acceso" suena traducido.
- **Title Case en español** (fuerte). "Descubre Tu Nuevo Estilo". En español va mayúscula solo la primera palabra y los nombres propios.
- **Raya a la inglesa** (muy fuerte en español). Una sola raya con espacios antes de un remate: "Todo en un lugar — y gratis". En español la raya de inciso va en pares y pegada al texto del inciso. *En vez:* coma, punto o dos puntos.
- **Exceso de ¡!** en cada pantalla. El tic es la cantidad, no la falta del signo de apertura.
- **Mezcla de tú y usted, o fuga de voseo** (fuerte). Elegir tú o usted según la marca y no salirse nunca.
- **Español neutro de doblaje.** A los hispanohablantes les suena seco y vagamente ajeno. *En vez:* en productos para Chile, palabras de acá y revisión local.

## 14. Estructura y puntuación (inglés y español)

- **Paralelismo negativo** (fuerte). "It's not an app, it's a ritual", "No es una app, es un hábito", "Not X. Not Y. Just Z." *En vez:* decir Y directo.
- **Regla de tres con casi-sinónimos** (fuerte). "Rápido, simple, intuitivo". *En vez:* dos cosas, o una con su prueba.
- **Fragmentos staccato** (fuerte). "Simple. Fast. Secure." *En vez:* una frase de verdad.
- **Pregunta y revelación** (fuerte). "The result? …", "¿El resultado? …"
- **Falso suspenso** (fuerte). "Here's the thing", "Here's the kicker", "Y honestamente…"
- **Voz de profesor.** "Let's dive in", "Let's break it down", "Imagine a world where…", "Imagina un mundo donde…"
- **Remate de importancia.** "…, ensuring a seamless experience".
- **Rangos falsos.** "From beginners to pros", "Desde principiantes hasta expertos".
- **Inflar lo que está en juego.** "This changes everything", "Redefine cómo…"
- **Rotar sinónimos** para lo mismo: app, plataforma, herramienta, solución. En una interfaz además es un bug. *En vez:* un nombre por cosa, en todas partes.
- **Autoridad vaga.** "Los expertos coinciden", "Experts agree".
- **Ritmo uniforme.** Todas las frases del mismo largo.
- **Raya en exceso** (fuerte). *En vez:* coma, punto o dos puntos; como mucho una por bloque.
- **Viñetas con etiqueta en negrita** (fuerte). "**Seamless sync:** …". *En vez:* prosa o viñetas cortas sin etiqueta.
- **Emoji como viñetas o títulos** (fuerte). ✅ 🚀 ✨ 💡.
- **Decoración unicode.** → ≈ ⚠ en el texto.

## 15. Microcopy (botones, errores, vacíos, notificaciones)

- **Errores con interjección** (fuerte). "Oops! Something went wrong 😅", "¡Ups! Algo salió mal". La HIG dice que "oops" suena poco sincero. *En vez:* qué pasó y cómo se arregla: "No se pudo guardar. Revisa tu conexión y vuelve a intentar."
- **Botones tiernos** (fuerte). "Let's get started!", "Let's do it!", "¡Comencemos!". *En vez:* verbo más objeto ("Crear partida"), y la misma palabra en el botón y en la confirmación ("Publicar", "Publicado").
- **Celebrar todo.** "You're all set! 🎉", "¡Todo listo! 🎉" después de cada acción.
- **Vacíos muertos.** "Nothing here yet!" *En vez:* por qué está vacío y un botón para salir de ahí.
- **"Nosotros" ambiguo.** "We're having trouble…" *En vez:* "Unable to load…"
- **Etiquetas genéricas.** Submit, Click here, Sí y No. *En vez:* la acción real ("Salir" y "Quedarme").
- **Persona forzada.** Slang Gen Z o chistes en un flujo de plata. El tono cambia según el momento; la voz no.
- **Push y paywall de cliché.** "Don't miss out!", "Hey there! 👋", "Take your X to the next level".
- **Texto que se filtró de la plantilla o del chat.** Lorem ipsum, "Your Company", Acme, "Get Started" tres veces en la misma página.

## 16. Imagen: ilustración, foto y 3D

- **Piel de cera, bokeh en todo, luz perfectamente pareja sin sombras ni grano** (fuerte). *En vez:* foto real con poros, grano y luz direccional.
- **Sonrisas huecas en escena de stock** (fuerte). Tres profesionales sonriéndole a un gráfico de torta. *En vez:* usuarios reales o el fundador, en foto espontánea.
- **Texto chico falso y errores de anatomía** (fuerte). Letreros con casi-palabras, aros que no calzan, dedos de más. *En vez:* nunca usar texto generado; la tipografía se pone a mano.
- **Escena que no cuadra.** Sombras contra la luz, perspectiva que no converge, multitudes y objetos repetidos que se deshacen al fondo.
- **Tinte amarillo cálido** de las imágenes de ChatGPT, o grading "cinematográfico" con encuadre simétrico.
- **Ilustración sin aire** (fuerte). Cada centímetro lleno de objetos. *En vez:* sacar elementos hasta que respire un foco.
- **Estilos que chocan** (fuerte). Vector plano, objeto 3D fotorrealista y letras con textura en el mismo cuadro. *En vez:* una lengua visual por set.
- **"Mugre IA".** Micro-textura irregular que ningún material real produce, y que empeora con cada re-edición.
- **Personaje que cambia entre imágenes** de un set (fuerte en sets). *En vez:* hoja de personaje y un ilustrador, o un sistema cerrado.
- **Corporate Memphis** (cabezas chicas, brazos de goma, pastel) **y su sucesor, la mascota-blob tierna** con ojos de orbe.
- **3D de plástico brillante "puffy"** (fuerte). Objetos de caramelo bajo luz de softbox; ya se venden como presets de prompt.
- **Formas abstractas flotando, cromo iridiscente, morado cósmico.**
- **Personas o productos generados en avisos.** En un estudio de NIQ (diciembre de 2024) la gente detectó la mayoría de los avisos hechos con IA sin que se lo dijeran y los recordó menos; en el de Getty (unas 30.000 personas), las marcas que los usan se ven peor.

## 17. Ícono de app

Cómo se arma el ícono en capas con Icon Composer lo explican las Human Interface Guidelines de Apple (App icons); qué pedir en el brief está en el skill `branding`, archivo `apps.md`. Esta sección cubre solo las señales de IA.

- **Efectos horneados** (fuerte). Objeto 3D sobre un squircle con degradado, brillos pintados, sombras, biseles, glow. Según Apple, los efectos del sistema son dinámicos y los propios quedan estáticos y chocan. *En vez:* formas planas superpuestas, y que Liquid Glass ponga la luz.
- **Sobre-detallado** (fuerte). Líneas finas y esquinas agudas que desaparecen a tamaño chico. *En vez:* una idea en las menos formas posibles.
- **Foto, captura, UI copiada o palabras en el ícono** (fuerte). Como mucho, una letra si es el nombre.
- **Un bitmap plano de IA.** No se puede separar en las capas que pide Icon Composer. *En vez:* bocetos, capas SVG y el archivo `.icon`.
- **Liquid Glass mal usado.** Capas pre-enmascaradas, bordes difuminados, vidrio sobre un raster que ya trae efectos, fondos con degradado propio, variantes oscura, transparente o tintada que faltan o cambian elementos.
- **Letra en un cuadrado redondeado con degradado.**
- *Prueba:* a tamaño de Settings, dentro de una carpeta y en la pantalla de inicio al sol.

## 18. App Store: capturas, video y ficha

Lo que pide Apple para la ficha (specs, reglas de revisión, textos, previews) está en las App Review Guidelines y las Marketing Guidelines (enlaces en [fuentes.md](fuentes.md)). Esta sección cubre solo las señales de IA.

- **Titulares sin peso** (fuerte). "Boost your productivity", "Track Smarter", "Stay Focused", "Powered by AI". *En vez:* texto corto que suma a la imagen, no que la describe (lo pide Apple en su guía de capturas). Que diga algo concreto, el beneficio o el resultado ("Tu tiempo se lee desde el otro lado del tablero"), no un eslogan vacío ("Juega mejor"). Localizado.
- **Teléfonos inclinados flotando sobre un degradado** (fuerte). Las Marketing Guidelines de Apple piden los equipos de frente, sin inclinar, sin cortar y sin agregar reflejos ni sombras. *En vez:* marco oficial de frente, o la UI agrandada sin marco.
- **La decoración se come al producto.** *En vez:* un fondo tranquilo en el color de la marca.
- **UI que no está en el build** (fuerte). Pantallas renderizadas o del roadmap: rechazo bajo 2.3 y 2.3.1. *En vez:* capturar del build que se envía; iterar solo encuadre y textos.
- **Prueba social falsa** (fuerte). "4.9 stars from 12,000 reviews" en una app con tres, "#1 App", laureles caseros, "As seen in Forbes". Falsear reseñas o rankings puede costar la cuenta de developer.
- **Datos vacíos o de plantilla.** Dashboards vacíos, John Doe, lorem ipsum, $99.99. *En vez:* datos ficticios realistas del dominio (la 2.3.9 pide que sean ficticios).
- **Cuadros clonados.** El mismo layout y la misma pantalla con otro texto. *En vez:* un tratamiento visual, un trabajo distinto por cuadro y una historia de punta a punta.
- **Splash o logo sobre degradado como primer cuadro.** Los primeros uno a tres cuadros salen en la búsqueda y casi nadie llega al quinto. *En vez:* la app en uso desde el primero.
- **Video con manos, B-roll ajeno, transiciones llamativas o morphing de IA** (fuerte). *En vez:* grabación de pantalla del equipo; los primeros segundos fuertes, porque el preview parte sin sonido.
- **Primera frase de la descripción desperdiciada,** keyword stuffing, lista de features con ✅. Es la única frase que se ve antes de "más".
- **Clon de una categoría saturada** (fuerte). La guideline 4.3(b) nombra apps de citas, linternas, efectos de sonido, wallpapers, timers simples y adivinación como categorías donde solo entran apps con una experiencia "significativamente distinta o mejor". La diferencia tiene que verse en la ficha, no solo existir dentro de la app.

## 19. Mockups y presentación

- **Mockups de fantasía** (fuerte). Tarjetas de visita flotando, papelería con sombra dramática, objetos entre nubes, tote bags, letreros en fachadas, afiches pegados en la calle, merch de un sistema que nunca se hizo, un teléfono en una mano estirada, el laptop en la mesa de la cocina.
- **El render impecable.** Sin grano, luz perfecta.
- **Renders 3D de equipos Apple, o un teléfono genérico con detalles de Apple.** Las guías de marketing de Apple no los permiten.
- *En vez:* aplicaciones reales, impresas si se puede, en los lugares donde la marca va a vivir de verdad.

## 20. Packaging y físico

- **Envase de stock con un logo serigrafiado.** Los mismos frascos de distribuidor hacen que todas las marcas se vean iguales.
- **Frasco ámbar con gotario, etiqueta blanca mínima y serif** (fuerte en beauty). El linaje Aesop, ya masivo.
- **Kraft con hojita como señal de "natural".** Sustentabilidad de utilería.
- *En vez:* tapa propia, peso, acabado mate, hot-stamping, etiqueta propia; un detalle físico que nadie más tenga.

## 21. La segunda ola: los tics del anti-tic

Es lo que sale hoy cuando a un modelo se le pide que no se vea hecho con IA. Delata tanto como el morado, y es lo que más se cuela cuando el brief ya prohibió lo obvio:

- **Crema, serif display y terracota** (fuerte). Fondo cerca de `#F4F1EA`, `#FAF8F5` o `#F5F1E8` (`bg-stone-50`), serif de alto contraste, acento cerca de `#D97757`, que es el acento de la propia interfaz de Claude. WIRED lo bautizó *tasteslop* (junio de 2026).
- **Crema con verde bosque o salvia.** Cerca de `#15573A`.
- **Casi negro con un solo acento ácido.** `#0B0B0B` o `#111` con verde lima o bermellón.
- **Diagramación de diario.** Filetes finos, radio cero y columnas densas tipo periódico.
- **Las fuentes "con carácter" de siempre.** Space Grotesk, Instrument Serif, Fraunces; monoespaciada para etiquetas.
- **El cromo de plantilla** de la sección 2: eyebrows, punto medio, "→", "01 / 02".

Ninguna está prohibida si el proyecto la justifica. Ninguna se usa sin una razón escrita en el design system.

---

# Qué hacer en vez

1. **Decidir antes de generar.** El design system (o un `design.md`) fija 4 a 6 colores con nombre, rol y razón; las fuentes y su papel; el concepto de layout; radio, sombra y densidad; y una palabra de sensación. Va donde la herramienta lee instrucciones fijas: el `CLAUDE.md`, el brief, el Knowledge del proyecto.
2. **Reglas que se puedan verificar mirando.** "Sombra dura sin blur" sirve; "padding generoso" no.
3. **Partir del mundo del producto.** Su industria, sus materiales, sus objetos y su jerga. Flighty partió del tablero de salidas del aeropuerto; Halide de una cámara ("hicimos una cámara, no una app"); una app de reloj de ajedrez puede partir del reloj de torneo y su pantalla partida.
4. **Referentes de fuera del rubro y fuera del feed.** Libros, archivos, arquitectura, señalética, diseñadores con nombre (Kamekura, Crouwel). Dribbble y Pinterest son parte de donde sale el promedio. Se copian sistemas, no assets. Prueba: si alguien puede nombrar de dónde lo sacaste, tomaste demasiado.
5. **La audacia en un solo lugar.** Una interacción firma o un elemento memorable, y el resto tranquilo y nativo. (Not Boring pone seis capas de feedback en un checkbox y deja los controles estándar al lado.) Antes de entregar, sacar un accesorio.
6. **Color con significado.** Un dominante, un acento y neutros teñidos; cada color con un trabajo.
7. **Prueba real.** Capturas del build, números con fuente, el nombre del fundador, testimonios de verdad.
8. **Los estados difíciles primero.** Error, vacío, sin conexión y mucho contenido.
9. **Direcciones, no rerolls.** Pedir direcciones de verdad distintas, compararlas lado a lado y ajustar una sección a la vez.
10. **Copy desde el habla.** Frases que el usuario final o el equipo dirían, palabras prohibidas en el voice doc, leer en voz alta. Español de Chile con tú.
11. **La IA aguas arriba.** Exploración, moodboard y opciones con IA; la decisión y el pulido final, de una persona. El ícono y las ilustraciones clave se encargan cuando importan.

---

# Cómo va en un brief

Todo brief de identidad, pantallas o assets para Claude Design, Figma Make, Midjourney o Claude Code termina con esta sección, adaptada al encargo:

```
## Clichés que hay que evitar

### Del diseño hecho por IA
- [5 a 10 señales de este catálogo con más riesgo en ESTE encargo, con valores concretos]

### Del rubro
- [los lugares comunes de la categoría: el caballo y la corona en ajedrez,
  el frasco ámbar en beauty, el anillo de progreso en hábitos]
```

Reglas del brief:

- **Elegir, no pegar.** Las señales se escogen según el encargo. El catálogo entero diluye el brief y la herramienta lo ignora.
- **Primero lo que sí.** Referentes con nombre, reglas de construcción y paleta con hex van antes de la lista de lo que no.
- **Sin palabras vacías en el prompt.** Nada de "cinematic", "8K", "hyper-detailed", "studio lighting", "modern", "clean" o "premium" sin decir qué significan en este proyecto.
- **Direcciones distintas.** Pedir conceptos que de verdad se diferencien, no variantes pulidas de uno.
- **Siempre incluir la segunda ola** (sección 21) cuando el encargo busca "personalidad", porque es adonde se escapa la herramienta.
- **En identidad, wordmark e isotipo** siempre.

---

# Revisar lo que entrega una herramienta

Antes de mostrárselo al usuario:

1. **Contar las señales** del catálogo (0–1 pasa, 2–3 se revisa, 4 o más se rehace).
2. **Correr las pruebas** que apliquen: logo tapado, tamaño, estados y voz alta.
3. **Mirar la segunda ola** en particular.
4. **Reportar en palabras simples** qué se encontró y el arreglo propuesto. Con 4 señales o más, proponer rehacer en vez de parchar.
