# Figma Image Specifications & Workflow

A guide for creating optimized images in Figma for contractor websites and uploading them as part of the deployment process.

## Image Requirements Overview

The contractor template requires images at specific sizes for optimal performance across devices. This document specifies exact dimensions for Figma creation.

---

## 1. HERO SECTION IMAGE

### Purpose
Full-width background image at the top of the page. Sets the tone for the entire site.

### Figma Artboard Dimensions

#### Desktop Version
- **Width:** 1920px
- **Height:** 1080px
- **Aspect Ratio:** 16:9
- **Export Format:** WebP (primary), JPG (fallback)
- **File Size Goal:** 150-200KB
- **DPI:** 72

#### Mobile Version
- **Width:** 540px
- **Height:** 720px
- **Aspect Ratio:** 3:4 (portrait)
- **Export Format:** WebP (primary), JPG (fallback)
- **File Size Goal:** 40-60KB
- **DPI:** 72

### Figma Setup Instructions

1. Create two artboards: "Hero-Desktop" and "Hero-Mobile"
2. Set dimensions as above
3. Add your design/photo/composition
4. Export both versions:
   - `hero-desktop.webp` (1920x1080)
   - `hero-mobile.webp` (540x720)
5. Ensure text and important content is readable on both sizes

### Usage in Template
```json
"hero": {
  "backgroundImage": "assets/images/hero-desktop.webp"
  // Mobile version loaded via CSS media query
}
```

---

## 2. GALLERY / RECENT WORK IMAGES

### Purpose
Showcase past projects in a horizontal scrolling marquee. Users see 3-4 images at once on desktop.

### Figma Artboard Dimensions

#### Desktop Version (for web display)
- **Width:** 400px
- **Height:** 300px
- **Aspect Ratio:** 4:3
- **Export Format:** WebP (primary), JPG (fallback)
- **File Size Goal:** 30-50KB per image
- **DPI:** 72

#### Mobile Version
- **Width:** 280px
- **Height:** 210px
- **Aspect Ratio:** 4:3 (maintains same ratio)
- **Export Format:** WebP (primary), JPG (fallback)
- **File Size Goal:** 15-25KB per image
- **DPI:** 72

### Figma Setup Instructions

1. Create artboards for each project:
   - "Gallery-Desktop-1", "Gallery-Desktop-2", etc.
   - "Gallery-Mobile-1", "Gallery-Mobile-2", etc.

2. Set dimensions as above (400x300 for desktop, 280x210 for mobile)

3. Add project photos/designs

4. Export 6 total images minimum:
   - Desktop: `project-1-desktop.webp` through `project-6-desktop.webp` (400x300)
   - Mobile: `project-1-mobile.webp` through `project-6-mobile.webp` (280x210)

### Usage in Template
```json
"gallery": {
  "images": [
    {
      "src": "assets/images/project-1-desktop.webp",
      "alt": "Project 1",
      "srcMobile": "assets/images/project-1-mobile.webp"
    },
    {
      "src": "assets/images/project-2-desktop.webp",
      "alt": "Project 2",
      "srcMobile": "assets/images/project-2-mobile.webp"
    }
    // ... up to 6 images
  ]
}
```

---

## 3. COMPLETE FIGMA TEMPLATE SETUP

### Create a Master Figma File

Name it: **[Client Name] - Web Assets Template**

This file should contain:

```
[Client Name] - Web Assets Template
├── HERO - DESKTOP
│   └── 1920x1080px artboard
├── HERO - MOBILE
│   └── 540x720px artboard
├── GALLERY - DESKTOP
│   ├── Project 1 (400x300px)
│   ├── Project 2 (400x300px)
│   ├── Project 3 (400x300px)
│   ├── Project 4 (400x300px)
│   ├── Project 5 (400x300px)
│   └── Project 6 (400x300px)
└── GALLERY - MOBILE
    ├── Project 1 (280x210px)
    ├── Project 2 (280x210px)
    ├── Project 3 (280x210px)
    ├── Project 4 (280x210px)
    ├── Project 5 (280x210px)
    └── Project 6 (280x210px)
```

### Export Process from Figma

1. Select artboard
2. Click "Export" in the right panel
3. Set format to "WebP" with quality 80
4. Add filename (e.g., `hero-desktop.webp`)
5. Download
6. Store in `assets/images/` folder

**Optional:** Also export as JPG as fallback for older browsers
- JPG quality: 85
- Same filenames: `hero-desktop.jpg`

---

## 4. DEPLOYMENT WORKFLOW: ADDING IMAGES

### For Each New Client Site:

#### Step 1: Get Figma File from Client (or Create)
- Client provides Figma file with their images/designs
- Or you create one based on brand guidelines

#### Step 2: Create Images in Figma
- Use the template artboards (dimensions provided above)
- Design/place client photos into each artboard
- Ensure images are optimized and properly cropped

#### Step 3: Export from Figma
```
Files to export:
├── hero-desktop.webp (1920x1080)
├── hero-mobile.webp (540x720)
├── project-1-desktop.webp (400x300)
├── project-1-mobile.webp (280x210)
├── project-2-desktop.webp (400x300)
├── project-2-mobile.webp (280x210)
├── ... (up to 6 projects)
```

#### Step 4: Organize in Template
```
[client-site]/
└── assets/
    └── images/
        ├── hero-desktop.webp
        ├── hero-mobile.webp
        ├── project-1-desktop.webp
        ├── project-1-mobile.webp
        ├── project-2-desktop.webp
        ├── project-2-mobile.webp
        └── ... (all images)
```

#### Step 5: Update site-config.json
```json
{
  "hero": {
    "backgroundImage": "assets/images/hero-desktop.webp"
  },
  "gallery": {
    "images": [
      {
        "src": "assets/images/project-1-desktop.webp",
        "srcMobile": "assets/images/project-1-mobile.webp",
        "alt": "Project 1 Description"
      },
      {
        "src": "assets/images/project-2-desktop.webp",
        "srcMobile": "assets/images/project-2-mobile.webp",
        "alt": "Project 2 Description"
      },
      // ... up to 6 total
    ]
  }
}
```

#### Step 6: Deploy
- Push to GitHub
- Deploy to Vercel
- Images are served from `assets/images/`

---

## 5. DEVICE-SPECIFIC IMAGE LOADING

The template automatically loads the correct image size:

### Desktop (1024px and wider)
- Hero: `hero-desktop.webp` (1920x1080)
- Gallery: `project-*-desktop.webp` (400x300)

### Mobile (under 768px)
- Hero: `hero-mobile.webp` (540x720)
- Gallery: `project-*-mobile.webp` (280x210)

This is handled by CSS `srcset` or JavaScript image swapping in the template.

---

## 6. IMAGE OPTIMIZATION CHECKLIST

For optimal performance:

### Figma Export Settings
- [ ] Format: WebP (primary)
- [ ] Quality: 80 (for WebP)
- [ ] Dimensions: Exact sizes specified above
- [ ] DPI: 72px per inch

### File Sizes
- [ ] Hero Desktop: 150-200KB
- [ ] Hero Mobile: 40-60KB
- [ ] Gallery Desktop: 30-50KB each
- [ ] Gallery Mobile: 15-25KB each

### Before Upload
- [ ] All images are optimized with WebP
- [ ] Filenames match config.json references
- [ ] Images placed in `assets/images/` folder
- [ ] site-config.json updated with new paths

---

## 7. QUICK REFERENCE: EXACT DIMENSIONS

### Copy-Paste Dimensions for Figma

**Hero Images:**
- Desktop: 1920 x 1080
- Mobile: 540 x 720

**Gallery Images (all):**
- Desktop: 400 x 300
- Mobile: 280 x 210

---

## 8. WORKFLOW SUMMARY FOR NEW CLIENT

1. **Create Figma File** with artboards at specified dimensions
2. **Design/Place Images** into each artboard
3. **Export WebP files** from Figma
4. **Organize** into `assets/images/` folder
5. **Update** `site-config.json` with image paths
6. **Push to GitHub** and deploy to Vercel
7. **Done!** Site loads optimized images for each device

---

## 9. RESPONSIVE IMAGE IMPLEMENTATION

Once images are in place, the template handles responsive loading via:

### CSS Media Queries
```css
@media (max-width: 768px) {
  /* Loads mobile versions */
}
```

### Picture Element (Optional Enhancement)
```html
<picture>
  <source media="(max-width: 768px)" srcset="assets/images/hero-mobile.webp">
  <img src="assets/images/hero-desktop.webp" alt="Hero">
</picture>
```

---

## 10. FILE SIZE TARGETS & PERFORMANCE

### Why These Sizes?

**Hero Desktop (1920x1080, 150-200KB)**
- Large enough for desktop displays
- Compresses well with WebP
- Loads fast on desktop connections

**Hero Mobile (540x720, 40-60KB)**
- Perfect for mobile screens
- Much smaller file size
- Reduces data usage on mobile

**Gallery Desktop (400x300, 30-50KB)**
- Shows 3-4 images on desktop view
- Scrolls smoothly in marquee
- Good compression with WebP

**Gallery Mobile (280x210, 15-25KB)**
- Displays 1-2 images on mobile
- Minimal data transfer
- Fast rendering

### Lighthouse Performance Impact
Following these sizes will maintain:
- Performance Score: 90+
- First Contentful Paint: <1.5s
- Largest Contentful Paint: <2.5s

---

## Notes

- All dimensions are in **pixels**
- All exports should be **WebP format** (with JPG fallback if needed)
- Keep DPI at **72px** (standard for web)
- File size targets ensure fast loading on all connections
- The template automatically serves correct image size based on device

---

**Ready to create client assets in Figma and deploy!** 🎨
