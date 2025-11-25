# Design Guidelines: Personal Aesthetic Galaxy Portfolio

## Design Approach
**Reference-Based: Aesthetic Portfolio Platforms**
Inspired by personal creative portfolios with immersive, atmospheric experiences. Think Awwwards-winning portfolio sites with bold animations and cosmic aesthetics. The design prioritizes emotional impact through visual storytelling with a dreamy, space-themed aesthetic.

**Core Principles:**
- Immersive full-screen experience with atmospheric depth
- Minimal UI with maximum visual impact
- Smooth, elegant animations that enhance rather than distract
- Personal, intimate connection through simplified navigation

---

## Typography

**Font Family:**
- Primary: 'Poppins' (Google Fonts)
- Weights: 300 (Light), 500 (Medium), 600 (Semi-Bold), 700 (Bold)

**Type Scale:**
- Hero Heading: 60px (3.75rem) - weight 600
- Menu Items: 22px (1.375rem) - weight 500
- All text: White with luminous text-shadows for ethereal glow effect

**Text Shadows:**
- Hero text: `0 0 25px rgba(255,255,255,0.7), 0 0 50px rgba(120,150,255,0.6)`
- Menu items: `0 0 10px rgba(0,0,0,0.7)` (default), `0 0 20px rgba(180,210,255,0.9)` (hover)

---

## Layout System

**Spacing:**
- Use Tailwind units: 2, 4, 8, 10, 12 for consistent spacing
- Menu gap: 40px (10 units)
- Generous breathing room around all elements

**Container:**
- Full viewport height (100vh) hero section
- Center-aligned content using absolute positioning
- Hero text: top 30%, center horizontal
- Menu: top 55%, center horizontal

**Responsive:**
- Mobile-first approach
- Stack menu items vertically on mobile
- Reduce font sizes appropriately (hero: 40px, menu: 18px on mobile)

---

## Component Library

### Hero Section
- Full-screen immersive experience
- Galaxy background image with subtle floating animation (20s ease-in-out loop)
- Layered depth with meteors and content on top
- No traditional header/navigation bar

### Navigation Menu
- Horizontal list layout (flex, gap-10)
- Three clickable items linking to external profiles/contact
- No icons, pure typography
- Hover state: scale to 1.18, slight upward translateY(-3px), enhanced glow

### Meteor Animation Elements
- 8 meteor streaks falling diagonally
- Thin (2px width, 90px height) white gradient trails
- Staggered delays (0s to 6.8s) for continuous shower effect
- 45-degree angle, top-right to bottom-left trajectory
- 4s animation duration per meteor

### Background Music Player
- Auto-playing audio element (music.mp3)
- Looping playback
- Hidden UI (no visible controls)

---

## Animations

**Text Entrance:**
- Hero "hello" text: Fade in from opacity 0 to 1 with upward slide (3.5s ease forwards)
- Menu: Same fade-in pattern but delayed to 6.5s for sequential reveal

**Background:**
- Subtle scale breathing animation (1.05 to 1.06) with slight vertical float
- 20s duration for dreamy, gentle movement

**Interactive:**
- Menu hover: Simultaneous scale (1.18), translateY(-3px), and glow enhancement
- 0.3s transition for smooth responsiveness

**Decorative:**
- Meteors continuously falling with opacity fade-in/out
- Natural physics simulation for authentic shooting star effect

---

## Images

**Hero Background:**
- Full-screen galaxy/space photograph
- Two variants provided: 1344005.jpeg (darker) and 1354384.png (brighter variant)
- Should be high-resolution (1920x1080 minimum)
- Object-fit: cover to maintain aspect ratio
- Slight brightness filter (0.92) for text readability
- Cosmic aesthetic with purples, blues, and starfield details

**Image Treatment:**
- Animated with floating/breathing effect
- Serves as the entire page backdrop
- No overlays or gradients - pure image with CSS animation

**Placement:**
- Position: absolute, full width/height
- Z-index: lowest layer
- Background images should be uploaded to Replit static assets folder

---

## Notes for Implementation

- Convert local file paths (C:/Users/...) to Replit-compatible public paths
- Upload all assets (images, audio) to public/static directory
- Ensure mobile viewport meta tag for responsive behavior
- Test music autoplay (may require user interaction in modern browsers)
- Validate all external links (Instagram, WhatsApp) are correct
- Clean up duplicate HTML elements in original code structure