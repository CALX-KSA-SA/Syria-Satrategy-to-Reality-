# سلس (SELIS) - Advanced Website

## 🇸🇾 المنصّة الوطنية السورية

A highly advanced, modern website showcasing the Selis platform - transforming strategies into tangible reality in Syria.

---

## 🎨 Features

### Visual Design
- **Modern Arabic Typography**: Using Cairo and Tajawal fonts for beautiful Arabic text
- **Gradient Animations**: Smooth transitions and eye-catching color schemes
- **Interactive Particles**: Dynamic background effects in the hero section
- **3D Card Effects**: Tilt and hover animations on feature cards
- **Scroll Animations**: Elements fade in as you scroll through the page
- **Progress Indicator**: Visual scroll progress at the top of the page
- **Custom Cursor**: Enhanced cursor effects on desktop

### Sections
1. **Hero Section**: Large title with animated stats and particles
2. **Vision Section**: Challenge and solution cards
3. **Journey Section**: Visual 4-step process (Strategy → Initiative → Program → Project)
4. **Features Section**: 5 detailed capabilities with visual elements
5. **Impact Section**: 5 key benefits with gradient background
6. **Statement Section**: Official message for Syrian officials
7. **Footer**: Branding and copyright information

### Interactions
- Smooth scroll navigation
- Animated counters (60%, 100%, 360°)
- Interactive journey steps with ripple effects
- Feature cards with 3D tilt and sparkle effects
- Impact items with glow effects
- Responsive design for all devices

---

## 📁 File Structure

```
SELIS/
├── index.html          # Main HTML structure
├── styles.css          # Advanced CSS with animations
├── script.js           # Interactive JavaScript features
├── assets/
│   └── images/         # Images extracted from PDFs (add here)
└── README.md           # This file
```

---

## 🖼️ Adding Images from PDFs

You have several PDF files in the workspace. To extract and add images to the website:

### Method 1: Manual Extraction
1. Open any PDF file (e.g., `Selis.pdf`, `Selis_Presentation_share.pdf`)
2. Export images from the PDF:
   - **Mac**: Open in Preview → File → Export → Select images
   - **Adobe Acrobat**: Tools → Export PDF → Image → Select format
3. Save extracted images to `assets/images/` folder
4. Recommended image names:
   - `selis-logo.png` - Main logo
   - `strategy-icon.png` - Strategy visualization
   - `dashboard-screenshot.png` - Platform dashboard
   - `team-photo.jpg` - Team or office photo
   - `impact-graph.png` - Impact statistics
   - `syria-map.png` - Syrian projects map

### Method 2: Using Command Line (Mac)
```bash
# Install pdfimages if not installed
brew install poppler

# Extract images from PDF
pdfimages -png "Selis.pdf" assets/images/selis
```

### Method 3: Using Python
```python
import fitz  # PyMuPDF
doc = fitz.open("Selis.pdf")
for page_num in range(len(doc)):
    page = doc[page_num]
    images = page.get_images()
    for img_index, img in enumerate(images):
        xref = img[0]
        base_image = doc.extract_image(xref)
        image_bytes = base_image["image"]
        with open(f"assets/images/page{page_num}_img{img_index}.png", "wb") as f:
            f.write(image_bytes)
```

---

## 🔧 Integrating Images into the Website

Once you have images in `assets/images/`, update the HTML:

### 1. Add Logo
```html
<!-- Replace the text logo in navbar -->
<div class="logo">
    <img src="assets/images/selis-logo.png" alt="سلس" class="logo-image">
</div>
```

### 2. Add Hero Background Image
```html
<!-- In hero-background div -->
<div class="hero-background">
    <img src="assets/images/hero-bg.jpg" alt="Background" class="hero-bg-image">
    <div class="gradient-overlay"></div>
</div>
```

### 3. Add Feature Visuals
```html
<!-- Replace dashboard-preview divs -->
<div class="feature-visual">
    <img src="assets/images/dashboard-screenshot.png" alt="Dashboard" class="feature-image">
</div>
```

### 4. Add Section Background Images
```css
/* In styles.css */
.journey-section {
    background: url('assets/images/pattern-bg.png'), linear-gradient(180deg, #f8fafc 0%, #ffffff 100%);
    background-size: cover;
    background-position: center;
}
```

---

## 🚀 Running the Website

### Option 1: Open Directly
Simply double-click `index.html` to open in your browser.

### Option 2: Local Server (Recommended)
```bash
# Using Python
python3 -m http.server 8000

# Using Node.js
npx http-server

# Then open: http://localhost:8000
```

### Option 3: VS Code Live Server
1. Install "Live Server" extension in VS Code
2. Right-click `index.html`
3. Select "Open with Live Server"

---

## 🎨 Customization

### Colors
Edit CSS variables in `styles.css`:
```css
:root {
    --primary: #6366f1;        /* Main brand color */
    --secondary: #8b5cf6;      /* Secondary color */
    --accent: #06b6d4;         /* Accent highlights */
}
```

### Fonts
Change Arabic fonts in HTML `<head>`:
```html
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700;900&display=swap" rel="stylesheet">
```

### Content
All Arabic text can be edited directly in `index.html`. The structure preserves all the information from your PDF without shortening.

---

## 📱 Responsive Design

The website is fully responsive:
- **Desktop**: Full features with 3D effects and custom cursor
- **Tablet**: Optimized layout with touch-friendly interactions
- **Mobile**: Stacked sections with mobile menu

---

## ⚡ Performance

- **Lazy Loading**: Animations trigger on scroll
- **Debounced Events**: Optimized scroll listeners
- **CSS Animations**: Hardware-accelerated transforms
- **Minimal Dependencies**: No jQuery or heavy frameworks

---

## 🌐 Browser Support

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Mobile)

---

## 📄 License

Copyright © 2025–2026 — CALX & Selis

---

## 🔗 Related Files in Workspace

PDFs available for image extraction:
1. `Selis.pdf` - Main presentation
2. `Selis_Presentation_share.pdf` - Shareable deck
3. `Selis Client Profiles.pdf` - Client information
4. `Selis health wip 2.pdf` - Healthcare sector
5. `THIS_IS_SELIS_v0.17_PMI_FEB2022 copy.pdf` - Technical specs
6. `Damascus_International_Fair_v0.3_compressed (1).pdf` - Fair presentation
7. `ECZA Digital Transformation Journey v16.pdf` - Digital transformation case

---

## 💡 Tips for Best Results

1. **Extract high-quality images** (300 DPI minimum)
2. **Optimize images** before adding (use TinyPNG or ImageOptim)
3. **Use PNG for logos** and icons with transparency
4. **Use JPG for photos** and backgrounds
5. **Name files descriptively** in English (e.g., `dashboard-overview.png`)
6. **Add alt text** in Arabic for accessibility

---

## 🎯 Next Steps

1. ✅ Website structure created
2. ✅ All Arabic content added (full text, no shortening)
3. ✅ Visual design implemented
4. ✅ Animations and interactions added
5. 🔄 Extract images from PDFs (your task)
6. 🔄 Integrate images into website
7. 🔄 Test on different devices
8. 🔄 Deploy to hosting

---

## 📞 Support

For questions about the Selis platform, refer to the PDF documentation in the workspace.

---

**Built with ❤️ for Syria 🇸🇾**