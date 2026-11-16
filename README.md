# Skills de Daniel 🧠☕

Hola, soy Daniel ([@daniellr](https://instagram.com/daniellr)). Co-fundador de Sotos, hablo de ropa, de IA y de café, y últimamente estoy totalmente demente con Claude.

Este repo tiene las skills que uso para diseñar marcas con IA **sin que se note que las hizo una IA**. Las armé conversando con Claude, así que si yo pude, tú también puedes.

Funcionan con Claude Code, Claude.ai y cualquier agente compatible con [`skills`](https://github.com/vercel-labs/skills) (Cursor, Codex, OpenCode y varios más).

## Qué hay acá

| Skill | Para qué sirve | Cómo la activas |
|---|---|---|
| [`branding`](skills/branding/SKILL.md) | Un design sprint paso a paso para la identidad de tu proyecto: audiencia, brand guidelines, paleta, tipografía, logo y design system. Sirve para apps, ropa, skincare, comida, servicios, lo que sea. | "haz el branding de X", "hagamos un design sprint", "definamos la paleta" |
| [`anti-slop`](skills/anti-slop/SKILL.md) | El catálogo de todo lo que delata que algo lo hizo una IA (el morado de siempre, Inter en todos lados, el ✨, el copy con "potencia tu..."), y qué hacer en vez. | "revisa esto con anti-slop", o sola cuando estás diseñando o escribiendo copy |

Se usan juntas: `branding` le pasa cada paso a `anti-slop` antes de mostrártelo. Te recomiendo instalar las dos.

## Cómo instalarlas

Necesitas tener [Node.js](https://nodejs.org) instalado (versión 22 o más nueva). Abre la terminal y corre:

```bash
npx skills add daniellr/skills
```

El instalador te pregunta qué skills quieres y para qué agente. Elige las dos y listo.

### Si usas Claude Code

Para tenerlas en todos tus proyectos:

```bash
npx skills add daniellr/skills --all -g -a claude-code
```

Para tenerlas solo en el proyecto donde estás parado, saca el `-g`:

```bash
npx skills add daniellr/skills --all -a claude-code
```

### Si quieres solo una

```bash
npx skills add daniellr/skills --skill anti-slop
```

### Si quieres ver qué hay antes de instalar

```bash
npx skills add daniellr/skills --list
```

### Para actualizarlas

Cuando suba cambios, corres esto y quedas al día:

```bash
npx skills update
```

### Sin terminal (Claude.ai)

1. Descarga la carpeta completa de la skill que quieres (por ejemplo `skills/branding`) y comprímela en un `.zip`. Ojo: no basta con el `SKILL.md`, la carpeta trae otros archivos que la skill lee cuando los necesita.
2. En Claude.ai anda a **Settings → Capabilities → Skills** y sube el `.zip`.
3. Repite con `anti-slop`.

## Cómo se usa

Abres Claude y le cuentas tu proyecto como se lo contarías a un amigo, desordenado está bien:

> haz el branding de una marca de café de especialidad para gente que toma café en la casa y no quiere pagar $5.000 por un cortado

Claude va paso a paso y te pregunta antes de avanzar. No te tira todo de una.

## Preguntas, ideas, reclamos

Déjame un mensaje en [Instagram](https://instagram.com/daniellr) o abre un issue acá. Si te sirvió, cuéntame qué armaste 👀

Más cosas en mi [canal de YouTube](https://www.youtube.com/@daniellrtv) y en [sotos.app/p/daniel](https://sotos.app/p/daniel).

## Licencia

[MIT](LICENSE). Úsalas, cámbialas y compártelas como quieras, solo deja el aviso de copyright.
