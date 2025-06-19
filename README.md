# 🏡 Houzeo-UI

A modern Vue.js + Vite real estate listing UI that mimics a Zillow-like interface. Built for responsiveness, smooth animations, and a clean user experience.

---

## 📌 Project Requirements (Implemented)

### ✅ 1. Header
- A header with a centered logo and clean layout.

### ✅ 2. Filter Bar
- **Status Dropdown**: "For Sale" / "Sold".
- **Price Dropdown**: Multiple price range options.
- **Save Buttons**: "Saved" and "Save Search".
- **Smooth Border Hover Effects**: CSS transitions applied to all filter inputs and dropdowns.

### ✅ 3. Map Section
- Displays a Live US map on the left embedded from Google Maps.
- Basic functionality to the map, such as zooming & exploring city.

### ✅ 4. Property Listings Section
- **Image Slider**: Carousel with arrows and bullets on hover.
- **Details Included**:
  - Property Type (e.g., House For Sale)
  - Price
  - Beds, Baths, Sqft
  - Address
  - Days on Market
  - Favorite Icon (Heart) with CSS pulse on hover
- **Hover Effects**: Smooth box-shadow transition on property card hover.

### ✅ 5. Sorting Option
- Dropdown with "Listing", "Price", and other static options (non-functional for now).

### ✅ 6. Responsive Design
- **Desktop**: Side-by-side layout with map and listings.
- **Mobile**: Stack layout optimized for iPhone 14 Pro Max.
  - Listings display full width.
  - Map collapses/adjusts behind the listings.

### ✅ 7. Performance Optimizations
- Lazy loading of images for faster page load.
- Optimized layout for performance across devices.

### ✅ 8. Reusable Component
- Reusable Card Component handles Dynamic Data.
- API can be integrated to make webite more dynamic.

### ✅ 9. Component Testing
- Components Manual Tested using DevTools

---

## 🚀 How to Run the Project

### 🔧 Prerequisites
- Node.js >= 14.x
- npm or pnpm installed

### 📥 Installation

```bash
git clone https://github.com/Rehan9-12/Houzeo-UI.git
cd Houzeo-UI
npm install   # or pnpm install
npm run dev
