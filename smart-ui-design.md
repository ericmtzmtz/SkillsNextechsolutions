---
name: smart-ui-design
description: >
  Guía de diseño UI inteligente basada en principios prácticos de diseño visual.
  Usar cuando el usuario pida diseñar interfaces, crear componentes UI, revisar
  diseños existentes, elegir colores/tipografía/espaciado, construir sistemas de
  diseño, o cuando pregunte "cómo se ve bien esto", "qué fuente usar", "cómo
  organizo esto", "cómo mejorar mi UI". Activar también cuando se mencionen:
  jerarquía visual, paleta de colores, layout, white space, sombras, bordes,
  tipografía, accesibilidad visual, componentes, cards, botones, formularios,
  dashboards, landing pages, o cualquier tarea de diseño frontend.
---

# Smart UI Design — Principios Prácticos

Guía condensada de diseño UI profesional. Aplicar en orden: primero estructura/jerarquía, luego color/tipografía, finalmente detalles.

---

## 1. EMPEZAR DESDE CERO

### Empieza con una feature, no con el layout
- NO: nav bar → sidebar → logo → shell
- SÍ: diseña la primera funcionalidad real (ej. "buscar vuelo" = campos + botón)
- El shell (nav, sidebar) se decide DESPUÉS de tener 2-3 features reales

### Detalle viene después
- Fase 1: sketches en papel / wireframes grises sin color
- Fase 2: grayscale en herramienta — usa solo contraste, tamaño y espacio
- Fase 3: introduce color al final
- Razón: diseñar en gris fuerza jerarquía real; el color luego la refuerza

### No diseñes demasiado
- Diseña la versión MÁS SIMPLE que se puede construir y enviar
- Si algo es "nice-to-have", diseñarlo después — build primero lo mínimo viable
- Itera en ciclos cortos: diseño → build → problemas reales → rediseño

### Sistemas desde el principio
Define ANTES de empezar:
```
Font sizes:   12 / 14 / 16 / 18 / 20 / 24 / 30 / 36 / 48 / 60
Font weights: 400 (normal), 600-700 (énfasis)
Spacing:      4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 96 / 128 (base 16px × factores)
Border-radius: 2px (formal) | 4-6px (neutral) | 8-12px+ (playful)
Colors: 8-10 shades por hue; grises; 1-2 colores de acento
```
Nunca picks valores arbitrarios — elige del sistema.

---

## 2. JERARQUÍA VISUAL

**Regla central**: No todos los elementos son iguales. La jerarquía visual ES el diseño.

### Herramientas de jerarquía (en orden de preferencia)
1. **Color/contraste** — texto primario oscuro, secundario gris, terciario gris claro
2. **Font weight** — 600-700 para énfasis, 400 normal; NO usar < 400
3. **Tamaño** — última opción; no sobre-depender de tamaño

### Reglas clave
- **2-3 colores de texto máximo**: dark (titulares) / grey (fechas, subtítulos) / light-grey (copyright, placeholders)
- **2 font weights máximo** para UI work
- **Énfasis por de-énfasis**: si el elemento principal no destaca, baja los secundarios en lugar de subir el principal
- **Texto gris sobre fondos de color**: NO usar gris genérico — usar mismo hue del fondo con menos saturación/más luminosidad
- **Labels son último recurso**: si el formato ya comunica (`janedoe@example.com` = email), omite el label; combina `label + valor` en frase natural ("12 left in stock" > "In stock: 12")

### Jerarquía semántica ≠ jerarquía visual
- `h1` puede estilizarse pequeño si es label de sección
- El contenido de la sección importa más que su título
- Elige elementos HTML por semántica; estilízalos por jerarquía visual

### Botones y acciones
```
Primario:    fondo sólido, alto contraste → 1 por página max
Secundario:  outline o fondo bajo contraste
Terciario:   estilo link, discoverable pero discreto
Destructivo: NO siempre rojo/grande → si no es acción primaria, usar estilo secundario
             Mostrar versión roja/bold solo en el confirmation dialog
```

### Íconos y peso visual
- Íconos sólidos son "pesados" → bajar contraste (softer color) para balancear con texto
- Borders 1px muy sutiles → aumentar width en lugar de oscurecer

---

## 3. LAYOUT Y ESPACIADO

### Regla de white space
- **Empieza con DEMASIADO espacio**, quita hasta que quede bien
- NO: agregar margin mínimo hasta que "no se vea mal"
- SÍ: partir de espacio generoso y recortar
- "Un poco demasiado" en elemento individual = "justo suficiente" en UI completa

### No llenes toda la pantalla
- Si el contenido necesita 600px → usar 600px. No estirar a 1200px
- Cada elemento recibe el espacio que NECESITA, no el que el container tiene
- Tip: shrink canvas → diseñar mobile-first (~400px) fuerza decisiones reales

### Sistema de espaciado (escala con base 16px)
```
4px / 8px / 12px / 16px / 24px / 32px / 48px / 64px / 96px / 128px / 192px / 256px
```
- Diferencia entre valores adyacentes: ~25% mínimo
- Small end (padding botón, gap ícono): diferencias de 2-4px importan mucho
- Large end (ancho card, padding sección): diferencias de 20px son imperceptibles

### Grids
- Los grids son **sobre-valorados** para app UIs
- Útiles para: columnas de contenido, layouts editoriales
- No forzar todo a un grid — elementos tienen tamaños inherentes

### Espaciado relativo no escala
- No usar `em` para todo — elementos fuera de contexto se ven roto
- Preferir valores del sistema de espaciado sobre valores relativos

### Evitar espaciado ambiguo
- Espacio entre elementos relacionados DEBE ser menor que entre grupos distintos
- Grupo A | espacio pequeño | elemento de A | espacio grande | Grupo B

---

## 4. TIPOGRAFÍA

### Sistema de tipo (type scale)
Definir escala ANTES de diseñar:
```
xs: 12px  |  sm: 14px  |  base: 16px  |  lg: 18px  |  xl: 20px
2xl: 24px | 3xl: 30px  | 4xl: 36px   | 5xl: 48px  | 6xl: 60px
```

### Fuentes: selección por personalidad
```
Serif (ej. Georgia, Playfair)    → elegante, clásico, editorial
Rounded sans-serif (ej. Nunito) → playful, friendly, informal  
Neutral sans-serif (ej. Inter)   → limpio, profesional, deja que el contenido hable
```
Regla: 1-2 familias máximo. Si solo una, usar pesos/tamaños para variedad.

### Line length
- Óptimo: **45-75 caracteres** por línea (prose)
- UI compacto puede ser más corto
- Demasiado ancho = cansancio de lectura; demasiado estrecho = fragmentación

### Line-height
```
UI compacto / headings grandes:  line-height: 1 - 1.2
Texto normal / párrafos cortos:  line-height: 1.4 - 1.5
Prose largo:                     line-height: 1.6 - 1.8
Regla: a más ancho el texto, más line-height necesitas
```

### Alineación
- **Left-align por defecto** para bloques de texto
- Center solo para: títulos cortos, hero text, UI muy compacto
- Right: números en tablas (alinear decimales)
- NUNCA justify en UI web

### Letter-spacing
- Texto normal: 0 (no tocar)
- ALL CAPS / labels pequeños: +0.05em a +0.1em (mejora legibilidad)
- Headings grandes: ligeramente negativo (-0.01em a -0.02em)

### Links
- No TODOS los links necesitan color azul subrayado
- En contextos de navegación o UI, usar peso/color sutil
- Reservar color+underline para links inline en prose

### Baseline, not center
- Alinear texto con otros elementos: usar baseline alignment, no center vertical
- Excepción: íconos muy pequeños junto a texto corto

---

## 5. COLOR

### Usa HSL, no hex
```
HSL: hsl(220, 90%, 56%)
→ Hue (0-360): el color
→ Saturation (0-100%): intensidad  
→ Lightness (0-100%): claro/oscuro
```
Ventaja: ajustar solo L para shades, S para tono.

### Sistema de colores completo
Para cada color necesitas **8-10 shades**:
```
50  → casi blanco con tinte
100 → muy claro (backgrounds sutiles)
200 → claro
300 → medio-claro
400 → medio
500 → color base/referencia
600 → medio-oscuro (texto sobre blanco)
700 → oscuro
800 → muy oscuro
900 → casi negro con tinte
```

### Grises con personalidad
- Grises puros (`hsl(0,0%,X%)`) se ven apagados
- Agregar tinte de hue principal: `hsl(220, 10%, X%)` para UI azul/tech
- Warm greys: `hsl(30-40, 5-15%, X%)` para UIs con calidez

### Paleta completa mínima
```
Grises:       8-10 shades (base de todo el UI)
Primary:      8-10 shades (color de marca/accent)
Semantic:
  - Error:   rojo   8-10 shades
  - Warning: amarillo 8-10 shades  
  - Success: verde  8-10 shades
  - Info:    azul   8-10 shades
```

### Saturación y luminosidad
- **No dejar que la luminosidad mate la saturación**
- Shades claros necesitan MÁS saturación para mantener viveza
- Shades oscuros necesitan MENOS saturación
- Al crear shades: ajustar S y L juntos, no solo L

### Accesibilidad de contraste
```
Texto normal: ratio mínimo 4.5:1
Texto grande (18px+): ratio mínimo 3:1
UI elements: 3:1
```
- Accesible NO significa feo — se puede mantener la paleta y ajustar shades
- Usar shade 600-700 para texto sobre blanco
- Sobre fondos de color: no usar gris genérico — usar mismo hue, ajustar S/L

### No depender solo del color
- Agregar íconos, patrones, o texto para comunicar estado
- Error: color rojo + ícono + mensaje (no solo borde rojo)
- Gráficas: color + patrón o etiqueta directa

---

## 6. PROFUNDIDAD Y SOMBRAS

### Simula fuente de luz consistente
- Luz viene de ARRIBA en interfaces modernas
- Elementos elevados: sombra abajo/normal
- Elementos inset (inputs, wells): sombra hacia adentro arriba

### Sombras y elevación
```
Nivel 0: sin sombra (página base)
Nivel 1: sombra muy sutil   → cards, panels
Nivel 2: sombra media       → dropdowns, tooltips  
Nivel 3: sombra pronunciada → modales, drawers
Nivel 4: sombra grande      → dialogs críticos

Ejemplo:
  xs:  box-shadow: 0 1px 2px 0 rgba(0,0,0,0.05)
  sm:  box-shadow: 0 1px 3px 0 rgba(0,0,0,0.1), 0 1px 2px rgba(0,0,0,0.06)
  md:  box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px rgba(0,0,0,0.06)
  lg:  box-shadow: 0 10px 15px -3px rgba(0,0,0,0.1), 0 4px 6px rgba(0,0,0,0.05)
  xl:  box-shadow: 0 20px 25px -5px rgba(0,0,0,0.1), 0 10px 10px rgba(0,0,0,0.04)
```

### Sombras de dos partes
- Sombra 1: grande, difusa, baja opacidad (volumen)
- Sombra 2: pequeña, definida, más opacidad (contacto con superficie)
- Combinadas = más natural que una sola sombra

### Profundidad sin sombras (flat design)
- Color ligeramente más oscuro/claro en lugar de sombra
- Bordes sutiles para delimitar
- Overlap de elementos para crear capas
- Gradientes sutiles de top a bottom

---

## 7. IMÁGENES

### Fotos de calidad
- Una foto mala arruina cualquier diseño bien ejecutado
- Usar stock photography de calidad (Unsplash, etc.) en prototipos
- Consistencia: misma paleta/tono entre fotos del mismo UI

### Texto sobre imágenes
- Problema: texto sobre imagen = contraste impredecible
- Soluciones:
  1. Overlay oscuro semi-transparente sobre imagen
  2. Texto en área específica más oscura/clara de la foto  
  3. Background blur bajo el texto
  4. Colorize la imagen con color de marca
  5. Texto con `text-shadow` suave

### Tamaños intencionales
- Cada imagen tiene tamaño óptimo — no escalar sin límites
- Avatar 32px: no mostrar avatar de 1000px
- Definir contenedores con aspect-ratio fijos
- `object-fit: cover` para imágenes en contenedores fijos

### Contenido de usuarios
- Usuario puede subir imagen muy pequeña, muy grande, portrait, landscape
- Siempre usar contenedores con tamaño fijo + `object-fit: cover`
- Prever: ¿qué pasa si no sube imagen? → fallback con iniciales o ícono

---

## 8. TOQUES FINALES

### Supercharge defaults
- Bullets genéricos → reemplazar con íconos coloreados o checkmarks
- Links → botones con hover state
- Inputs → con iconos descriptivos o labels flotantes
- Select default → custom styled con mejor UX

### Bordes de acento (accent borders)
- Borde izquierdo de color en cards/alerts → añade personalidad sin ruido
- Top border en header o secciones
- Bottom border en tabs activos
- Más sutil que cambio de background completo

### Decorar backgrounds
- Gradiente sutil (mismo hue, 2 shades diferentes)
- Patrón geométrico muy sutil como texture
- Formas abstractas de color bajo (opacity 5-10%)
- SVG blob o wave en secciones hero

### Empty states
- NO dejar pantalla en blanco — diseñar el empty state
- Componentes: ícono illustrado + título + descripción + CTA primario
- Empty states son oportunidad de guiar al usuario

### Menos bordes
- Borde no es la única forma de separar elementos
- Alternativas: espacio en blanco, fondo levemente diferente, sombra sutil
- Muchos bordes = sensación de cuadrícula/tabla no intencional

### Think outside the box
- Bullet points → iconos coloreados o numeración con diseño
- Tablas → cards o list items más visuales
- Formularios largos → wizards por pasos
- Tooltips → inline explanatory text
- Modales → slide-overs o inline expansions

---

## RESUMEN: CHECKLIST DE REVISIÓN DE UI

Al revisar cualquier diseño, verificar:

```
JERARQUÍA
□ ¿Hay un elemento claramente más importante?
□ ¿Los secundarios están de-enfatizados?
□ ¿Labels innecesarios eliminados?
□ ¿Botones con jerarquía clara (primario/secundario/terciario)?

ESPACIADO
□ ¿Suficiente white space? (errar por exceso)
□ ¿Elementos relacionados más juntos que grupos distintos?
□ ¿Valores del sistema de espaciado usados?

TIPOGRAFÍA
□ ¿Type scale definido y respetado?
□ ¿Line-height apropiado para el contexto?
□ ¿Line-length entre 45-75 chars para prose?
□ ¿Max 2 font weights?

COLOR
□ ¿Sistema de shades definido?
□ ¿Contraste suficiente (4.5:1 texto normal)?
□ ¿Grises con personalidad (slight hue)?
□ ¿Color no es el único indicador de estado?

PROFUNDIDAD
□ ¿Sombras consistentes con nivel de elevación?
□ ¿Fuente de luz consistente?

DETALLES
□ ¿Empty states diseñados?
□ ¿Estados de error/vacío/carga considerados?
□ ¿Imágenes con contenedores definidos?
```

---

## PERSONALIDAD: TABLA DE REFERENCIA RÁPIDA

| Quiere | Font | Color | Border-radius | Sombras |
|--------|------|-------|---------------|---------|
| Elegante/lujoso | Serif | Gold, neutro | 2-4px | Sutiles |
| Profesional/confiable | Neutral sans | Azul, verde | 4-6px | Medias |
| Moderno/tech | Geometric sans | Azul eléctrico, morado | 6-8px | Medias |
| Playful/friendly | Rounded sans | Rosa, naranja, teal | 12px+ | Pronunciadas |
| Serio/formal | Serif o Neutral | Azul oscuro, negro | 0-2px | Mínimas |
| Cálido/humano | Humanist sans | Terracota, warm yellow | 8px | Sutiles |