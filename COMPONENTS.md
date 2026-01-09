# Hydro Charger Landing - Especificaciones de Componentes

## 🏗️ Arquitectura General

```
Layout.astro (wrapper principal)
├── Header (fixed, transparent on hero)
├── Main
│   ├── Hero.astro
│   ├── ConceptSection.astro
│   ├── ComparisonTable.astro
│   ├── Simulator.astro
│   ├── CaseStudies.astro
│   ├── TechSpecs.astro
│   └── FinalCTA.astro
└── Footer.astro
```

---

## 1. Layout.astro (Base)

### Propósito
Wrapper principal que define estructura HTML, meta tags, fonts, y estilos globales.

### Props
```typescript
interface Props {
  title?: string;
  description?: string;
  ogImage?: string;
}
```

### Estructura
```astro
---
const { 
  title = "Hydro Charger - Energía infinita mientras navegas",
  description = "Hidrogenerador SWI-TEC para veleros. Genera hasta 500W desde 3 nudos. Baterías cargadas sin motor ni combustible.",
  ogImage = "/og-image.jpg"
} = Astro.props;
---

<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{title}</title>
  <meta name="description" content={description}>
  
  <!-- OG Tags -->
  <meta property="og:title" content={title}>
  <meta property="og:description" content={description}>
  <meta property="og:image" content={ogImage}>
  <meta property="og:type" content="website">
  
  <!-- Fonts: Inter -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
  
  <!-- Favicon -->
  <link rel="icon" type="image/svg+xml" href="/favicon.svg">
</head>
<body class="bg-dark text-white antialiased">
  <slot />
</body>
</html>
```

### Estilos Globales (global.css)
```css
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {
  :root {
    --bg-dark: #0a0a0a;
    --bg-section: #111111;
    --accent-cyan: #00d9ff;
    --accent-blue: #0066ff;
  }
  
  body {
    font-family: 'Inter', sans-serif;
    background-color: var(--bg-dark);
    color: white;
  }
  
  /* Smooth scroll */
  html {
    scroll-behavior: smooth;
  }
  
  /* Remove scrollbar pero mantener funcionalidad */
  ::-webkit-scrollbar {
    width: 0px;
    background: transparent;
  }
}

@layer utilities {
  .text-gradient {
    background: linear-gradient(135deg, var(--accent-cyan), var(--accent-blue));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }
}
```

---

## 2. Hero.astro

### Propósito
Primera impresión. Video de fondo + headline + CTA scroll.

### Estructura
```astro
---
// Sin props, todo hardcoded para máxima simplicidad
---

<section class="relative h-screen w-full overflow-hidden">
  <!-- Video Background -->
  <video 
    autoplay 
    muted 
    loop 
    playsinline
    class="absolute inset-0 w-full h-full object-cover"
    poster="/videos/hero-poster.jpg"
  >
    <source src="/videos/hero.mp4" type="video/mp4">
  </video>
  
  <!-- Overlay oscuro para legibilidad -->
  <div class="absolute inset-0 bg-black/40"></div>
  
  <!-- Content -->
  <div class="relative z-10 h-full flex flex-col items-center justify-center px-4 text-center">
    <h1 class="text-6xl md:text-7xl lg:text-8xl font-bold mb-6 max-w-5xl leading-tight">
      Energía infinita<br/>mientras navegas
    </h1>
    
    <p class="text-xl md:text-2xl text-gray-300 mb-12 max-w-3xl">
      El hidrogenerador que transforma el movimiento del agua en electricidad para tu velero
    </p>
    
    <a 
      href="#concepto" 
      class="inline-flex items-center gap-2 text-lg font-medium hover:text-cyan-400 transition-colors group"
    >
      Descubre cómo funciona
      <svg class="w-5 h-5 animate-bounce group-hover:translate-y-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"></path>
      </svg>
    </a>
  </div>
  
  <!-- Scroll indicator (animado) -->
  <div class="absolute bottom-8 left-1/2 -translate-x-1/2 z-10">
    <div class="w-6 h-10 border-2 border-white/30 rounded-full flex justify-center">
      <div class="w-1 h-3 bg-white rounded-full mt-2 animate-pulse"></div>
    </div>
  </div>
</section>

<style>
  /* Parallax effect en scroll */
  @media (prefers-reduced-motion: no-preference) {
    video {
      transform: translateZ(0);
      will-change: transform;
    }
  }
</style>
```

### Notas Técnicas
- Video: max 5MB, optimizado para web
- Fallback: poster image si video no carga
- Overlay 40% opacity para legibilidad
- Animaciones sutiles: bounce en flecha, pulse en scroll indicator

---

## 3. ConceptSection.astro

### Propósito
Explicar QUÉ ES un hidrogenerador y CÓMO FUNCIONA de forma visual.

### Layout
50/50 en desktop, stack en mobile

### Estructura
```astro
<section id="concepto" class="min-h-screen flex items-center py-24 px-4 bg-[#111111]">
  <div class="max-w-7xl mx-auto grid lg:grid-cols-2 gap-16 items-center">
    
    <!-- Visual izquierda -->
    <div class="relative">
      <img 
        src="https://hydro-charger.com/wp-content/uploads/2019/12/hydro-charguer-14_webshop-1.jpg"
        alt="Hydro Charger instalado"
        class="rounded-2xl shadow-2xl"
        loading="lazy"
      >
      <!-- Overlay con spec destacada opcional -->
      <div class="absolute -bottom-6 -right-6 bg-cyan-500 text-black p-6 rounded-xl shadow-xl">
        <div class="text-4xl font-bold">500W</div>
        <div class="text-sm font-medium">Potencia máxima</div>
      </div>
    </div>
    
    <!-- Contenido derecha -->
    <div>
      <h2 class="text-5xl lg:text-6xl font-bold mb-6 leading-tight">
        Mientras tu velero corta el agua, tú generas energía
      </h2>
      
      <p class="text-xl text-gray-400 mb-12 leading-relaxed">
        El Hydro Charger SWI-TEC convierte el movimiento de tu velero en electricidad 
        limpia y constante. Baja el generador al agua y empieza a cargar automáticamente.
      </p>
      
      <!-- 3 specs destacadas -->
      <div class="space-y-6">
        <div class="flex items-start gap-4">
          <div class="w-12 h-12 bg-cyan-500/10 rounded-lg flex items-center justify-center flex-shrink-0">
            <span class="text-2xl">🌊</span>
          </div>
          <div>
            <h3 class="text-xl font-semibold mb-1">Desde 3 nudos</h3>
            <p class="text-gray-400">Comienza a generar energía a partir de 3 nudos de velocidad</p>
          </div>
        </div>
        
        <div class="flex items-start gap-4">
          <div class="w-12 h-12 bg-cyan-500/10 rounded-lg flex items-center justify-center flex-shrink-0">
            <span class="text-2xl">⚡</span>
          </div>
          <div>
            <h3 class="text-xl font-semibold mb-1">Hasta 500W</h3>
            <p class="text-gray-400">Potencia suficiente para todos tus equipos a bordo</p>
          </div>
        </div>
        
        <div class="flex items-start gap-4">
          <div class="w-12 h-12 bg-cyan-500/10 rounded-lg flex items-center justify-center flex-shrink-0">
            <span class="text-2xl">🌙</span>
          </div>
          <div>
            <h3 class="text-xl font-semibold mb-1">24 horas al día</h3>
            <p class="text-gray-400">Funciona día y noche, siempre que navegues</p>
          </div>
        </div>
      </div>
    </div>
    
  </div>
</section>
```

### Variantes
- Opción A: Imagen estática
- Opción B: Video corto (15s) del proceso
- Opción C: Diagrama animado (SVG con CSS animations)

---

## 4. ComparisonTable.astro

### Propósito
Mostrar superioridad del producto vs alternativas de forma visual.

### Estructura
```astro
<section class="min-h-[80vh] flex items-center py-24 px-4">
  <div class="max-w-6xl mx-auto w-full">
    
    <h2 class="text-5xl font-bold text-center mb-4">
      Por qué Hydro Charger es superior
    </h2>
    <p class="text-xl text-gray-400 text-center mb-16">
      La única fuente de energía que funciona 24/7 mientras navegas
    </p>
    
    <!-- Tabla responsive -->
    <div class="overflow-x-auto">
      <table class="w-full border-collapse">
        <thead>
          <tr class="border-b border-gray-800">
            <th class="text-left py-4 px-6 font-semibold">Característica</th>
            <th class="text-center py-4 px-6 font-semibold text-gray-400">Solar</th>
            <th class="text-center py-4 px-6 font-semibold text-gray-400">Motor Gasoil</th>
            <th class="text-center py-4 px-6 font-semibold text-cyan-400">Hydro Charger</th>
          </tr>
        </thead>
        <tbody class="divide-y divide-gray-800">
          <tr class="hover:bg-gray-900/50 transition-colors">
            <td class="py-4 px-6">Funciona navegando</td>
            <td class="text-center py-4 px-6 text-2xl">❌</td>
            <td class="text-center py-4 px-6 text-2xl">✅</td>
            <td class="text-center py-4 px-6 text-2xl">✅</td>
          </tr>
          <!-- Repetir para cada row... -->
        </tbody>
      </table>
    </div>
    
    <!-- Highlight box -->
    <div class="mt-12 bg-gradient-to-r from-cyan-500/10 to-blue-500/10 border border-cyan-500/20 rounded-xl p-8 text-center">
      <p class="text-xl">
        💡 <strong>Combinación perfecta:</strong> Solar durante el día + Hidro mientras navegas = Baterías siempre al 100%
      </p>
    </div>
    
  </div>
</section>
```

### Mejoras Mobile
- Tabla scroll horizontal
- O convertir a cards comparativas (stack vertical)

---

## 5. Simulator.astro (Componente Interactivo)

### Propósito
Engagement + demostración de performance real.

### Tecnología
- Alpine.js (ligero) o Preact island
- Chart.js o D3.js para gráfica

### Estructura (con Alpine.js)
```astro
<section class="min-h-screen flex items-center py-24 px-4 bg-[#111111]">
  <div class="max-w-6xl mx-auto w-full">
    
    <h2 class="text-5xl font-bold text-center mb-4">
      Comprueba la potencia real
    </h2>
    <p class="text-xl text-gray-400 text-center mb-16">
      Ajusta la velocidad y ve cuánta energía generas
    </p>
    
    <div 
      x-data="simulator()"
      class="bg-gray-900/50 rounded-2xl p-8 lg:p-12 border border-gray-800"
    >
      
      <!-- Display principal -->
      <div class="text-center mb-12">
        <div class="text-8xl font-bold text-gradient mb-4" x-text="watts + 'W'"></div>
        <div class="text-2xl text-gray-400" x-text="status"></div>
      </div>
      
      <!-- Slider de velocidad -->
      <div class="mb-12">
        <label class="block text-center text-xl mb-4">
          Velocidad del barco: <span class="font-bold text-cyan-400" x-text="speed"></span> nudos
        </label>
        <input 
          type="range" 
          min="0" 
          max="10" 
          step="0.5"
          x-model.number="speed"
          class="w-full h-3 bg-gray-700 rounded-lg appearance-none cursor-pointer accent-cyan-500"
        >
        <div class="flex justify-between text-sm text-gray-500 mt-2">
          <span>0 kn</span>
          <span>5 kn</span>
          <span>10 kn</span>
        </div>
      </div>
      
      <!-- Gráfica de rendimiento -->
      <div class="bg-gray-800/50 rounded-xl p-6">
        <img 
          src="https://hydro-charger.com/wp-content/uploads/2019/12/Diagramm-10.14-Prestashop.jpg"
          alt="Gráfica de rendimiento real"
          class="w-full rounded-lg"
        >
        <p class="text-sm text-gray-400 mt-4 text-center">
          📊 Datos reales: Nevera (4A) + Piloto (6A) → +7.2% carga neta en 7.5h
        </p>
      </div>
      
    </div>
    
  </div>
</section>

<script>
  function simulator() {
    return {
      speed: 0,
      get watts() {
        if (this.speed < 3) return 0;
        if (this.speed < 4) return 50;
        if (this.speed < 5) return 100;
        if (this.speed < 6) return 200;
        if (this.speed < 7) return 300;
        if (this.speed < 8) return 400;
        return 500;
      },
      get status() {
        if (this.speed < 3) return 'Modo reposo - Mínimo 3 nudos';
        return 'Generando energía';
      }
    }
  }
</script>
```

### Mejoras Futuras
- Animación de batería llenándose
- Gráfica interactiva con Chart.js
- Simulación de consumos (nevera, electrónica, etc.)

---

## 6. CaseStudies.astro

### Propósito
Social proof con fotos reales y testimonios.

### Layout
Grid 2x2 con overlays

### Estructura
```astro
<section class="min-h-screen py-24 px-4">
  <div class="max-w-7xl mx-auto">
    
    <h2 class="text-5xl font-bold text-center mb-4">
      Probado en todo tipo de travesías
    </h2>
    <p class="text-xl text-gray-400 text-center mb-16">
      Miles de millas navegadas con Hydro Charger
    </p>
    
    <!-- Grid de casos -->
    <div class="grid md:grid-cols-2 gap-8">
      
      <!-- Card 1 -->
      <div class="group relative aspect-[4/3] rounded-2xl overflow-hidden cursor-pointer">
        <img 
          src="https://hydro-charger.com/wp-content/uploads/2019/12/IMG_1984.jpg"
          alt="Instalación en velero"
          class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500"
        >
        <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent flex flex-col justify-end p-8">
          <div class="text-sm text-cyan-400 font-semibold mb-2">30,000 millas navegadas</div>
          <blockquote class="text-lg mb-2">
            "Baterías siempre cargadas. Este viaje no habría sido posible sin él."
          </blockquote>
          <cite class="text-gray-400 not-italic">— Tommy, East London</cite>
        </div>
      </div>
      
      <!-- Repetir para 3-4 casos más -->
      
    </div>
    
    <!-- Stats -->
    <div class="grid grid-cols-2 lg:grid-cols-4 gap-8 mt-16 text-center">
      <div>
        <div class="text-4xl font-bold text-cyan-400 mb-2">95%</div>
        <div class="text-gray-400">Recomiendan Hydro Charger</div>
      </div>
      <!-- Más stats... -->
    </div>
    
  </div>
</section>
```

---

## 7. TechSpecs.astro

### Propósito
Specs técnicas organizadas y legibles.

### Layout
Cards con categorías

### Estructura
```astro
<section class="min-h-[80vh] py-24 px-4 bg-[#111111]">
  <div class="max-w-6xl mx-auto">
    
    <h2 class="text-5xl font-bold text-center mb-4">
      Ingeniería de precisión
    </h2>
    <p class="text-xl text-gray-400 text-center mb-16">
      Construcción marina premium
    </p>
    
    <!-- Grid de specs -->
    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
      
      <!-- Card Performance -->
      <div class="bg-gray-900/50 border border-gray-800 rounded-xl p-6">
        <h3 class="text-xl font-semibold mb-4 text-cyan-400">Performance</h3>
        <dl class="space-y-3">
          <div class="flex justify-between">
            <dt class="text-gray-400">Potencia</dt>
            <dd class="font-semibold">50-500W</dd>
          </div>
          <div class="flex justify-between">
            <dt class="text-gray-400">Vel. mínima</dt>
            <dd class="font-semibold">3 nudos</dd>
          </div>
          <!-- Más specs... -->
        </dl>
      </div>
      
      <!-- Card Construcción -->
      <div class="bg-gray-900/50 border border-gray-800 rounded-xl p-6">
        <h3 class="text-xl font-semibold mb-4 text-cyan-400">Construcción</h3>
        <!-- Similar estructura... -->
      </div>
      
      <!-- Más cards... -->
      
    </div>
    
  </div>
</section>
```

---

## 8. FinalCTA.astro

### Propósito
Conversión hacia SWI-TEC.

### Estructura
```astro
<section class="min-h-[60vh] flex items-center justify-center py-24 px-4">
  <div class="max-w-4xl mx-auto text-center">
    
    <h2 class="text-6xl font-bold mb-6">
      ¿Listo para navegar sin límites?
    </h2>
    
    <p class="text-xl text-gray-400 mb-12">
      Más de 20 años perfeccionando la tecnología de hidrogeneración marina
    </p>
    
    <!-- Features rápidos -->
    <div class="grid grid-cols-2 lg:grid-cols-4 gap-6 mb-12">
      <div>
        <div class="text-3xl font-bold text-cyan-400 mb-1">€2,093</div>
        <div class="text-sm text-gray-400">Desde</div>
      </div>
      <!-- Más features... -->
    </div>
    
    <!-- CTAs -->
    <div class="flex flex-col sm:flex-row gap-4 justify-center">
      <a 
        href="https://swi-tec.com/product/universal-hydro-generator"
        class="px-8 py-4 bg-cyan-500 hover:bg-cyan-400 text-black font-semibold rounded-lg transition-colors inline-flex items-center justify-center gap-2"
      >
        Configurar mi sistema
        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7l5 5m0 0l-5 5m5-5H6"></path>
        </svg>
      </a>
      
      <a 
        href="https://wa.me/34971822426"
        class="px-8 py-4 bg-gray-800 hover:bg-gray-700 font-semibold rounded-lg transition-colors"
      >
        Hablar con experto
      </a>
    </div>
    
    <!-- Trust badges -->
    <div class="flex flex-wrap justify-center gap-8 mt-12 text-sm text-gray-400">
      <div class="flex items-center gap-2">
        <span>🔒</span> Pago seguro SSL
      </div>
      <!-- Más badges... -->
    </div>
    
  </div>
</section>
```

---

## 9. Footer.astro

### Propósito
Navegación secundaria + legal + contacto.

### Estructura Minimalista
```astro
<footer class="border-t border-gray-800 py-12 px-4">
  <div class="max-w-7xl mx-auto">
    
    <div class="grid md:grid-cols-4 gap-8 mb-8">
      
      <!-- Logo + Tagline -->
      <div class="md:col-span-2">
        <img src="/logo.svg" alt="Hydro Charger" class="h-8 mb-4">
        <p class="text-gray-400 text-sm">
          Más de 20 años de innovación náutica
        </p>
      </div>
      
      <!-- Links -->
      <div>
        <h4 class="font-semibold mb-4">Producto</h4>
        <ul class="space-y-2 text-sm text-gray-400">
          <li><a href="#" class="hover:text-white transition-colors">Especificaciones</a></li>
          <!-- Más links... -->
        </ul>
      </div>
      
      <!-- Contacto -->
      <div>
        <h4 class="font-semibold mb-4">Contacto</h4>
        <ul class="space-y-2 text-sm text-gray-400">
          <li>Porto Cristo, Mallorca</li>
          <li>info@swi-tec.com</li>
        </ul>
      </div>
      
    </div>
    
    <!-- Bottom bar -->
    <div class="pt-8 border-t border-gray-800 flex flex-col md:flex-row justify-between items-center gap-4 text-sm text-gray-400">
      <p>© 2025 SWI-TEC. Todos los derechos reservados.</p>
      <div class="flex gap-6">
        <a href="#" class="hover:text-white transition-colors">Privacidad</a>
        <a href="#" class="hover:text-white transition-colors">Términos</a>
      </div>
    </div>
    
  </div>
</footer>
```

---

## 🎨 Animaciones y Efectos

### Scroll Animations
```javascript
// /src/scripts/animations.js

// Intersection Observer para fade-in
const observerOptions = {
  threshold: 0.1,
  rootMargin: '0px 0px -100px 0px'
};

const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('animate-in');
    }
  });
}, observerOptions);

document.querySelectorAll('[data-animate]').forEach(el => {
  observer.observe(el);
});
```

### Tailwind Custom Animations
```javascript
// tailwind.config.mjs

theme: {
  extend: {
    animation: {
      'fade-in': 'fadeIn 0.6s ease-out forwards',
      'slide-up': 'slideUp 0.6s ease-out forwards',
    },
    keyframes: {
      fadeIn: {
        '0%': { opacity: '0' },
        '100%': { opacity: '1' },
      },
      slideUp: {
        '0%': { opacity: '0', transform: 'translateY(30px)' },
        '100%': { opacity: '1', transform: 'translateY(0)' },
      },
    },
  },
}
```

---

## 📱 Responsive Breakpoints

```javascript
// Tailwind breakpoints
{
  'sm': '640px',   // Mobile landscape
  'md': '768px',   // Tablet
  'lg': '1024px',  // Desktop
  'xl': '1280px',  // Large desktop
  '2xl': '1536px', // XL desktop
}
```

### Mobile-First Strategy
- Base: mobile (< 640px)
- Adjustments: `md:` para tablet+
- Desktop enhancements: `lg:` y `xl:`

---

**Última actualización**: Enero 2025
**Framework**: Astro 4.x + Tailwind CSS 3.x
