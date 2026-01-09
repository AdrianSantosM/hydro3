# PROMPT PARA CURSOR - Hydro Charger Landing Page

## 🎯 Contexto del Proyecto

Voy a crear una landing page minimalista y premium para **Hydro Charger**, un hidrogenerador náutico de SWI-TEC. El objetivo es capturar el estilo de diseño de [Normal Computing](https://www.normalcomputing.com/) - minimalista, espacioso, con tipografía grande y animaciones sutiles.

**Objetivo de la landing**: Pre-venta y awareness. La página debe enamorar del producto y llevar al usuario a configurar su compra en swi-tec.com.

**Usuario objetivo**: Navegantes y veleros que hacen travesías y necesitan energía constante sin motor.

---

## 📚 Documentación Disponible

Tengo preparados 3 documentos maestros con toda la información:

1. **BRIEF.md** - Estrategia completa, diseño, colores, estructura de secciones
2. **CONTENT.md** - Todo el copy organizado por secciones (headlines, descripciones, testimonios, specs)
3. **COMPONENTS.md** - Especificaciones técnicas de cada componente Astro

**Lee los 3 documentos antes de empezar a codear** para entender la visión completa.

---

## 🛠️ Stack Técnico

- **Astro 4.x** (SSG, Islands Architecture)
- **Tailwind CSS 3.x** con design tokens custom
- **TypeScript**
- **Alpine.js** para el simulador interactivo (o Preact si prefieres)
- **Inter font** de Google Fonts

---

## 🎨 Estilo de Diseño (Crítico)

### Inspiración: Normal Computing
- Minimalismo extremo
- MUCHO espacio en blanco (o negro en este caso)
- Tipografía grande y bold para headlines (6xl, 7xl, 8xl)
- Animaciones sutiles (parallax, fade-in al scroll)
- Cada sección cuenta UNA idea
- Videos/imágenes como protagonistas
- CTA discretos pero claros

### Paleta de Colores
```
Fondo oscuro: #0a0a0a
Secciones alternas: #111111
Texto principal: #ffffff
Texto secundario: #a0a0a0
Acento cyan: #00d9ff (para energía, agua, tech)
Acento blue: #0066ff
```

### Tipografía
- Font: Inter
- Headlines H1: text-7xl o text-8xl (72px+)
- Headlines H2: text-5xl o text-6xl (48-60px)
- Body: text-base o text-lg
- Bold weights para headlines (font-bold, font-semibold)

### Espaciado
- Secciones: min-h-screen o min-h-[80vh]
- Padding generoso: py-24, px-4
- Gaps grandes entre elementos: gap-12, gap-16
- Márgenes amplios en copy: mb-12, mb-16

---

## 📐 Estructura de Secciones

La landing tiene **8 secciones principales**:

1. **Hero** (100vh) - Video de fondo + headline épico + CTA scroll
2. **Concepto** (100vh) - Explicación visual del producto (50/50 layout)
3. **Comparativa** (80vh) - Tabla mostrando superioridad vs solar/gasoil
4. **Simulador** (100vh) - Interactivo: slider velocidad → watts generados
5. **Casos Reales** (100vh) - Grid 2x2 de fotos con testimonios overlay
6. **Specs Técnicas** (80vh) - Cards organizadas por categorías
7. **CTA Final** (60vh) - Conversión hacia SWI-TEC
8. **Footer** - Minimalista con links y contacto

**Importante**: Cada sección debe respirar. No saturar. Menos es más.

---

## 🖼️ Assets Temporales

Usa estas URLs de las webs actuales mientras desarrollo:

### Videos
```
https://hydro-charger.com/wp-content/uploads/2019/12/hidrocharger.mp4
https://test.hydro-charger.com/videos/hero.mp4
https://test.hydro-charger.com/videos/7111-video.mp4
```

### Imágenes Clave
```
# Hero/Producto
https://hydro-charger.com/wp-content/uploads/2019/12/hydro-charguer-14_webshop-1.jpg

# Instalaciones
https://hydro-charger.com/wp-content/uploads/2019/12/IMG_1984.jpg
https://hydro-charger.com/wp-content/uploads/2019/12/hydro-charcher-7.jpg

# Diagrama rendimiento
https://hydro-charger.com/wp-content/uploads/2019/12/Diagramm-10.14-Prestashop.jpg

# Monturas
https://test.hydro-charger.com/images/7111.png
https://test.hydro-charger.com/images/7110.png
https://test.hydro-charger.com/images/7109-a.png

# Logos
https://test.hydro-charger.com/images/logo.jpg
https://test.hydro-charger.com/images/logo-swi-tec.png
```

**Nota**: Luego las descargaré y optimizaré, pero usa estas URLs para desarrollo rápido.

---

## 🎬 Orden de Desarrollo Sugerido

### Fase 1: Setup Base (15-20 min)
1. Crear proyecto Astro nuevo
2. Instalar Tailwind + configurar design tokens
3. Setup Layout.astro base
4. Agregar Inter font de Google Fonts

### Fase 2: Componentes Estáticos (1-2h)
1. Hero.astro (video + headline)
2. ConceptSection.astro (50/50 layout)
3. ComparisonTable.astro (tabla simple)
4. Footer.astro (minimalista)

### Fase 3: Componentes Avanzados (1-2h)
1. CaseStudies.astro (grid con overlays)
2. TechSpecs.astro (cards organizadas)
3. FinalCTA.astro (conversión)

### Fase 4: Interactividad (1h)
1. Simulator.astro (Alpine.js o Preact)
2. Scroll animations (Intersection Observer)
3. Smooth scroll entre secciones

### Fase 5: Polish (30min)
1. Responsive adjustments
2. Loading states para video
3. Performance check

---

## ✅ Requisitos Clave

### Performance
- [ ] Lazy load de videos e imágenes
- [ ] Critical CSS inline
- [ ] Lighthouse score 95+
- [ ] Videos optimizados < 5MB

### UX
- [ ] Smooth scroll entre secciones
- [ ] Animaciones sutiles (fade-in, slide-up)
- [ ] Responsive mobile-first
- [ ] Estados hover en CTAs

### SEO
- [ ] Meta tags completos
- [ ] OG tags para social
- [ ] Semántica HTML correcta
- [ ] Alt text en imágenes

---

## 🚨 Cosas a EVITAR

❌ **NO hacer**:
- Saturar con texto o features
- Usar más de 2-3 colores de acento
- Animaciones agresivas o rápidas
- Secciones apretadas sin espacio
- Diseño recargado o complejo
- Bullet points o listas largas en hero/concepto

✅ **SÍ hacer**:
- Espacios generosos entre secciones
- Tipografía grande y legible
- Jerarquía visual clara
- Copy conciso y directo
- Animaciones sutiles y elegantes
- Mobile-first responsive

---

## 💬 Cómo Ayudarme

### Al desarrollar cada componente:
1. **Lee el COMPONENTS.md** para ver la estructura exacta
2. **Usa el copy del CONTENT.md** (no inventes texto)
3. **Sigue los colores y espaciados del BRIEF.md**
4. **Pregúntame** si algo no está claro antes de asumir

### Formato de respuesta ideal:
```
[Componente que vas a crear]

[Breve explicación del approach]

[Código del componente]

[Notas técnicas si hay algo importante]
```

---

## 🎯 Primera Tarea

**Empecemos por el setup base**:

1. Crear estructura de proyecto Astro
2. Configurar Tailwind con los design tokens del BRIEF.md
3. Crear Layout.astro con:
   - HTML base
   - Meta tags
   - Google Fonts (Inter)
   - Estilos globales (smooth scroll, colores CSS vars)

**Muéstrame** el código de:
- `tailwind.config.mjs` (con tokens custom)
- `src/layouts/Layout.astro`
- `src/styles/global.css`
- `astro.config.mjs`

Una vez tengamos la base sólida, continuamos con Hero y demás componentes.

---

## 📝 Notas Finales

- **Prioridad absoluta**: Diseño minimalista premium (como Normal Computing)
- **Segunda prioridad**: Performance y carga rápida
- **Tercera prioridad**: Conversión hacia SWI-TEC

Recuerda: **Menos es más**. Si dudas entre agregar algo o no, probablemente es mejor no agregarlo.

¡Vamos a crear algo épico! 🚀

---

**Documentos maestros**: BRIEF.md, CONTENT.md, COMPONENTS.md
**Referencia de diseño**: https://www.normalcomputing.com/
**Producto**: Hydrogenerador náutico Hydro Charger SWI-TEC
