# SOFTBIKE Bootstrap Project - Copilot Instructions

## Project Overview
SOFTBIKE is a web-based bicycle shop portfolio website built for an academic web development course (ADS - Análise e Desenvolvimento de Sistemas). The project demonstrates Bootstrap 5.1.3 implementation with multi-page navigation, image galleries, and semantic HTML structure.

**Key Context:**
- Course/Discipline: Desenvolvimento Web (Web Development)
- Theme: E-commerce showcase for bicycle products
- Status: Educational project with extensive HTML/CSS comments for teaching purposes

## Architecture & Structure

### Page Organization
The site follows a hub-and-spoke model with `index.html` as the entry point:
- **Hub pages:** `index.html` (home/landing)
- **Content pages:** `empresa.html` (company info), `produtos.html` (product gallery), `texto.html` (text content), `listas.html` (list examples), `tabela.html` (table examples), `links.html` (link examples)
- **Reference page:** `wireframe.html` (project documentation/wireframes)
- **Assets:** `/imagens/` folder contains product SVG images (`produto1.svg` through `produto25.svg`)

### Navigation Pattern
Every page includes:
1. **Collapsible navbar** (`navbarToggleExternalContent`) - contains project title and context
2. **Primary navbar** (dark, with brand logo) - navigation to home
3. **Secondary menu** (light, horizontal links) - navigation between all 8 pages

This three-layer structure is repeated across all pages - keep it consistent when modifying navigation.

## Key Conventions & Patterns

### Bootstrap & Styling
- **Bootstrap version:** 5.1.3 (CDN link in every page `<head>`)
- **CSS strategy:** Bootstrap handles 95% of styling; `style.css` contains only supplementary customizations
- **Custom classes:** Used sparingly for educational purposes:
  - `.menu-link` - secondary menu styling with hover effects
  - `.hero-softbike` - hero section background and layout
  - `.gallery-image` - product card images (220px height, cover fit)
  - `.section-title` - centered section headings
  - `.wire-box` - wireframe documentation styling

### HTML Patterns
- **Language:** Portuguese (pt-br) in all `lang` attributes
- **Comments:** Extensive inline comments in HTML explain Bootstrap classes for teaching
- **Anchors:** Each page includes `<a id="inicio"></a>` for "back to top" functionality
- **Image optimization:** Product gallery uses `.gallery-image` class with `object-fit: cover` for consistent aspect ratios
- **Cards:** Product cards use Bootstrap's `.card` class with shadow effects (`shadow-sm`)

### Responsive Design
- **Breakpoints:** Leverages Bootstrap's grid system (`col-md-6 col-lg-4`)
- **Product gallery:** 3-column layout on desktop, 2 columns on tablet, 1 on mobile
- **Viewport:** All pages include `<meta name="viewport" content="width=device-width, initial-scale=1.0">`

## Critical Implementation Details

### Product Gallery (produtos.html)
- **Structure:** Grid with `row g-4` (gap spacing) containing 25+ product cards
- **Each card:** Contains SVG image → title → description text
- **Classes:** `col-md-6 col-lg-4` for responsive columns, `.card.shadow-sm.h-100` for equal heights
- **Image format:** SVG from `/imagens/` folder with alt text matching product number

### Content Pages
All content pages follow the same template structure:
1. Doctype → HTML with pt-br lang
2. Head: charset, viewport, Bootstrap CDN, style.css link
3. Body: inicio anchor → collapse menu → navbar → secondary menu → content section → footer (if present)

## CSS Customization Guidelines

### When Modifying style.css
- **Hero section:** `.hero-softbike` sets background and min-height - adjust for page-specific heights
- **Card images:** `.gallery-image` height (220px) and `object-fit: cover` - balance with container width
- **Menu styling:** `.menu-link` and `.menu-link:hover` define navigation appearance - maintain hover feedback
- **Keep Bootstrap integration:** Never override Bootstrap's core spacing/layout; only add supplementary styles

### Color Scheme
- Primary dark color: `#1f1f1f` (dark text), `#0d6efd` (Bootstrap primary blue on hover)
- Background: `#f1f1f1` (light gray body), `#ececec` (hero section)
- Navigation: `.bg-dark` (dark navbar), `.bg-light` (secondary menu)

## Developer Workflows

### Adding New Pages
1. Copy any existing HTML file (e.g., `texto.html`)
2. Keep all three navigation layers intact
3. Ensure `<title>` follows pattern: `SOFTBIKE - [Page Name]`
4. Add link to secondary menu in ALL pages (update all 8 files)
5. Update `wireframe.html` documentation if needed

### Adding Products to Gallery
1. Add SVG image to `/imagens/` folder (naming: `produtoN.svg`)
2. Duplicate a product card block in `produtos.html`
3. Update image src and alt text
4. Keep card structure: `col-md-6 col-lg-4` → `.card.shadow-sm` → image + body

### Image Asset Management
- **Format:** SVG preferred (scalable, light weight)
- **Naming:** `produtoN.svg` where N is sequential
- **Location:** `/imagens/` folder only
- **Size consideration:** Gallery images set to 220px height via `.gallery-image` class

## Testing & Validation

### Cross-Page Consistency
- Verify navigation links work on all pages (8 links each)
- Test responsive layout at mobile (375px), tablet (768px), desktop (1200px+)
- Check that secondary menu styling remains consistent

### Common Issues to Avoid
- **Navigation breakage:** If renaming HTML files, update href attributes in ALL secondary menus
- **Image missing:** Verify paths use relative links (`imagens/produtoN.svg`), not absolute
- **Bootstrap override conflicts:** Check custom CSS doesn't use `!important` unless fixing Bootstrap conflicts (one exception: `.card img border-radius`)

## Integration & Dependencies
- **External:** Bootstrap 5.1.3 CDN only (no JS plugins beyond Bootstrap's built-in)
- **Local:** Single custom stylesheet `style.css`
- **Cross-file:** All pages reference same CSS and image folder - changes affect entire site
- **No backend:** Static HTML/CSS project - no server-side processing or databases

## Notes for AI Agents
- This is an **educational, commented codebase** - preserve inline comments explaining Bootstrap concepts
- The repetitive navigation structure is **intentional for teaching** - consistency across pages is critical
- Wireframe.html is a **documentation artifact** - may contain design references or requirements
- When suggesting improvements, prioritize **maintainability and clarity** over cutting-edge patterns
