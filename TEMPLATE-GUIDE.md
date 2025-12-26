# Contractor Template - Mass Production Guide

A professional, animated contractor landing page template ready for rapid client site creation.

## Template Overview

This is a **zero-configuration** starter template designed for quick duplication and deployment across multiple contractor clients.

### Built With
- Vanilla HTML, CSS, and JavaScript (no build process)
- Configuration-driven architecture (single `site-config.json` file)
- Responsive design (mobile, tablet, desktop)
- Smooth animations and transitions
- 7 logo options included

## Quick Start: Creating a New Client Site

### Option 1: Manual Duplication

```bash
# Copy the template
cp -r contractor-template [new-client-name]

# Navigate to the new site
cd [new-client-name]

# Edit the configuration
nano site-config.json
```

### Option 2: Using Git

```bash
# Clone or copy the template
cp -r contractor-template [new-client-name]
cd [new-client-name]

# Initialize git for the new client
git init
git add .
git commit -m "Initial commit: [Client Name] Contractors Template"
git remote add origin git@github.com:your-org/[client-name]-contractors.git
git push -u origin main
```

## Configuration Workflow

### 1. Business Information

Update these fields in `site-config.json`:

```json
{
  "business": {
    "name": "Your Company Name",
    "tagline": "Your company tagline",
    "phone": "(555) 123-4567",
    "email": "info@company.com",
    "address": "123 Main Street",
    "city": "Your City",
    "state": "ST",
    "zip": "12345"
  }
}
```

### 2. Logo Selection

Choose from 7 pre-designed logos with green branding:

```json
{
  "logo": {
    "type": "contractor",
    "alt": "Company Logo"
  },
  "logoOptions": {
    "contractor": "assets/Contractor-logo.svg",
    "painting": "assets/Painting-Logo.svg",
    "handyman": "assets/handyman-logo.svg",
    "house": "assets/house-logo.svg",
    "house-lux": "assets/house-lux-logo.svg",
    "landscape": "assets/landscape-logo.svg",
    "pro": "assets/pro-logo.svg"
  }
}
```

**Available Logo Types:**
- `contractor` - General contractor logo
- `painting` - Painting company logo
- `handyman` - Handyman services logo
- `house` - House/home services logo
- `house-lux` - Luxury home services logo
- `landscape` - Landscaping services logo
- `pro` - Professional services logo

Just change `"type": "contractor"` to any of the above options.

### 3. Color Customization

Current theme uses green accent colors. To change:

```json
{
  "theme": {
    "primaryColor": "#00ff00",    // Bright green
    "secondaryColor": "#00cc00",  // Medium green
    "accentColor": "#00aa00"      // Dark green
  }
}
```

Replace with your brand colors (hex values).

### 4. Services

Define what services the contractor offers:

```json
{
  "services": [
    {
      "title": "Service One",
      "description": "Professional service with expert craftsmanship and attention to detail.",
      "icon": "hammer"
    },
    {
      "title": "Service Two",
      "description": "Complete solutions tailored to your specific project requirements.",
      "icon": "wrench"
    }
  ]
}
```

**Available Icons:**
- `hammer` - 🔨
- `wrench` - 🔧
- `drill` - ⚙️
- `cog` - ⚙️
- `paint` - 🎨
- `shovel` - 🛠️
- `truck` - 🚚
- `bolt` - ⚡

### 5. Gallery Images

Add your project showcase images:

```json
{
  "gallery": {
    "headline": "Recent Work",
    "images": [
      {
        "src": "https://images.unsplash.com/photo-1552321554-5fefe8c9ef14?w=800&h=600&fit=crop&q=80",
        "alt": "Project 1"
      },
      {
        "src": "https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=800&h=600&fit=crop&q=80",
        "alt": "Project 2"
      }
    ]
  }
}
```

**Finding Unsplash Images:**
1. Visit [unsplash.com](https://unsplash.com)
2. Search relevant terms: "construction", "concrete", "painting", "home renovation"
3. Copy the image URL: `https://images.unsplash.com/photo-[ID]?w=800&h=600&fit=crop&q=80`

### 6. Client Reviews/Testimonials

Add customer testimonials:

```json
{
  "reviews": [
    {
      "quote": "Excellent work and professional service. Highly recommended!",
      "name": "John S.",
      "rating": 5
    },
    {
      "quote": "Amazing attention to detail. Best contractors we've hired!",
      "name": "Sarah M.",
      "rating": 5
    }
  ]
}
```

### 7. Process Steps

Explain your service process:

```json
{
  "process": [
    {
      "title": "Site evaluation & planning",
      "description": "We thoroughly assess your space and develop a detailed plan tailored to your needs."
    },
    {
      "title": "Proper preparation",
      "description": "Our team prepares everything to exact specifications."
    },
    {
      "title": "Expert execution",
      "description": "We execute using professional techniques and high-quality materials."
    },
    {
      "title": "Finishing & cleanup",
      "description": "Professional finishing touches and complete site cleanup."
    }
  ]
}
```

### 8. Service Area

Define your service territory:

```json
{
  "serviceArea": {
    "mapImage": "assets/service-area-map.svg",
    "headline": "We Service the Greater St. Louis and St. Charles Area",
    "highlightText": "Greater St. Louis and St. Charles Area",
    "description": "We proudly serve the greater region with professional contractor services...",
    "benefits": [
      {
        "title": "Local Expertise",
        "description": "Deep knowledge of local conditions and project requirements."
      },
      {
        "title": "Fast Response Times",
        "description": "Quick consultations and flexible project timelines."
      }
    ]
  }
}
```

### 9. SEO Settings

Optimize for search engines:

```json
{
  "seo": {
    "title": "Professional Contractors | Expert Services",
    "description": "Professional contractor services with quality workmanship and excellent customer service. Free estimates available.",
    "keywords": "contractors, professional services, quality work, free estimates"
  }
}
```

## File Structure

```
client-site/
├── index.html              # Main HTML (do not modify)
├── css/
│   └── styles.css          # Styles (do not modify unless customizing)
├── js/
│   └── main.js             # JavaScript (do not modify unless customizing)
├── site-config.json        # ⭐ EDIT THIS FILE ONLY
└── assets/
    ├── [logo].svg          # 7 logo options available
    └── service-area-map.svg # Customizable service area map
```

## Single File Modification

**99% of configuration happens in `site-config.json`.**

This is the only file you need to edit for most client sites. The HTML, CSS, and JavaScript are designed to be reusable across all clients.

## Deployment Workflow

### Step 1: Setup GitHub Repository

```bash
cd [client-site]
git init
git add .
git commit -m "Initial commit: [Client Name] Contractors"
git remote add origin git@github.com:your-org/[client-name]-contractors.git
git push -u origin main
```

### Step 2: Deploy to Vercel

1. Go to [vercel.com](https://vercel.com)
2. Click "New Project"
3. Select your GitHub repository
4. Click "Deploy"
5. Get your live URL immediately

**Alternative:** Deploy to Netlify, GitHub Pages, or any static host.

### Step 3: Domain Configuration

- Update DNS to point to Vercel deployment
- Or use Vercel custom domain feature

## Contact Form Integration

The template includes a contact form placeholder. To make it functional:

### Option 1: JotForm (Recommended)

1. Create form on [jotform.com](https://jotform.com)
2. Get the embed code
3. Replace the form section in `index.html`

### Option 2: Formspree

1. Go to [formspree.io](https://formspree.io)
2. Create new form
3. Update form action in HTML

### Option 3: Custom Backend

Update the form submission in `js/main.js`:

```javascript
function initForm() {
    const form = document.getElementById('contact-form');
    form.addEventListener('submit', async (e) => {
        e.preventDefault();
        // Add your API endpoint here
        await fetch('/api/contact', {
            method: 'POST',
            body: new FormData(form)
        });
    });
}
```

## Mass Production Checklist

Use this checklist when creating a new client site:

- [ ] Copy template directory
- [ ] Update business name, phone, email, address
- [ ] Select appropriate logo type
- [ ] Update brand colors (if needed)
- [ ] Add 4-6 services with descriptions
- [ ] Add 6 gallery images (Unsplash or client photos)
- [ ] Add 3-5 customer testimonials
- [ ] Update process steps
- [ ] Update service area map or headline
- [ ] Update SEO title, description, keywords
- [ ] Test locally (`python3 -m http.server 8000`)
- [ ] Initialize git and push to GitHub
- [ ] Deploy to Vercel
- [ ] Configure custom domain
- [ ] Integrate contact form
- [ ] Test all animations on mobile
- [ ] Launch!

## Performance Tips

The template is already optimized, but here are additional tips:

1. **Image Optimization**
   - Use Unsplash's `?w=` and `?q=` parameters to control size and quality
   - Example: `?w=800&h=600&fit=crop&q=80`

2. **Mobile Testing**
   - Test on actual devices
   - Check animations on slower connections

3. **Analytics**
   - Add Google Analytics tag to `index.html`
   - Monitor user behavior

4. **Forms**
   - Integrate contact form submission
   - Set up email notifications

## Customization Beyond Configuration

For changes beyond the config file, edit:

- **HTML Structure:** `index.html`
- **Styles/Colors:** `css/styles.css`
- **Behavior:** `js/main.js`

All JavaScript uses vanilla APIs (no frameworks), so changes are straightforward.

## Support Resources

- **Browser Support:** All modern browsers (Chrome, Firefox, Safari, Edge)
- **Issues:** Check browser console for errors
- **Mobile:** Test on actual devices

## License

Free to use for client projects.

---

**Ready to launch client sites at scale!** ✨

Each new client requires only:
1. Copy template
2. Update `site-config.json`
3. Push to GitHub
4. Deploy to Vercel
5. Configure domain

Total setup time per client: **15-20 minutes**
