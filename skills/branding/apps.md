# Branding: lo que aplica solo a apps

Complemento de [SKILL.md](SKILL.md). Se lee solo cuando el proyecto es una app; si no, nada de esto aplica.

## 1. Ícono de app (Paso 5)

El ícono se entrega en capas para Icon Composer (detalle en las Human Interface Guidelines de Apple, App icons: https://developer.apple.com/design/human-interface-guidelines/app-icons):
- El concepto en una frase.
- La composición en 2 a 4 grupos de profundidad.
- Cada capa como SVG de lienzo completo a 1024×1024: sin máscara, texto en contornos, rellenos planos y sin efectos (brillos, biseles, sombras, blur). Nombre con prefijo de orden (`1-fondo.svg`, `2-…`), de atrás hacia adelante.
- Los colores de relleno de cada capa para Default, Dark y Mono.
- Armado en Icon Composer como `AppIcon.icon`. La luz y el vidrio los pone el sistema.

Se prueba a 1024 px, 60 pt y 29 pt sobre fondos claros y oscuros.

## 2. Marca que vive en una app (Paso 6)

Cómo entra la marca a la interfaz lo dicen las Human Interface Guidelines de Apple (Branding: https://developer.apple.com/design/human-interface-guidelines/branding). Lo que más se olvida:
- El color de marca va en la capa de contenido (imágenes, gradientes, ilustraciones), no pintado en las barras.
- El logo aparece como mucho una vez en la app.
- Sin marca en el launch screen. El momento de marca va en la bienvenida del onboarding, si existe.
- SF Pro y New York tienen licencia solo para mockups de la app. Nunca en marketing, redes ni web: ahí la marca usa su propia fuente.

## 3. Pantallas clave (Paso 7)

Es una lista de referencia; van las pantallas que definen este producto:

1. Onboarding — solo si hace falta. Por defecto la app abre directo en la vista core con defaults sensatos. Nunca un carrusel de tres slides; los permisos se piden cuando se usa la función
2. Home / Dashboard — lo próximo real del usuario, no una grilla de stats ni un saludo con su nombre
3. Vista core — donde se gasta la audacia: la interacción firma del producto
4. Perfil / Settings (si aplica) — nativo y sin adornos
5. Paywall (si modelo de suscripción) — qué recibe por el precio, precio real, cierre visible, sin toggle de prueba gratis

Los mockups llevan datos realistas del dominio, nunca "Alex", "John Doe" ni "$12,450.00", y muestran al menos un estado vacío o de error.

**Chequeo anti-slop:** secciones 3–8 y 12–15, más la prueba de estados. Con 4 señales o más, se rehace antes de mostrar.
