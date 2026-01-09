# Hydro Charger Landing Page - Brief Maestro

## 🎯 Objetivo del Proyecto

Crear una landing page minimalista y premium estilo **Normal Computing** para el Hydro Charger de SWI-TEC.

### Propósito
- **Pre-venta / Awareness**: Enamorar del producto antes de llevar a la tienda
- **Educación**: Explicar qué es un hidrogenerador y por qué es superior
- **Conversión**: Click hacia SWI-TEC.com para configurar y comprar

### Usuario objetivo
Navegantes y veleros que:
- Hacen travesías largas (coastal u offshore)
- Necesitan energía constante sin motor
- Buscan soluciones sostenibles y premium
- Valoran tecnología náutica de calidad

---

## 🎨 Referencias de Diseño

### Inspiración Principal: Normal Computing
**URL**: https://www.normalcomputing.com/

**Por qué este estilo funciona:**
- Minimalismo tech premium
- Espaciado generoso (mucho aire entre secciones)
- Tipografía grande y bold para headlines
- Animaciones sutiles (parallax, fade-in)
- Imágenes/videos como protagonistas
- Copy conciso y potente
- CTA discretos pero claros

### Elementos a adoptar:
- ✅ Hero full-screen con video de fondo
- ✅ Secciones con altura completa (100vh o más)
- ✅ Scroll narrativo (cada sección = 1 idea)
- ✅ Microinteracciones suaves
- ✅ Paleta oscura con acentos
- ✅ Footer minimalista

---

## 🎨 Sistema de Diseño

### Colores
```css
/* Base */
--bg-dark: #0a0a0a        /* Fondo principal oscuro */
--bg-section: #111111      /* Fondo secciones alternadas */
--text-primary: #ffffff    /* Texto principal */
--text-secondary: #a0a0a0  /* Texto secundario */

/* Acentos */
--accent-cyan: #00d9ff     /* Azul eléctrico/cyan (energía, agua, tech) */
--accent-blue: #0066ff     /* Azul tech secundario */
--accent-gray: #2a2a2a     /* Gray cards/borders */

/* Estados */
--success: #00ff88
--warning: #ffaa00
```

### Tipografía
```css
/* Familia */
font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;

/* Escalas */
--text-xs: 0.75rem    /* 12px - Pequeños labels */
--text-sm: 0.875rem   /* 14px - Body secundario */
--text-base: 1rem     /* 16px - Body principal */
--text-lg: 1.125rem   /* 18px - Destacados */
--text-xl: 1.25rem    /* 20px - Subtítulos */
--text-2xl: 1.5rem    /* 24px */
--text-3xl: 1.875rem  /* 30px */
--text-4xl: 2.25rem   /* 36px */
--text-5xl: 3rem      /* 48px - Headlines H2 */
--text-6xl: 3.75rem   /* 60px - Headlines H1 */
--text-7xl: 4.5rem    /* 72px - Hero principal */

/* Pesos */
--font-normal: 400
--font-medium: 500
--font-semibold: 600
--font-bold: 700
```

### Espaciado
```css
/* Sistema 8px base */
--space-1: 0.5rem   /* 8px */
--space-2: 1rem     /* 16px */
--space-3: 1.5rem   /* 24px */
--space-4: 2rem     /* 32px */
--space-6: 3rem     /* 48px */
--space-8: 4rem     /* 64px */
--space-12: 6rem    /* 96px */
--space-16: 8rem    /* 128px */
--space-24: 12rem   /* 192px */
```

### Animaciones
```css
/* Duraciones */
--duration-fast: 150ms
--duration-base: 300ms
--duration-slow: 500ms

/* Easings */
--ease-smooth: cubic-bezier(0.4, 0, 0.2, 1)
--ease-bounce: cubic-bezier(0.68, -0.55, 0.265, 1.55)
```

---

## 📐 Estructura de la Landing

### 1. Hero Section (100vh)
**Objetivo**: Impacto inmediato + comprensión del concepto

**Elementos**:
- Video de fondo: hidrogenerador en acción (loop, muted, autoplay)
- Overlay oscuro sutil para legibilidad
- Headline principal: "Energía infinita mientras navegas"
- Subheadline: "El hidrogenerador que transforma el agua en electricidad"
- CTA primario: [Descubre cómo funciona ↓] (scroll suave a siguiente sección)
- Indicador de scroll (animado)

**Assets necesarios**:
- Video hero: hidrogenerador bajando/operando (MP4 optimizado)
- Fallback: imagen estática si video no carga

---

### 2. Concepto / Educación (100vh)
**Objetivo**: Explicar QUÉ ES y CÓMO FUNCIONA

**Layout**: 50/50 (visual izq + texto der)

**Elementos visuales**:
- Animación o diagrama simple: Agua → Hélice → Electricidad → Batería
- O video corto mostrando el proceso

**Copy**:
- Headline: "Mientras tu velero corta el agua, generas energía"
- 3 specs destacadas (grande, visual):
  - 🌊 Desde 3 nudos
  - ⚡ Hasta 500W
  - 🌙 24 horas al día

**Assets**:
- Imagen/video del hidrogenerador instalado
- Diagrama de funcionamiento (puedes usar ilustración SVG)

---

### 3. Comparativa Visual (80vh)
**Objetivo**: Posicionar el producto como superior

**Layout**: 3 columnas centradas

**Tabla simplificada**:
```
                Solar    Motor Gasoil    Hydro Charger
Funciona navegando  ❌        ✅              ✅
De noche            ❌        ✅              ✅
Silencioso          ✅        ❌              ✅
Sin combustible     ✅        ❌              ✅
Hasta 500W          ❌        ✅              ✅
Mantenimiento       Bajo      Alto            Mínimo
```

**Highlight**: "El único que funciona las 24h mientras navegas"

---

### 4. Simulador Interactivo (100vh)
**Objetivo**: Engagement + proof of performance

**Elementos**:
- Slider grande de velocidad (3-10 nudos)
- Display de watts generados en tiempo real
- Visualización de batería cargándose
- Gráfica de rendimiento real (tu diagrama actual)

**Interacción**:
- Usuario mueve slider → números y gráfica se actualizan
- Animación suave de transición
- Tooltips explicativos

**Assets**:
- Tu gráfica de rendimiento real (PNG/SVG optimizado)

---

### 5. Instalaciones / Casos Reales (100vh)
**Objetivo**: Social proof + casos de uso

**Layout**: Grid 2x2 o carrusel de imágenes grandes

**Elementos**:
- 4-6 fotos épicas de instalaciones reales
- Overlay con datos:
  - Tipo de velero
  - Millas navegadas
  - Quote corto del dueño

**Ejemplos**:
```
[FOTO: Hidro en Oceanis 40]
"30,000 millas navegadas"
- Tommy, East London

[FOTO: Instalación en catamarán]
"Baterías siempre al 100%"
- Carlos, Mallorca
```

**Assets**:
- Mejores fotos de instalaciones (alta calidad)
- Testimonios de test.hydro-charger.com

---

### 6. Specs Técnicas (80vh)
**Objetivo**: Información para decisión de compra

**Layout**: Cards limpias con categorías

**Secciones**:
- Performance (50-500W, 3 nudos min, etc.)
- Construcción (Acero 316, peso 8kg)
- Control (App Android, Bluetooth)
- Compatibilidad (12V/24V, Litio*)

**Estilo**: Minimalista, solo datos clave, sin saturar

---

### 7. CTA Final (60vh)
**Objetivo**: Conversión a SWI-TEC

**Layout**: Centrado, simple, potente

**Copy**:
- Headline: "¿Listo para navegar sin límites?"
- Features rápidos (4 bullets máx):
  - Sistema completo desde €2,093
  - Instalación en 60 minutos
  - Garantía 24 meses
  - Envío desde España
- CTA primario: [Configurar mi sistema →] (link a SWI-TEC)
- CTA secundario: [Hablar con un experto] (WhatsApp)

---

### 8. Footer (Minimalista)
**Elementos**:
- Logo SWI-TEC
- Links: FAQ | Manual | Contacto | Legal
- Redes sociales (iconos discretos)
- Copyright

---

## 🛠️ Stack Técnico

### Framework
- **Astro 4.x** con TypeScript
- SSG (Static Site Generation)
- Islands Architecture para componentes interactivos

### Styling
- **Tailwind CSS 3.x**
- Custom design tokens en `tailwind.config.mjs`
- Plugins: typography, forms, aspect-ratio

### Interactividad
- **Vanilla JS** para animaciones simples
- **Alpine.js** o **Preact** para simulador (decidir según complejidad)
- **Intersection Observer** para scroll animations

### Assets
- Videos: MP4 optimizado (< 5MB), WebM backup
- Imágenes: WebP con fallback JPG
- SVGs para iconos y diagramas

### Performance
- Lazy loading de videos/imágenes
- Critical CSS inline
- Prefetch de links importantes
- Lighthouse score target: 95+

---

## 📦 Estructura de Archivos Propuesta

```
hydro-landing/
├── src/
│   ├── layouts/
│   │   └── Layout.astro           # Layout base
│   ├── components/
│   │   ├── Hero.astro             # Hero section
│   │   ├── ConceptSection.astro   # Explicación del concepto
│   │   ├── Comparison.astro       # Tabla comparativa
│   │   ├── Simulator.astro        # Simulador interactivo
│   │   ├── CaseStudies.astro      # Instalaciones reales
│   │   ├── TechSpecs.astro        # Especificaciones
│   │   ├── FinalCTA.astro         # CTA principal
│   │   └── Footer.astro           # Footer
│   ├── pages/
│   │   └── index.astro            # Homepage
│   ├── styles/
│   │   └── global.css             # Estilos globales
│   └── scripts/
│       └── animations.js          # Animaciones scroll
├── public/
│   ├── videos/
│   │   ├── hero.mp4
│   │   └── hero-poster.jpg
│   ├── images/
│   └── fonts/
├── tailwind.config.mjs
├── astro.config.mjs
└── package.json
```

---

## 🎬 Assets Temporales (URLs actuales)

### Videos
```
https://hydro-charger.com/wp-content/uploads/2019/12/hidrocharger.mp4
https://test.hydro-charger.com/videos/hero.mp4
https://test.hydro-charger.com/videos/7111-video.mp4
```

### Imágenes
```
# Instalaciones
https://hydro-charger.com/wp-content/uploads/2019/12/IMG_1984.jpg
https://hydro-charger.com/wp-content/uploads/2019/12/hydro-charguer-14_webshop-1.jpg
https://hydro-charger.com/wp-content/uploads/2019/12/hydro-charcher-7.jpg

# Diagrama
https://hydro-charger.com/wp-content/uploads/2019/12/Diagramm-10.14-Prestashop.jpg

# Monturas
https://test.hydro-charger.com/images/7111.png
https://test.hydro-charger.com/images/7110.png
https://test.hydro-charger.com/images/7109-a.png

# Logos
https://test.hydro-charger.com/images/logo.jpg
https://test.hydro-charger.com/images/logo-swi-tec.png
```

---

## ✅ Checklist de Implementación

### Fase 1: Setup (30 min)
- [ ] Inicializar proyecto Astro
- [ ] Configurar Tailwind + tokens custom
- [ ] Estructura de carpetas
- [ ] Layout base con header/footer

### Fase 2: Componentes Core (2-3h)
- [ ] Hero con video
- [ ] Sección concepto
- [ ] Comparativa
- [ ] Footer

### Fase 3: Componentes Interactivos (2h)
- [ ] Simulador (funcionalidad básica)
- [ ] Animaciones scroll
- [ ] Lazy loading

### Fase 4: Contenido y Ajustes (1-2h)
- [ ] Copy definitivo
- [ ] Optimización imágenes/videos
- [ ] Testing responsive
- [ ] Performance audit

### Fase 5: Deploy
- [ ] Build production
- [ ] Deploy a Vercel
- [ ] Pruebas finales

---

## 🚀 Próximos Pasos

1. **Revisar este brief** y confirmar dirección
2. **Preparar assets** (descargar videos/imágenes, optimizar)
3. **Crear proyecto** en Cursor con el prompt
4. **Iterar rápido** componente por componente
5. **Testing** en diferentes dispositivos

---

## 💡 Notas Importantes

- **Prioridad 1**: Diseño minimalista premium (como Normal)
- **Prioridad 2**: Performance y carga rápida
- **Prioridad 3**: Conversión a SWI-TEC
- **NO hacer**: Saturar con texto, features innecesarias, diseño recargado
- **SÍ hacer**: Espacios generosos, tipografía grande, menos es más

---

**Última actualización**: Enero 2025
**Versión**: 1.0
