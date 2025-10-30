# Vivek - Video Editor Portfolio

A sleek, cinematic one-page portfolio website for freelance video editor Vivek, featuring a modern black and neon blue design with smooth animations and interactive elements.

## ✨ Features

- **Cinematic Hero Section** - Full-screen video background with animated tagline
- **Responsive Navigation** - Fixed navbar with smooth scrolling
- **About Section** - Professional introduction and tools showcase
- **Services Section** - 5 animated service cards highlighting expertise
- **Portfolio Section** - 9 project cards with category filtering
- **Testimonials** - Client reviews with elegant styling
- **Contact Form** - Minimalist contact form with social media links
- **Smooth Animations** - Intersection Observer, parallax effects, and micro-interactions
- **Fully Responsive** - Optimized for all device sizes

## 🎨 Design Style

- Black background (#000000)
- Neon blue highlights (#00d4ff)
- Cinematic typography (Playfair Display + Montserrat)
- Smooth transitions and animations
- Modern, minimalist aesthetic

## 🚀 Getting Started

### Prerequisites

- A modern web browser (Chrome, Firefox, Safari, Edge)
- A local development server (optional, for testing)

### Installation

1. Clone or download this repository
2. Open the project folder
3. Open `index.html` in your web browser

Or use a local server:

```bash
# Using Python 3
python -m http.server 8000

# Using Node.js (http-server)
npx http-server

# Using PHP
php -S localhost:8000
```

Then navigate to `http://localhost:8000` in your browser.

## 📁 Project Structure

```
vivek-portfolio/
├── index.html          # Main HTML file
├── styles.css          # CSS styling and animations
├── script.js           # JavaScript interactions
├── README.md           # Project documentation
└── assets/             # Assets folder (create this)
    ├── hero-video.mp4  # Hero section background video
    └── portfolio/      # Portfolio project images
        ├── project-1.jpg
        ├── project-2.jpg
        └── ...
```

## 🎬 Adding Content

### Hero Video

1. Create an `assets` folder in the project root
2. Add your hero video as `hero-video.mp4`
3. Recommended: 1920x1080, under 10MB, looping-friendly

### Portfolio Images

1. Create `assets/portfolio/` folder
2. Add portfolio images as `project-1.jpg`, `project-2.jpg`, etc.
3. Recommended size: 1280x720 or 1920x1080
4. Update image names in `index.html` if needed

### Customizing Content

#### Personal Information
- Edit name, tagline, and about text in `index.html`
- Update social media links (Instagram, YouTube, LinkedIn)

#### Services
- Modify service cards in the Services section
- Change icons, titles, and descriptions

#### Portfolio Projects
- Update project titles and categories
- Change the `data-category` attribute for filtering
- Add or remove projects as needed

#### Testimonials
- Edit client quotes and information
- Add more testimonial cards by copying the structure

## 🎨 Customization

### Colors

Edit CSS variables in `styles.css`:

```css
:root {
    --neon-blue: #00d4ff;          /* Primary accent color */
    --neon-blue-glow: rgba(0, 212, 255, 0.5);
    --dark-bg: #000000;            /* Main background */
    --dark-bg-alt: #0a0a0a;        /* Alternate background */
    --text-primary: #ffffff;       /* Primary text */
    --text-secondary: #b0b0b0;     /* Secondary text */
}
```

### Typography

Change fonts in `index.html`:

```html
<link href="https://fonts.googleapis.com/css2?family=YourFont&display=swap" rel="stylesheet">
```

Update font-family in `styles.css`:

```css
body {
    font-family: 'YourFont', sans-serif;
}
```

### Animations

Adjust animation speeds in `styles.css` and `script.js`:

```css
--transition-smooth: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
```

## 📱 Responsive Breakpoints

- Desktop: 1200px+
- Tablet: 768px - 1199px
- Mobile: 480px - 767px
- Small Mobile: < 480px

## 🔧 Technologies Used

- HTML5
- CSS3 (Grid, Flexbox, Animations)
- Vanilla JavaScript (ES6+)
- Google Fonts
- Intersection Observer API

## 📝 Form Integration

The contact form currently shows an alert on submission. To connect it to a backend:

### Option 1: FormSubmit.co
```html
<form action="https://formsubmit.co/your@email.com" method="POST">
```

### Option 2: Netlify Forms
```html
<form name="contact" method="POST" data-netlify="true">
```

### Option 3: Custom Backend
Modify the form submit handler in `script.js` to send data to your API endpoint.

## 🚀 Deployment

### GitHub Pages
1. Push to GitHub repository
2. Go to Settings > Pages
3. Select main branch
4. Site will be live at `https://username.github.io/repo-name`

### Netlify
1. Drag and drop folder to Netlify
2. Or connect GitHub repository
3. Site deploys automatically

### Vercel
```bash
npm i -g vercel
vercel
```

## 🎯 Performance Tips

1. Compress hero video (use H.264, reduce file size)
2. Optimize portfolio images (use WebP format)
3. Consider lazy loading for images
4. Minify CSS and JavaScript for production
5. Use a CDN for faster global delivery

## 📄 License

This project is open source and available for personal and commercial use.

## 👤 Author

**Vivek** - Video Editor

- Instagram: [@vivek](https://instagram.com/vivek)
- YouTube: [@vivek](https://youtube.com/@vivek)
- LinkedIn: [Vivek](https://linkedin.com/in/vivek)

---

**Crafting Stories Frame by Frame** 🎬✨
