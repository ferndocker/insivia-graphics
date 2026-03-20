# Content Strategy Map - Build Prompts

## Overview
Document the AI prompts, design decisions, and inspiration used to build this interactive content strategy visualization.

## Design System & Inspiration
- **Visual Reference:** `chart.png` - Wireframe of the content strategy flow
- **UI Library:** Insivia HTML Graphics Library
- **Theme:** Dark glassmorphism with ambient gradient blobs
- **Icons:** Lucide Icons

## Prompts Used

### 1. Initial Concept
**Prompt:** Create an interactive SVG visualization of a B2B content strategy framework with draggable nodes representing different content types (commercial intent, question pages, thesis pages, proof pages, trend pages).

**Result:** 7-node interactive map with bezier curve connections showing relationships between content types.

### 2. Node Styling & Animation
**Prompt:** Design a glassmorphism card component with backdrop blur, gradient accents, and spring animations for node entrance and hover states.

**Result:** Smooth staggered entrance animations with accent bars and responsive glow effects.

### 3. Connection Logic
**Prompt:** Create bezier curve paths between nodes that automatically recalculate positions when nodes are dragged. Add colored arrow markers to indicate connection direction.

**Result:** Real-time SVG path updates with control point offset calculation based on connection distance.

### 4. Local Storage Integration
**Prompt:** Implement local storage to save node positions when users rearrange them, with a reset button to restore defaults.

**Result:** Automatic position persistence across page refreshes with one-click layout reset.

### 5. Tooltip System
**Prompt:** Create an information badge system that appears when hovering over connection arrows, showing strategic context for each relationship.

**Result:** Positioned tooltips with dot indicators matching edge colors and detailed explanations.

## Technical Stack
- Vanilla HTML/CSS/JavaScript (no frameworks)
- SVG for vector graphics and animations
- Local Storage API for persistence
- Cubic bezier animation timing functions
- CSS Grid for responsive layout

## Future Enhancements
- Export functionality (PNG/SVG)
- Collaborative editing with real-time sync
- Additional content strategy templates
- Mobile-optimized touch interactions

---
*Last updated: March 20, 2026*
