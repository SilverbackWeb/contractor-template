# Contractor Templates Repository

A collection of high-performance, configuration-driven contractor landing page templates designed for rapid deployment and mass production.

## Available Templates

### 🏗️ Contractor Template

A professional contractor landing page with dark theme, animated elements, and multiple logo options.

**Features:**
- Dark theme with green accent colors
- Marquee animations (gallery and reviews scroll opposite directions)
- Installation process section with animated steps
- Service area section with customizable map
- 7 logo options (contractor, painting, handyman, house, house-lux, landscape, pro)
- Fully responsive design
- Configuration-driven (single JSON file)
- SEO optimized

**Setup Time:** 15-20 minutes per client

**Directory:** `contractor-template/`

## Getting Started

### 1. Choose a Template

All templates follow the same structure and workflow.

### 2. Copy for New Client

```bash
cp -r contractor-template [client-name]-site
cd [client-name]-site
```

### 3. Configure

Edit `site-config.json`:
- Business information
- Logo type
- Services
- Colors (if needed)
- Images
- Testimonials
- Process steps

### 4. Deploy

```bash
git init
git add .
git commit -m "Initial: [Client Name]"
git remote add origin git@github.com:your-org/[client-name]-site.git
git push -u origin main
```

Then connect to Vercel for automatic deployment.

## Template Architecture

Each template includes:

```
[template-name]/
├── index.html              # HTML structure (shared across all clients)
├── css/
│   └── styles.css          # Responsive styles (shared)
├── js/
│   └── main.js             # Config loader & interactions (shared)
├── site-config.json        # ⭐ Client-specific configuration
├── assets/
│   ├── [logos].svg         # Pre-designed logos
│   └── service-area-map.svg # Customizable map
└── README.md               # Template documentation
```

### Key Principle: Configuration-Driven

**99% of changes are made in `site-config.json`** - no code editing required for typical client sites.

## Configuration Guide

### Minimal Setup

At minimum, edit these fields in `site-config.json`:

```json
{
  "business": {
    "name": "Client Company Name",
    "phone": "(555) 123-4567",
    "email": "info@company.com",
    "address": "123 Main Street",
    "city": "City Name",
    "state": "ST",
    "zip": "12345"
  },
  "logo": {
    "type": "contractor"  // or: painting, handyman, house, house-lux, landscape, pro
  },
  "theme": {
    "primaryColor": "#00ff00",
    "secondaryColor": "#00cc00",
    "accentColor": "#00aa00"
  }
}
```

### Full Configuration

See `TEMPLATE-GUIDE.md` for complete configuration options including:
- Services
- Gallery images
- Testimonials
- Process steps
- Service area
- SEO metadata

## Logos Included

All 7 logos are pre-designed with green branding:

1. **Contractor** - General contractor logo
2. **Painting** - Painting services logo
3. **Handyman** - Handyman services logo
4. **House** - Home services logo
5. **House Lux** - Luxury home services logo
6. **Landscape** - Landscaping services logo
7. **Pro** - Professional services logo

Change logo by updating `logo.type` in config:

```json
"logo": {
  "type": "painting"  // Switches to Painting-Logo.svg
}
```

## Color Customization

Default theme uses green:
- Primary: `#00ff00` (bright green)
- Secondary: `#00cc00` (medium green)
- Accent: `#00aa00` (dark green)

Override in `site-config.json`:

```json
"theme": {
  "primaryColor": "#2563eb",      // Blue example
  "secondaryColor": "#1e40af",
  "accentColor": "#1e3a8a"
}
```

## Image Management

Templates use Unsplash for quick setup. Configure in `site-config.json`:

### Hero Image
```json
"hero": {
  "backgroundImage": "https://images.unsplash.com/photo-XXXXX?w=1920&h=1080&fit=crop&q=80"
}
```

### Gallery Images
```json
"gallery": {
  "images": [
    {
      "src": "https://images.unsplash.com/photo-XXXXX?w=800&h=600&fit=crop&q=80",
      "alt": "Project description"
    }
  ]
}
```

### Finding Images

1. Visit [unsplash.com](https://unsplash.com)
2. Search relevant terms (e.g., "construction", "painting", "home")
3. Format URL: `https://images.unsplash.com/photo-[ID]?w=800&h=600&fit=crop&q=80`

## Deployment

### Option 1: Vercel (Recommended)

1. Push code to GitHub
2. Connect repo to Vercel
3. Auto-deploys on push
4. Custom domains supported

### Option 2: Netlify

1. Push code to GitHub
2. Connect repo to Netlify
3. Auto-deploys on push

### Option 3: GitHub Pages

Free hosting directly from GitHub:

```bash
git push origin main
```

## Local Development

Test locally before deployment:

```bash
python3 -m http.server 8000
```

Visit `http://localhost:8000` and refresh after any changes to `site-config.json`.

## Mass Production Workflow

**Time per client site: 15-20 minutes**

1. Copy template
2. Update `site-config.json`
3. Test locally
4. Push to GitHub
5. Deploy to Vercel
6. Configure domain
7. Set up contact form
8. Launch

## Contact Form Integration

The template includes a form. Make it functional by:

### Option A: JotForm

1. Create form at [jotform.com](https://jotform.com)
2. Get embed code
3. Replace form in `index.html`

### Option B: Formspree

1. Register at [formspree.io](https://formspree.io)
2. Update form action in HTML

### Option C: Custom Endpoint

Update `js/main.js` form submission handler.

## Browser Support

All modern browsers:
- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)

## Performance

- **Vanilla JavaScript** - No dependencies or build process
- **CSS Animations** - Hardware-accelerated
- **Optimized Images** - Unsplash serves optimized images
- **Mobile Optimized** - Fully responsive design

Lighthouse score: 90+ (Performance, Accessibility, Best Practices, SEO)

## Customization

### Light Configuration (Recommended)
Edit only `site-config.json` - works for 95% of client sites.

### Heavy Customization
Edit HTML, CSS, or JavaScript as needed:
- `index.html` - Structure
- `css/styles.css` - Appearance
- `js/main.js` - Behavior

## Support

- **Documentation:** See individual template README.md
- **Guide:** See TEMPLATE-GUIDE.md for detailed workflow
- **Issues:** Check browser console for errors

## License

Free to use for client projects.

---

**Ready for mass production!** 🚀

Clone, configure, and deploy professional contractor sites in under 20 minutes.
