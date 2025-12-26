# Quick Image Size Reference

Quick copy-paste guide for creating images in Figma.

## Hero Section

### Desktop
```
Dimensions: 1920 x 1080 px
Format: WebP
Quality: 80
File Size: 150-200 KB
Filename: hero-desktop.webp
Aspect Ratio: 16:9
```

### Mobile
```
Dimensions: 540 x 720 px
Format: WebP
Quality: 80
File Size: 40-60 KB
Filename: hero-mobile.webp
Aspect Ratio: 3:4
```

---

## Gallery Images (Recent Work)

Create **6 images** (minimum) at these sizes:

### Desktop
```
Dimensions: 400 x 300 px
Format: WebP
Quality: 80
File Size: 30-50 KB each
Filenames: project-1-desktop.webp ... project-6-desktop.webp
Aspect Ratio: 4:3
```

### Mobile
```
Dimensions: 280 x 210 px
Format: WebP
Quality: 80
File Size: 15-25 KB each
Filenames: project-1-mobile.webp ... project-6-mobile.webp
Aspect Ratio: 4:3
```

---

## Figma Artboards to Create

1. **HERO - DESKTOP** → 1920x1080
2. **HERO - MOBILE** → 540x720
3. **GALLERY 1-6 - DESKTOP** → 400x300 (×6)
4. **GALLERY 1-6 - MOBILE** → 280x210 (×6)

**Total: 14 artboards, 14 images to export**

---

## Export Settings

- Format: **WebP** (primary)
- Quality: **80**
- DPI: **72**
- Progressive: Yes (for JPG fallback)

---

## File Organization

```
assets/
└── images/
    ├── hero-desktop.webp
    ├── hero-mobile.webp
    ├── project-1-desktop.webp
    ├── project-1-mobile.webp
    ├── project-2-desktop.webp
    ├── project-2-mobile.webp
    ├── project-3-desktop.webp
    ├── project-3-mobile.webp
    ├── project-4-desktop.webp
    ├── project-4-mobile.webp
    ├── project-5-desktop.webp
    ├── project-5-mobile.webp
    ├── project-6-desktop.webp
    └── project-6-mobile.webp
```

---

## Config File Example

```json
{
  "hero": {
    "backgroundImage": "assets/images/hero-desktop.webp",
    "backgroundImageMobile": "assets/images/hero-mobile.webp"
  },
  "gallery": {
    "images": [
      {
        "src": "assets/images/project-1-desktop.webp",
        "srcMobile": "assets/images/project-1-mobile.webp",
        "alt": "Project 1"
      },
      {
        "src": "assets/images/project-2-desktop.webp",
        "srcMobile": "assets/images/project-2-mobile.webp",
        "alt": "Project 2"
      },
      // ... up to 6 total
    ]
  }
}
```

---

## One-Minute Checklist

Before uploading images:

- [ ] 1 hero desktop image (1920×1080)
- [ ] 1 hero mobile image (540×720)
- [ ] 6 gallery desktop images (400×300 each)
- [ ] 6 gallery mobile images (280×210 each)
- [ ] All images in WebP format
- [ ] All file sizes optimized (hero ~150-200KB, gallery ~30-50KB desktop, ~15-25KB mobile)
- [ ] Filenames match site-config.json
- [ ] Images placed in `assets/images/` folder
- [ ] Config file updated with image paths

---

**That's it!** Template handles the rest.
