# Hydro Charger Landing - Quick Reference

## 🎨 Design Tokens (Copy-Paste)

### Colors
```javascript
// tailwind.config.mjs
colors: {
  'dark': '#0a0a0a',
  'section': '#111111',
  'cyan': {
    400: '#22d3ee',
    500: '#00d9ff',
  },
  'blue': {
    500: '#0066ff',
  },
  'gray': {
    400: '#a0a0a0',
    700: '#2a2a2a',
    800: '#1a1a1a',
    900: '#0f0f0f',
  }
}
```

### Typography Scale
```
text-xs: 12px
text-sm: 14px
text-base: 16px
text-lg: 18px
text-xl: 20px
text-2xl: 24px
text-3xl: 30px
text-4xl: 36px
text-5xl: 48px   ← H2
text-6xl: 60px   ← H2 large
text-7xl: 72px   ← H1
text-8xl: 96px   ← H1 hero
```

---

## 📦 Project Structure

```
src/
├── layouts/
│   └── Layout.astro
├── components/
│   ├── Hero.astro
│   ├── ConceptSection.astro
│   ├── ComparisonTable.astro
│   ├── Simulator.astro
│   ├── CaseStudies.astro
│   ├── TechSpecs.astro
│   ├── FinalCTA.astro
│   └── Footer.astro
├── pages/
│   └── index.astro
├── styles/
│   └── global.css
└── scripts/
    └── animations.js
```

---

## 🔗 Asset URLs

### Videos
```html
<source src="https://hydro-charger.com/wp-content/uploads/2019/12/hidrocharger.mp4">
<source src="https://test.hydro-charger.com/videos/hero.mp4">
```

### Images
```html
<!-- Hero/Product -->
<img src="https://hydro-charger.com/wp-content/uploads/2019/12/hydro-charguer-14_webshop-1.jpg">

<!-- Installations -->
<img src="https://hydro-charger.com/wp-content/uploads/2019/12/IMG_1984.jpg">
<img src="https://hydro-charger.com/wp-content/uploads/2019/12/hydro-charcher-7.jpg">

<!-- Performance Chart -->
<img src="https://hydro-charger.com/wp-content/uploads/2019/12/Diagramm-10.14-Prestashop.jpg">
```

---

## 📝 Copy Snippets (Spanish)

### Hero
```
H1: Energía infinita mientras navegas
Subtitle: El hidrogenerador que transforma el movimiento del agua en electricidad
CTA: Descubre cómo funciona ↓
```

### Concepto
```
H2: Mientras tu velero corta el agua, tú generas energía
Body: El Hydro Charger SWI-TEC convierte el movimiento de tu velero en electricidad limpia y constante.

Features:
🌊 Desde 3 nudos | ⚡ Hasta 500W | 🌙 24 horas al día
```

### CTA Final
```
H2: ¿Listo para navegar sin límites?
CTA: Configurar mi sistema →
Link: https://swi-tec.com/product/universal-hydro-generator
```

---

## 🎬 Common Patterns

### Section Wrapper
```astro
<section class="min-h-screen flex items-center py-24 px-4 bg-[#111111]">
  <div class="max-w-7xl mx-auto">
    <!-- Content -->
  </div>
</section>
```

### Headline + Subtitle
```astro
<h2 class="text-5xl lg:text-6xl font-bold text-center mb-4">
  Headline aquí
</h2>
<p class="text-xl text-gray-400 text-center mb-16">
  Subtítulo aquí
</p>
```

### CTA Button Primary
```astro
<a 
  href="#"
  class="px-8 py-4 bg-cyan-500 hover:bg-cyan-400 text-black font-semibold rounded-lg transition-colors inline-flex items-center gap-2"
>
  Texto del botón
  <svg class="w-5 h-5"><!-- Arrow icon --></svg>
</a>
```

### CTA Button Secondary
```astro
<a 
  href="#"
  class="px-8 py-4 bg-gray-800 hover:bg-gray-700 font-semibold rounded-lg transition-colors"
>
  Texto secundario
</a>
```

---

## 🎨 Animations

### Fade In on Scroll
```astro
<!-- Add to element -->
<div data-animate class="opacity-0 transition-opacity duration-500">
  Content
</div>

<!-- Add script -->
<script>
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.remove('opacity-0');
        entry.target.classList.add('opacity-100');
      }
    });
  }, { threshold: 0.1 });
  
  document.querySelectorAll('[data-animate]').forEach(el => {
    observer.observe(el);
  });
</script>
```

---

## 📱 Responsive Breakpoints

```
Mobile: < 640px (base)
Tablet: md: 768px+
Desktop: lg: 1024px+
Large: xl: 1280px+
```

### Common Patterns
```astro
<!-- Stack mobile, side-by-side desktop -->
<div class="grid lg:grid-cols-2 gap-16">

<!-- Text sizes responsive -->
<h1 class="text-6xl md:text-7xl lg:text-8xl">

<!-- Padding responsive -->
<section class="py-12 md:py-16 lg:py-24">
```

---

## 🚀 Quick Start Commands

```bash
# Create project
npm create astro@latest hydro-landing

# Install dependencies
npm install -D tailwindcss @astrojs/tailwind

# Dev server
npm run dev

# Build
npm run build

# Preview
npm run preview
```

---

## ✅ Pre-Launch Checklist

- [ ] All images have alt text
- [ ] Videos have poster images
- [ ] Smooth scroll works
- [ ] Mobile responsive (< 640px)
- [ ] CTAs link to swi-tec.com
- [ ] Meta tags complete
- [ ] Lighthouse score > 90

---

## 🔥 Pro Tips

1. **Use max-w-7xl** for content containers
2. **Space sections** with min-h-screen or min-h-[80vh]
3. **Large headlines**: text-5xl minimum for H2
4. **Generous padding**: py-24, px-4 as default
5. **Subtle animations**: duration-500, ease-out
6. **Gray text**: text-gray-400 for secondary content
7. **Cyan accents**: Sparingly for highlights
8. **Clean hover states**: transition-colors on all interactive elements

---

**Docs**: BRIEF.md, CONTENT.md, COMPONENTS.md, PROMPT.md
**Reference**: https://www.normalcomputing.com/
