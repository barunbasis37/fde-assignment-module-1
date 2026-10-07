# FDE Landing Pages

Three responsive, modern landing pages for Forward Deployed Engineering (FDE) services. Each design offers a unique visual identity while maintaining full accessibility and responsive behavior.

## Pages

### 1. **index-sonnet.html** — Professional & Enterprise
- **Color Scheme:** Navy (`#0F172A`), Blue accents (`#0369A1`)
- **Best For:** B2B SaaS, enterprise clients, professional services
- **Key Features:**
  - Hero section with embedded stats card
  - Service grid layout (3x2)
  - Sticky header with smooth navigation
  - Process timeline with step indicators
  - Trust bar with customer logos
  - FAQ section with details/summary elements

### 2. **index-opus.html** — Warm & Modern
- **Color Scheme:** Off-white (`#FAF8F5`), Orange accents (`#C2410C`)
- **Best For:** Modern SaaS startups, tech-forward companies
- **Key Features:**
  - Glassmorphism effects on header
  - Mock terminal deployment log in hero
  - Services displayed in a grid with hover effects
  - Dark section with 4-phase timeline
  - Comparison table vs. traditional hiring/agencies
  - Testimonial cards with featured quote
  - Transparent pricing with custom CTA form

### 3. **index-Haiku.html** — Minimalist & Clean
- **Color Scheme:** Purple (`#6D28D9`), White backgrounds
- **Best For:** Startups, tech companies, minimalist branding
- **Key Features:**
  - Hamburger mobile menu with smooth animations
  - Hero stats grid (3 KPIs)
  - Code-styled terminal output in hero
  - Service cards with hover transform
  - Dark timeline section for process steps
  - Collapsible FAQ with smooth transitions
  - Simple, focused pricing cards

## Features

✅ **Fully Responsive**
- Mobile (375px), Tablet (768px), Desktop (1440px+)
- Hamburger menu on mobile devices
- Touch-friendly buttons (44px minimum)

✅ **Dark Mode Support**
- Automatic detection via `prefers-color-scheme`
- Carefully tuned color palettes for readability
- Smooth transitions between modes

✅ **Accessibility**
- WCAG AA contrast ratios (4.5:1 minimum)
- Semantic HTML structure
- Keyboard navigation support
- Focus indicators on all interactive elements
- Aria labels and skip links

✅ **Performance**
- Single-file deployment (no external JS)
- CSS variables for theming
- Optimized animations respecting `prefers-reduced-motion`
- No external dependencies (fonts via Google Fonts API)

✅ **Browser Support**
- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Mobile)

## Quick Start

### View Locally
```bash
# Start a simple HTTP server in the project directory
python -m http.server 8000

# Then open in your browser:
# http://localhost:8000/index-sonnet.html
# http://localhost:8000/index-opus.html
# http://localhost:8000/index-Haiku.html
```

### Deploy
Each HTML file is self-contained and can be deployed directly to any static hosting:
- GitHub Pages
- Netlify
- Vercel
- AWS S3
- Any web server

## Customization

All color schemes use CSS variables defined at the `:root` level:

```css
:root {
  --color-primary: #YOUR_COLOR;
  --color-accent: #YOUR_ACCENT;
  /* etc. */
}

@media (prefers-color-scheme: dark) {
  :root {
    --color-primary: #DARK_COLOR;
    /* dark mode overrides */
  }
}
```

Edit these variables to match your brand colors. Typography can also be customized via the `--font-*` variables.

## Project Structure

```
fde-assignment-module-1/
├── index-sonnet.html              # Professional design
├── index-opus.html                # Warm modern design
├── index-Haiku.html               # Minimalist design
├── README.md                      # This file
├── CONTRIBUTING.md                # Contribution guidelines
├── CODE_OF_CONDUCT.md             # Community standards
└── .github/
    └── pull_request_template.md   # PR template for contributions
```

## Development

### Testing Checklist
Before deploying, verify:
- [ ] Mobile (375px) renders without horizontal scroll
- [ ] Tablet (768px) layout is balanced
- [ ] Desktop (1440px) utilizes space well
- [ ] Dark mode colors have sufficient contrast
- [ ] All links are clickable (44px+ touch targets)
- [ ] Keyboard Tab navigation works
- [ ] Focus indicators are visible
- [ ] No console errors

### Browser DevTools Testing
1. **Responsive Design Mode**
   - Test at multiple breakpoints
   - Check portrait/landscape modes
   
2. **Dark Mode**
   - Enable in DevTools (Appearance section)
   - Verify color readability
   
3. **Accessibility Inspector**
   - Check contrast ratios
   - Verify heading hierarchy
   - Confirm alt text presence

4. **Performance**
   - Check Lighthouse score
   - Verify no layout shifts (CLS)
   - Monitor Core Web Vitals

## Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on:
- Setting up your development environment
- Coding standards
- Testing requirements
- Pull request process

## Code of Conduct

This project adheres to the Contributor Covenant. See [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for details.

## License

This project is part of the FDE Assignment for Module 1. All rights reserved.

## Attribution

- **Author:** Barun Basis
- **Email:** barun.kanti.ca@gmail.com
- **Built with:** HTML5, CSS3
- **Fonts:** Google Fonts (Outfit, Space Grotesk, Plus Jakarta Sans, Inter, IBM Plex Mono)

---

**Questions?** Open an issue or check the [FAQ](CONTRIBUTING.md#faqs) section.

🚀 Ready to deploy your FDE landing page!
