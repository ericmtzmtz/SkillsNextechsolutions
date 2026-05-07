# Skills Nexus

Colección de skills modulares para agentes de código. Principios prácticos, workflows optimizados y herramientas de desarrollo.

## Skills

### [smart-ui-design](./smart-ui-design.md)

Guía de diseño UI inteligente basada en principios prácticos de diseño visual. Cubre:

- **Jerarquía visual** — contraste, font weight, tamaño
- **Layout y espaciado** — sistema de escala base 16px, white space
- **Tipografía** — type scale, line-height, line-length, selección de fuentes
- **Color** — sistema HSL, 8-10 shades por color, grises con personalidad
- **Profundidad** — sombras, elevación, flat design
- **Imágenes** — manejo de fotos, texto sobre imágenes, contenedores
- **Toques finales** — accent borders, empty states, decoración

## Instalación

```bash
git clone https://github.com/ericmtzmtz/SkillsNextechsolutions.git
```

Copia el archivo `.md` del skill en el directorio de skills de tu agente.

## Estructura

```
SkillsNextechsolutions/
├── index.html           # Landing page del repositorio
├── README.md            # Documentación
└── smart-ui-design.md   # Skill: principios de diseño UI
```

## Uso

Cada skill es un archivo markdown con frontmatter que define nombre, descripción y triggers de activación. El agente carga el skill y aplica sus instrucciones cuando detecta una tarea relacionada.

## Licencia

GNU Affero General Public License v3.0 (AGPLv3)
