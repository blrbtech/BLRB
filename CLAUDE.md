# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

BLRB (newsletter for builders) is a tech newsletter website project that has been extensively developed as a sophisticated single-page application. The project features a dark theme design with blue/cyan gradient branding, dynamic content lanes, smooth animations, and mobile-first responsive design.

## Current Status: FULLY FUNCTIONAL DEMO

The project now has a complete, working demonstration website with advanced features:

### Primary Working Files
- **`index.html`** - Main production-ready demo with latest enhancements
- **`blrb-demo-v2.html`** - Alternative demo version
  
Both files feature:
  - Complete lane system (AI, TECH, PRODUCTS, DEV, CRYPTO)
  - Full-width "Today's Hits" carousel with optimized gradients and smart arrows
  - Mobile swipe gestures between lanes
  - Bottom sheet BLRB explainer panels
  - Professional subscribe popup with form fields
  - Clean hamburger menu with navigation
  - Smooth animations and transitions
  - Modern article card design with sharp corners

### Development Setup
- **Local Server**: Use `python -m http.server 8000` for proper file serving
- **Primary URL**: `http://localhost:8000/index.html` (latest version)
- **Alternative URL**: `http://localhost:8000/blrb-demo-v2.html`
- **Testing**: Both desktop and mobile interactions work seamlessly

## Technical Architecture

### Design System
- **Primary Color**: `#00b4ff` (Electric Blue)
- **Accent Color**: `#20d3ce` (Cyan)
- **Background**: Pure black (`#000000`)
- **Framework**: Tailwind CSS via CDN
- **Typography**: System fonts with gradient text effects

### Core Features Implemented
1. **Today's Hits Carousel** - Full-width with gradient overlays and centered arrows
2. **Dynamic Lane System** - 5 content categories with 10 articles each
3. **Smooth Sliding Animations** - Distance-based transition timing
4. **Mobile Swipe Support** - Touch gesture navigation between lanes
5. **BLRB Bottom Sheets** - Detailed story explainer panels
6. **Professional Subscribe Form** - Name/email fields with refined typography
7. **Hamburger Menu** - Clean dropdown with Newsletter/About/Contact
8. **Responsive Design** - Mobile-first with desktop enhancements

## File Structure & Status

```
F:\BLRB\3_WEBSITE/
├── index.html                  # ✅ PRIMARY DEMO - Latest version with all enhancements
├── blrb-demo-v2.html           # ✅ ALTERNATIVE DEMO - Full featured site
├── blrb-demo.html              # ⚠️  Legacy demo - Basic features
├── BLRB_FRONTEND_LLM.json      # 📋 Original specification document
├── BLRB_FRONT_END_MOCK_UP.png  # 🎨 Design mockup reference
├── CLAUDE.md                   # 📝 This documentation file
└── blrb-web/                   # 🚧 Next.js version (partially built)
    ├── src/app/page.tsx        # Basic Next.js implementation
    ├── package.json            # Dependencies configured
    └── [standard Next.js structure]
```

## Key Implementation Details

### Lane System Architecture
- **Preloaded Content**: All 50 articles (10 per lane) loaded on page load
- **Horizontal Container**: CSS transforms for smooth sliding
- **Lane Positions**: AI=0, TECH=1, PRODUCTS=2, DEV=3, CRYPTO=4
- **Distance-Based Animation**: Longer lane jumps = longer transition time

### Today's Hits Carousel
- **5 Featured Stories**: GPT-5, Vision Pro 2, Microsoft AI Deal, Copilot Workspace, Ethereum Staking
- **Full-Width Design**: Extends edge-to-edge with single story visibility
- **Optimized Gradients**: Soft black-to-transparent fade (80% → 20% → transparent)
- **Smart Navigation Arrows**: Only visible when scrolling is possible (hide at first/last)
- **Clean Interactions**: Headlines/text link to articles, BLRB buttons open detailed views
- **No Source Labels**: Streamlined design without redundant topic/source text
- **Smooth Scrolling**: CSS snap points with proper touch support
- **Hidden Scrollbars**: Clean visual appearance

### Mobile Interaction
- **Touch Events**: Proper horizontal swipe detection
- **Vertical Scroll Preservation**: Doesn't interfere with page scrolling
- **Swipe Thresholds**: 50px minimum distance, 500ms maximum time
- **Touch Action**: `pan-y` to allow vertical scrolling

### Content Structure
- **Story Objects**: Each has lane, source, title, blurb, and unique ID
- **Mock Publishers**: TechCrunch, The Verge, Bloomberg, GitHub, CoinDesk, etc.
- **Realistic Content**: All articles have believable tech news headlines

## Development Workflow

### To Continue Development:
1. **Start Local Server**: `python -m http.server 8000`
2. **Open Demo**: Navigate to `http://localhost:8000/index.html` (primary) or `blrb-demo-v2.html`
3. **Edit HTML File**: Make changes to `index.html` for latest version
4. **Test Features**: Verify lane switching, hits scrolling, mobile swipe, article interactions

### Key Functions to Know:
- `selectLane(button)` - Handles lane navigation clicks
- `slideToLane(laneName, distance)` - Animates between lanes
- `setupSwipeHandlers()` - Initializes touch gesture support
- `setupHitsScrolling()` - Enables hits carousel navigation
- `openBlrb(storyId)` - Opens bottom sheet explainer
- `openSubscribe()` - Opens newsletter signup popup
- `closeSubscribe()` - Closes newsletter signup popup
- `toggleDropdown()` - Handles hamburger menu dropdown
- `setupMenuHandlers()` - Initializes navigation menu system

### Testing Checklist:
- ✅ Desktop lane clicking works
- ✅ Mobile swiping between lanes works  
- ✅ Lane selection shows blue rounded rectangle (not just text color)
- ✅ Lanes properly span full width on mobile without scrolling
- ✅ Today's Hits carousel with optimized gradients works
- ✅ Smart arrows hide/show based on scroll position
- ✅ Today's Hits click behavior: thumbnails inactive, headlines/text link out, BLRB opens sheets
- ✅ Article cards have modern layout with right-side 9:16 thumbnails
- ✅ All elements have sharp corners (no rounded borders)
- ✅ BLRB bottom sheets open/close
- ✅ Hamburger menu dropdown opens/closes
- ✅ Newsletter menu item opens subscribe popup
- ✅ Subscribe popup with name/email form works
- ✅ All click-outside-to-close functionality works
- ✅ Responsive design scales properly

## Future Development Notes

### If Building Next.js Version:
- Reference `blrb-web/src/app/page.tsx` for component structure
- Port the lane system logic to React state management
- Convert CSS animations to Framer Motion or similar
- Implement proper data fetching for story content

### If Enhancing HTML Demo:
- All core functionality is complete and working
- Focus on content updates, visual polish, or performance
- The architecture supports easy content additions

### Performance Considerations:
- Current demo loads 50 articles on page load (acceptable for demo)
- For production, consider lazy loading lane content
- Image assets are currently placeholder gradients (by design)

## Brand Guidelines
- **Tone**: Technical, direct, builder-focused
- **Colors**: Electric blue (#00b4ff) + Cyan (#20d3ce) gradients only
- **Typography**: Bold, uppercase tracking for headers
- **Design Philosophy**: Clean, architectural feel with sharp corners (no rounded edges)
- **Interactions**: Smooth, premium feel with proper easing
- **Mobile-First**: Touch interactions are primary UX
- **Subscribe Form**: Professional with tight spacing, larger blue headings
- **Navigation**: Minimal dropdown over complex sliding panels

## Quick Reference Commands

```bash
# Start development server
python -m http.server 8000

# Open primary demo (latest)
start http://localhost:8000/index.html

# Open alternative demo
start http://localhost:8000/blrb-demo-v2.html

# View files
ls F:\BLRB\3_WEBSITE
```

## Recent Major Updates

### August 12, 2025 - UX Enhancements & Modern Card Design
- **Today's Hits Improvements**: White heading text, reduced gradient opacity (20% → 10%), softer edge transitions
- **Smart Navigation**: Arrows only show when scrolling is possible, eliminated redundant source labels
- **Click Behavior Optimization**: Headlines/paragraphs link to articles, BLRB buttons open detailed views
- **Lane Navigation Redesign**: Blue rounded rectangle selection instead of text color, responsive full-width mobile layout
- **Modern Article Cards**: Sharp corners throughout, right-side 9:16 portrait thumbnails, top-right BLRB buttons
- **Typography Hierarchy**: Improved text sizing and spacing for better readability

### August 11, 2025 - Navigation & Form Enhancements
- **Hamburger Menu**: Added clean dropdown navigation (Newsletter/About Us/Contact)
- **Subscribe Popup Redesign**: Added First Name and Email form fields
- **Typography Improvements**: Larger BLRB logo, bigger blue feature headings
- **Design Refinements**: Sharp corners throughout, tighter spacing, better alignment
- **Integration**: Newsletter menu item connects to subscribe popup

---
*Last updated: August 12, 2025 - Modern card design and enhanced user experience complete*