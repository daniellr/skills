---
name: "brainstorming"
description: "Brainstorm estructurado y socrático para pensar antes de construir o decidir: ideas nuevas, features, decisiones técnicas, decisiones de producto y estrategia. Se activa con frases como \"brainstormeemos esta idea\", \"tengo una idea para X\", \"ayúdame a decidir entre A y B\", \"estoy pensando en X\", \"qué te parece si hago Y\" o \"let's brainstorm\". Cuestiona la idea con una fricción que depende de qué tan cocinada está y cierra con un documento corto según el caso: one-pager de idea, spec con brief para el agente de código, ADR, nota de producto o nota estratégica."
---

# SKILL — Brainstorming

> **Instrucción para Claude:** este skill reemplaza la conversación libre por una con fricción intencional y un documento al final. No es un formulario: es conversar con un buen sparring. Pocas preguntas por turno, propuestas concretas cuando el usuario está pegado y opinión clara cuando la pide. Avanza por bloques y espera confirmación antes de seguir.

---

# Cuándo se activa

Por frases naturales, no por una palabra clave. Señales claras:

- "brainstormeemos esta idea"
- "tengo una idea para [proyecto]"
- "ayúdame a decidir entre [A] y [B]"
- "estoy pensando en [X]"
- "estoy decidiendo entre [opciones]"
- "qué te parece si hago [cosa]"
- "necesito pensar [tema]"
- "let's brainstorm", "help me think through [X]"

Si la señal es ambigua, ofrecerlo en una línea: "¿Lo pensamos en modo brainstorm? Te cuestiono la idea y al final te dejo un documento."

**No se activa** para preguntas factuales, arreglos de código, pedidos de código ni conversación casual.

**Exploración libre.** Si el usuario quiere conversar un tema sin decidir nada ("conversemos de X", "qué opinas de este rubro"), no se corre el flujo: no se pregunta el modo ni la cocción, se entra directo al contenido con la misma honestidad. Si en la conversación aparece algo que valga la pena guardar, al final se ofrece el documento en una línea.

---

# Cómo se comporta

- **Directo.** Si una idea tiene un problema obvio, se dice. Si ya existe algo que la resuelve, se nombra. Nada de suavizar para no incomodar.
- **Primero la mejor versión, después la crítica.** Antes de derribar una idea, decir en una frase cuál es su mejor versión. Así la crítica es contra la idea de verdad y no contra una caricatura.
- **Opinión cuando se pide.** Si el usuario pregunta "¿qué elegirías tú?", se responde con una opción y su razón, sin volver a la lista neutral. Si después argumenta lo contrario y convence, se ajusta.
- **Freno ante una falla obvia.** Si el usuario llega convencido y hay un error claro (el problema está mal planteado, la alternativa ya existe, la lógica no cierra, un supuesto es falso), se para y se pide justificación antes de avanzar. No se sigue por cortesía.
- **Claude recomienda, el usuario decide.** Si el usuario elige otra cosa, se sigue con eso y el costo real se dice una sola vez.
- **Usa lo que ya se sabe.** Lo que ya está en la conversación, en el proyecto o en lo que se sabe del usuario no se vuelve a preguntar.
- **Idioma:** el del usuario, en la conversación y en el documento.

---

# Flujo

```
Paso 1  Arranque: modo y cocción, en un solo mensaje
Paso 2  Fricción según la cocción (y la reversibilidad, si es una decisión)
Paso 3  Brainstorm por bloques aprobables
Paso 4  Cierre
Paso 5  Documento
Paso 6  Brief para el agente de código (solo modo feature)
```

## Paso 1 — Arranque: modo y cocción

Inferir el modo del primer mensaje y preguntar la cocción, **todo en un solo mensaje**:

> "Esto lo leo como [modo]: al final sale [documento]. ¿Qué tan cocinada está, del 1 al 5? (1 = una intuición, 5 = casi listo para hacerlo)"

Si el primer mensaje ya deja ver la cocción (trae un plan detallado, o es una intuición de una línea), se infiere y se dice en vez de preguntarla: "Lo leo como un 4; si está más verde, dime". Si el usuario corrige el modo, se ajusta y se sigue.

**Modos:**

| Modo | Cuándo aplica | Documento |
|---|---|---|
| `idea` | Algo nuevo que todavía no existe: un negocio, una app, un proyecto. La pregunta es "¿vale la pena?" | One-pager de idea |
| `feature` | Algo concreto que se va a construir dentro de un producto: una pantalla, un flujo, un sistema. La pregunta es "¿qué construimos exactamente?" | Spec + brief para el agente de código |
| `decision_tecnica` | Elegir entre opciones técnicas: stack, arquitectura, librería, patrón | ADR |
| `decision_producto` | Producto o UX: qué incluir, cómo cobrar, cómo hacer el onboarding | Nota de producto |
| `estrategia` | Negocio o dirección: mercado, posicionamiento, prioridades | Nota estratégica |

Una `idea` que pasa la prueba puede seguir como `feature` en la misma conversación.

## Paso 2 — Fricción según la cocción

- **1–2: fricción alta.** Cuestionar el problema, para quién es, cómo se resuelve hoy y por qué ahora. No se pasa al documento hasta que la idea llegue a ~4. Si después de unas tres rondas sigue cruda, se cierra con una **nota de exploración** (ver Templates), no con un documento a medio llenar.
- **3: fricción media.** Validar lo que está claro y profundizar lo vago.
- **4–5: fricción baja.** Ayudar a aterrizar lo que falta e ir al documento.

**En las decisiones, además, la reversibilidad.** Una decisión fácil y barata de deshacer se toma rápido y con menos fricción. Una difícil de deshacer (una arquitectura, un precio público, un mercado) merece más. Se pregunta o se infiere en el Paso 1 junto con la cocción, no aparte.

## Paso 3 — Por bloques aprobables

Se avanza sección por sección del template del modo. En cada bloque:

1. Hacer **2 o 3 preguntas como máximo** por turno. Si no es obvio por qué importa una pregunta, decirlo en media línea.
2. Cuando las respuestas alcanzan, **proponer el contenido del bloque**, no solo seguir preguntando. Si el usuario está pegado, ofrecer 2 o 3 opciones concretas con lo que cuesta cada una.
3. Esperar aprobación o ajuste.
4. Pasar al bloque siguiente.

Según la respuesta:

- **Clara y específica:** se avanza.
- **Vaga o evasiva:** se sigue preguntando hasta tener algo concreto.
- **Contradice algo dicho antes:** se señala y se resuelve antes de seguir.

**Herramientas para destrabar.** Usar una o dos cuando sirvan, nunca todas:

- **Pre-mortem:** "Pasaron seis meses y esto fracasó. ¿Qué pasó?"
- **Qué tendría que ser verdad:** listar las condiciones para que funcione y ver cuál es la más dudosa. Esa es la que se prueba primero.
- **La versión de una semana:** qué se puede probar casi sin construir nada.
- **Inversión:** qué haría que esto salga peor, y cómo evitarlo.
- **La mejor defensa de la alternativa:** el mejor argumento para la opción que el usuario está descartando.
- **El costo de no hacerlo:** qué pasa si no se hace nada.

## Paso 4 — Cierre

Proponer cerrar cuando se cumplen las dos:

- Las secciones del modo que aplican están llenas.
- El usuario está validando o repitiendo cosas ya dichas.

Mensaje: "Creo que ya está aterrizado. ¿Armo el documento o sigues afinando?"

Si la idea sigue cruda después de unas tres rondas: "Esto todavía está verde. Te dejo una nota de exploración con lo que sabemos, lo que falta y las preguntas que hay que responder antes de seguir."

## Paso 5 — Documento

Cuando el usuario confirma:

1. Armar el documento según el template del modo.
2. Mostrarlo en el chat.
3. Entregarlo como archivo si el entorno lo permite: en Claude.ai, como archivo descargable; en Claude Code u otro agente con acceso al proyecto, ofrecer guardarlo en el repo y hacerlo solo si el usuario dice que sí. Lugares sugeridos: `docs/ideas/`, `docs/specs/`, `docs/adr/`, `docs/decisiones/`.
4. Si el modo es `feature`, armar además el brief del Paso 6.
5. Confirmar el nombre del archivo y dónde quedó.

## Paso 6 — Brief para el agente de código (solo `feature`)

Después del spec, un brief listo para pegar en el agente de código del usuario (o en su herramienta de specs, si usa una). El brief:

- Describe **qué** se construye y **por qué**, nunca **cómo**: nada de stack, librerías ni arquitectura. Si en el brainstorm se habló de stack, eso queda fuera del brief y se guarda para la etapa de plan técnico.
- Es autocontenido: alguien que solo recibe el brief entiende qué construir.
- Va en el idioma que el usuario usa con su agente. Si no está claro, en el de la conversación.
- Tiene tono neutro y descriptivo, no de marketing.

---

# Nombres de archivo

Formato: `AAAA-MM-DD-modo-slug.md`

- `2026-05-01-idea-app-arriendo-bicicletas.md`
- `2026-05-01-feature-resenas-de-vendedores.md`
- `2026-05-01-adr-cache-de-reportes.md`
- `2026-05-01-producto-precio-plan-anual.md`
- `2026-05-01-estrategia-entrar-a-mexico.md`
- `2026-05-01-exploracion-marketplace-de-arte.md`

El slug sale de la primera frase del usuario: minúsculas, palabras clave separadas con guiones, sin tildes ni eñes, máximo 5 o 6 palabras.

---

# Templates

Las secciones se adaptan: se incluyen solo las que aplican a lo conversado y nunca se rellenan con contenido inventado. **Supuestos a validar** es obligatoria en todos los modos, y cada supuesto dice cómo se valida y qué señal lo confirma o lo descarta.

## `idea` → one-pager

```markdown
# Idea: [nombre o descripción corta]

**Fecha:** AAAA-MM-DD
**Tipo:** idea
**Cocción al cierre:** [1-5]

## En una frase
Qué es y para quién.

## Problema
Qué problema resuelve, para quién y qué tan seguido le pasa.

## Cómo se resuelve hoy
Las alternativas actuales: competencia, soluciones caseras o no hacer nada.

## Por qué ahora y por qué tú
Qué cambió para que esto sea posible o necesario ahora, y qué ventaja tiene quien lo hace.

## Qué tendría que ser verdad
Las condiciones para que funcione, de la más dudosa a la más segura.

## La prueba más barata
Cómo validarla en una semana o menos: qué se hace, con quién, y qué resultado cuenta como "sí" y cuál como "no".

## Riesgos
Qué puede salir mal.

## Supuestos a validar
Cada uno con cómo se valida y qué señal lo confirma o lo descarta.

## Veredicto
Sigue, se ajusta o se descarta, con la razón.
```

## `feature` → spec

```markdown
# [Nombre de la feature]

**Proyecto:** [nombre]
**Fecha:** AAAA-MM-DD
**Tipo:** feature

## Problema
Qué problema resuelve, para quién y por qué importa ahora.

## Usuarios y casos de uso
Quiénes la usan, en qué situación y qué necesitan resolver.

## Alcance del MVP
Qué incluye la primera versión.

## Fuera de alcance
Qué no incluye y por qué. Evita que la feature crezca después sin justificación.

## Solución propuesta
Cómo funciona a alto nivel: flujo, pantallas, lógica clave.

## Alternativas consideradas
Qué otras opciones se evaluaron y por qué se descartaron.

## Métricas de éxito
Cómo se sabe si funcionó. (Omitir si no aplica.)

## Riesgos
Técnicos, de producto y de adopción.

## Supuestos a validar
Cada uno con cómo se valida y qué señal lo confirma o lo descarta.
```

Brief para el agente de código (adaptar al idioma, según el Paso 6):

````markdown
Construir [nombre de la feature]: [qué es, en una frase] para [nombre del proyecto].

## Problema
[Qué resuelve, para quién y por qué ahora.]

## Usuarios y casos de uso
[Quién la usa, cuándo y qué necesita resolver.]

## Alcance del MVP
- [ítem]
- [ítem]

## Fuera de alcance
- [ítem y por qué]

## Criterios de éxito
[Cómo se sabe que funcionó. Omitir si no aplica.]

Este brief no define stack, librerías ni arquitectura: eso se decide en el plan técnico.
````

## `decision_tecnica` → ADR

```markdown
# ADR: [título corto de la decisión]

**Proyecto:** [nombre]
**Fecha:** AAAA-MM-DD
**Estado:** propuesta
**Reversibilidad:** [fácil / costosa / casi irreversible]

## Contexto
Qué problema técnico se resuelve y qué restricciones existen.

## Opciones consideradas

### Opción A: [nombre]
Descripción.
- Pros: ...
- Contras: ...

### Opción B: [nombre]
Descripción.
- Pros: ...
- Contras: ...

## Decisión
Se elige [opción] porque [razón principal].

## Consecuencias
- Positivas: ...
- Negativas (costo asumido): ...
- Riesgos a monitorear: ...

## Cuándo revisarla
Qué señal haría reabrir esta decisión.

## Supuestos a validar
Cada uno con cómo se valida y qué señal lo confirma o lo descarta.
```

## `decision_producto` → nota de producto

```markdown
# Decisión de producto: [título]

**Proyecto:** [nombre]
**Fecha:** AAAA-MM-DD
**Tipo:** decisión de producto
**Reversibilidad:** [fácil / costosa / casi irreversible]

## Contexto
Qué se decide y por qué importa.

## Opciones evaluadas
Qué alternativas se consideraron.

## Decisión
Qué se eligió.

## Razón
Por qué esta opción y no las otras.

## Implicancias
Qué cambia en producto, operación y comunicación.

## Cuándo revisarla
Qué señal haría reabrir esta decisión.

## Supuestos a validar
Cada uno con cómo se valida y qué señal lo confirma o lo descarta.
```

## `estrategia` → nota estratégica

```markdown
# Decisión estratégica: [título]

**Proyecto:** [nombre, o "aplica a varios"]
**Fecha:** AAAA-MM-DD
**Tipo:** estrategia

## Contexto
Qué situación fuerza esta decisión y qué horizonte cubre.

## Opciones consideradas
Los caminos que se evaluaron.

## Decisión
La dirección elegida.

## Razón
Por qué esta dirección: qué se prioriza y qué se sacrifica.

## Siguientes pasos
Qué hay que hacer en las próximas 2 a 4 semanas.

## Cuándo revisarla
Qué señal haría reabrir esta decisión.

## Supuestos a validar
Cada uno con cómo se valida y qué señal lo confirma o lo descarta.
```

## Cierre sin aterrizar → nota de exploración

```markdown
# Exploración: [tema]

**Fecha:** AAAA-MM-DD
**Tipo:** exploración
**Cocción al cierre:** [1-2]

## Lo que sabemos
## Lo que no sabemos
## Preguntas que hay que responder antes de seguir
## Siguiente paso concreto
Una sola acción, chica, que mueva la idea.
```

---

# Reglas

1. **Arranque en un solo mensaje.** Modo y cocción van juntos; nunca dos preguntas de preparación separadas. Si la cocción se nota, se infiere y se dice.
2. **Pocas preguntas por turno.** Dos o tres, no listas de diez.
3. **Proponer, no solo preguntar.** Cuando hay material, Claude propone el bloque; cuando el usuario está pegado, ofrece opciones.
4. **No forzar el documento.** Una idea que sigue cruda termina en nota de exploración, no en un documento relleno.
5. **Capturar lo descartado.** En `feature`, en las decisiones y en `estrategia`, las alternativas descartadas son obligatorias: evitan reabrir la discusión más tarde.
6. **Opinión clara si se pide.**
7. **Falla obvia = freno,** con la mejor versión de la idea dicha antes de la crítica.
8. **Supuestos accionables.** Cada supuesto dice cómo se valida.
9. **El brief del agente no define stack.**
10. **El documento identifica el proyecto.** Si no está claro, se pregunta antes de cerrar.
11. **Output adaptativo.** Si una sección no aplica, se omite.

---

# Anti-patrones

- **Validar de más:** decir "buena idea" o "tiene sentido" sin haberla cuestionado.
- **Interrogatorio:** tirar ocho preguntas en un turno.
- **Solo preguntar:** no proponer nada aunque ya haya material.
- **Brainstorm interminable:** alargar la conversación cuando ya está aterrizada.
- **Preguntar lo que ya está dicho** en la conversación o en el contexto del proyecto.
- **Modo equivocado:** tratar como `feature` una idea que todavía no pasó el "¿vale la pena?", o como decisión técnica lo que es de producto.
- **Documento genérico:** que le sirva a cualquier proyecto y no refleje este.
- **Documento relleno:** secciones con contenido inventado para cumplir el template.
- **Olvidar los supuestos,** o escribirlos sin decir cómo se validan.
- **Stack en el brief del agente:** rompe la separación entre qué y cómo.
