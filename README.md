# Embryo-AI Website Audit Presentation

A 12-slide HTML presentation created from the MaruOnline audit report for Embryo-AI website.

## Overview

This presentation summarizes the top-line website audit findings for embryo-ai.co.za, prepared by Jimmy Motsei of MaruOnline. The audit covers rendering, SEO, performance, accessibility, and security aspects of the website.

## Files Structure

```
Embryo-Ai/
├── index.html          # Main presentation file
├── slides.md           # 12 slides in Markdown format
├── styles.css          # MaruOnline brand styling
├── assets/             # Assets directory (for logo if needed)
└── README.md           # This file
```

## How to View the Presentation

### Option 1: Direct File Opening
1. Navigate to the project directory
2. Double-click `index.html` to open in your default browser
3. Use arrow keys or click to navigate between slides

### Option 2: Local Server (Recommended)
1. Open terminal in the project directory
2. Run a local server:
   ```bash
   # Python 3
   python -m http.server 8000
   
   # Python 2
   python -m SimpleHTTPServer 8000
   
   # Node.js (if you have it)
   npx serve .
   ```
3. Open `http://localhost:8000` in your browser

## Navigation Controls

- **Arrow Keys**: Navigate between slides
- **Space Bar**: Next slide
- **Shift + Space**: Previous slide
- **Home**: First slide
- **End**: Last slide
- **ESC**: Overview mode
- **F**: Fullscreen mode
- **S**: Speaker notes (if available)

## Printing to PDF

### Method 1: Browser Print
1. Open the presentation in your browser
2. Press `Ctrl+P` (Windows/Linux) or `Cmd+P` (Mac)
3. Select "Save as PDF" as destination
4. Choose "More settings" and select "Background graphics" for colors
5. Print

### Method 2: Print Mode URL
1. Add `?print-pdf` to the URL: `http://localhost:8000?print-pdf`
2. Press `Ctrl+P` or `Cmd+P` to print
3. This method provides better formatting for PDF output

## Customization

### Editing Content
- Edit `slides.md` to modify slide content
- Use standard Markdown syntax
- Separate slides with `---` on a new line

### Styling
- Modify `styles.css` to change colors, fonts, or layout
- Brand colors are defined as CSS variables:
  - `--maru-heading`: #4A5A63 (slate grey)
  - `--maru-accent`: #78B2BE (teal)

### Adding Logo
- Place `MaruOnline_logo.png` in the `assets/` directory
- The logo will automatically appear on the title slide

## Technical Details

- **Framework**: Reveal.js 4.3.1 (loaded via CDN)
- **Styling**: Custom CSS with MaruOnline brand colors
- **Responsive**: Optimized for 1280×720 and mobile devices
- **Accessibility**: Keyboard navigation and screen reader support
- **Print Support**: Clean PDF output with proper formatting

## Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge)
- Internet connection (for CDN resources)
- No build process required - static files only

## Troubleshooting

- If slides don't load, check browser console for errors
- Ensure `slides.md` file is in the same directory as `index.html`
- For local server issues, try a different port or method
- Clear browser cache if styling appears incorrect
