# Brief — franciscodelgado.dev

Landing page personal de Francisco Delgado. Objetivo: portafolio simple y profesional
para acompañar el CV, orientado a roles de **Health IT** (sistemas de información
clínica, integración, análisis de negocios TI en salud). No es un sitio de marketing,
es una tarjeta de presentación técnica.

## 1. Quién es (para que el copy no suene genérico)

- Ingeniero en Tecnología de Software (UANL - FIME), con experiencia real en
  desarrollo .NET/C#/SQL Server en entornos empresariales (Panasonic Energy México,
  Fiscalía General de Justicia de NL).
- Formación técnica en Radiología + experiencia de piso en hospital (rayos X,
  apoyo en mamografía/ultrasonido). Esto es el diferenciador real: no es un
  desarrollador que "también sabe de salud", es alguien que trabajó en el flujo
  clínico y ahora construye software para ese mismo mundo.
- Interés declarado: sistemas de imagenología y flujos clínicos — visores DICOM
  web, integraciones tipo mini-PACS, flujos para equipo portátil de rayos X.
- Sin trabajos rimbombantes de marketing. El tono es de alguien que documenta bien
  y construye cosas que funcionan, no que vende humo.

## 2. Estructura del sitio (una sola página, sin scroll infinito de secciones vacías)

1. **Hero** — nombre, una línea de posicionamiento, y qué está buscando/construyendo.
   Nada de "Hola, soy Francisco 👋" ni frases de agencia. Directo.
2. **Sobre mí** — 2-3 párrafos cortos: desarrollador de software + formación
   clínica en radiología. Por qué le interesa Health IT específicamente.
3. **Proyectos** — tarjetas o lista, cada una con estado claro:
   - **Sistema de control de acceso vehicular RFID (FIME-UANL)** — proyecto real,
     completo en diseño y desarrollo de software (API .NET, gateway offline en
     SQLite, dashboard React, base de datos SQL Server con diagrama E-R).
     Estado honesto: **desarrollo de software terminado, despliegue físico e
     integración con hardware pendientes**. No lo infles a "sistema en producción".
     Esto es candidato a link a un repo (aunque sea privado con README público) o
     a un PDF/resumen de una página con el diagrama de arquitectura.
   - **Visor web DICOM** — estado: *en planeación / próximamente*. Una línea
     describiendo qué problema resolvería (ver imágenes DICOM desde navegador
     sin instalar visor propietario).
   - **Flujo mini-PACS** — estado: *en planeación*. Una línea: recepción y
     organización de estudios de un equipo portátil de rayos X.
   - Regla: si un proyecto no está construido, dilo con una etiqueta tipo
     "Concepto" o "En diseño" — no lo presentes como si ya existiera. Es más
     creíble un roadmap honesto que tres proyectos fantasma con screenshots
     inventados.
4. **Stack / lo que domina** — lista corta, sin iconos genéricos de "skill bars":
   C#, .NET, SQL Server, React/JS, y por separado: fundamentos de sistemas de
   información en salud (HIS, RIS, LIS, PACS, DICOM, HL7) — aclarando que es
   conocimiento de fundamentos, no de implementación en producción todavía.
5. **Contacto** — email, LinkedIn, y el CV en PDF para descargar. Nada de
   formulario de contacto (no lo va a monitorear).

No lleves esto a 6-7 secciones con "Testimonios" o "Por qué trabajar conmigo":
no aplica para un portafolio individual en etapa temprana.

## 3. Dirección de diseño

Nada de la estética genérica de landing "hecha por IA": sin fondo crema con acento
terracota, sin tarjetas idénticas con la misma sombra gris suave, sin eyebrows en
mayúsculas tipo "PROYECTOS —", sin flechitas "→" pegadas a cada link, sin números
01/02/03 si el contenido no es realmente una secuencia.

En vez de eso, ancla el diseño en el mundo real del sujeto: pantallas de equipo
médico/radiológico y paneles técnicos (como el dashboard que se ve en el informe
del proyecto RFID) — alto contraste, tipografía funcional, sensación de
"instrumento", no de "producto SaaS".

**Paleta** (base, 5 tonos):
- `#0B0F14` — casi negro azulado, fondo principal (como una pantalla de lectura
  de estudios, no negro puro)
- `#E8ECEF` — texto principal sobre fondo oscuro
- `#7FB3A8` — verde-azulado apagado (acento, recuerda fósforo de monitor médico
  antiguo sin caer en "matrix verde neón")
- `#B8860B` a ajustar / o un ámbar apagado como acento secundario para estados
  ("en planeación")
- `#1C232B` — superficie para tarjetas, ligeramente más clara que el fondo

**Tipografía**: una sola familia para todo, con una variante monoespaciada
para metadatos (fechas, stack, estado del proyecto) — el mono no es decoración,
es información (como una etiqueta de estado en una interfaz clínica).
Sugerencia: algo tipo IBM Plex Sans + IBM Plex Mono, o Inter + JetBrains Mono si
prefieres algo más neutro. Evita Inter a solas para todo — es el default de
cualquier generador.

**Layout**: alineado a la izquierda, no centrado. Ancho de línea corto
(<80 caracteres) en los párrafos. Un solo elemento con protagonismo visual (el
hero), el resto tranquilo y disciplinado. Sin animaciones de fade-in en cada
sección al hacer scroll — como mucho, una transición sutil en el hero al cargar.

**Regla de un solo acento llamativo**: el estado de cada proyecto ("Completo",
"En planeación") se muestra como una etiqueta de texto simple con color, no
como un badge con icono y sombra.

## 4. Qué NO hacer (checklist rápido antes de dar por terminado)

- [ ] Sin gradientes decorativos de fondo
- [ ] Sin el mismo border-radius y la misma sombra en todo
- [ ] Sin "Hola 👋" ni emojis en el copy
- [ ] Sin inventar screenshots de proyectos que no existen
- [ ] Sin exagerar el estado del proyecto RFID ("en producción", "desplegado")
- [ ] Responsive real en móvil, no solo desktop
- [ ] Foco de teclado visible en links y botones
- [ ] Contraste de texto suficiente sobre el fondo oscuro

## 5. Stack técnico recomendado (simple, gratis, fácil de mantener)

- **Framework**: Astro (genera HTML estático, cero backend, muy rápido de
  aprender, ideal para un sitio de una sola página que casi no cambia).
  Alternativa aún más simple si prefieres cero build tools: HTML + CSS +
  un poco de JS vanilla, sin framework.
- **Hosting gratis**: GitHub Pages (o Cloudflare Pages, igual de gratis y con
  mejor soporte de dominios personalizados). Ambos soportan dominio propio
  con HTTPS gratis.
- **Dominio**: apuntar `franciscodelgado.dev` con un registro CNAME (o los
  registros A/ALIAS que pida GitHub Pages) desde donde compraste el dominio.
- **Repo**: un solo repositorio público (o privado si prefieres, pero público
  ayuda porque también es evidencia de que sabes usar Git/GitHub, algo que
  ya mencionas en tu CV).
- **Sin CMS, sin base de datos, sin backend** — es una tarjeta de presentación,
  no una app.

### Pasos de despliegue (para cuando el sitio ya esté construido)

1. `npm create astro@latest` → elegir plantilla mínima/vacía.
2. Construir el sitio siguiendo las secciones y la dirección de diseño de
   arriba.
3. Subir a un repo de GitHub.
4. Activar GitHub Pages (Settings → Pages → Build from GitHub Actions, Astro
   trae su propia acción oficial) o conectar el repo a Cloudflare Pages.
5. Agregar archivo `CNAME` con `franciscodelgado.dev` (GitHub Pages) o
   configurar el dominio personalizado en el panel de Cloudflare Pages.
6. En el proveedor del dominio, agregar el registro DNS que indique la
   plataforma elegida.
7. Verificar HTTPS activo (ambas plataformas lo emiten automático, puede
   tardar unos minutos/horas).

## 6. Prompt listo para pegar en Claude Code

```
Construye una landing page de una sola página para franciscodelgado.dev usando
Astro, siguiendo exactamente el brief en BRIEF.md de este repo (estructura,
copy, paleta, tipografía y el checklist de "qué no hacer"). Es un portafolio
personal orientado a Health IT, no un sitio de marketing. Sigue las reglas de
diseño anti-genérico del brief al pie de la letra. Al terminar, deja el sitio
listo para desplegar en GitHub Pages con dominio personalizado (agrega el
archivo CNAME correspondiente).
```

Guarda este archivo como `BRIEF.md` en la raíz del repo antes de correr el
prompt — así Claude Code lo lee directo.
