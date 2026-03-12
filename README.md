# 🌸 Crave Me by Ashakky

**Premium Lingerie & Intimate Apparel E-Commerce Website**

A luxurious, fully-functional e-commerce platform for premium lingerie, sleepwear, and intimate apparel with real-time inventory management and WhatsApp order integration.

![Crave Me by Ashakky](Images/craveme-logo.jpeg)

---

## 🌟 Live Demo

- **Website:** [cravemebyashakky.vercel.app](https://cravemebyashakky.vercel.app)
- **Admin Panel:** [cravemebyashakky.vercel.app/admin.html](https://cravemebyashakky.vercel.app/admin.html)

---

## ✨ Features

### 🛍️ Customer Experience
- **41 Premium Products** across 4 categories (Panties, Sleepwear, Lingerie, Men's)
- **Smart Category Filtering** for easy product discovery
- **Responsive Design** - Perfect on desktop, tablet, and mobile
- **Animated Hero Section** with pulsing gold effects and shimmer text
- **WhatsApp Integration** - One-click ordering via WhatsApp
- **Customer Reviews** - Social proof from satisfied customers
- **How to Order Guide** - Clear 4-step ordering process

### 🎨 Design & UI
- **Luxury Brand Aesthetic** - Gold (#C9A84C) and black color scheme
- **Smooth Animations** - Fade-up effects, hover transitions, gradient shimmer
- **Professional Typography** - Playfair Display, Cormorant Garamond, Montserrat
- **High-Quality Product Images** - Hosted on GitHub with lazy loading
- **Mobile-First Design** - Hamburger menu, stacking layouts, touch-optimized

### 🔧 Admin Panel
- **Real-Time Inventory Management** - Add, edit, delete products instantly
- **Secure Login** - Password-protected admin access
- **Product Statistics** - Total products and category counts
- **Image URL Management** - Direct GitHub integration
- **Size Variations** - Customizable size options per product

### 🔥 Backend & Database
- **Supabase Backend** - PostgreSQL database with Row Level Security
- **Real-Time Updates** - Changes appear instantly on the website
- **Secure API** - Authenticated endpoints
- **Product Schema:** id, name, category, price, description, sizes, img, created_at

---

## 📁 Project Structure

```
Cravemebyashakky-Lingerie-Business-Website/
│
├── index.html                          # Main customer-facing website
├── admin.html                          # Admin panel for product management
├── upload-products-FINAL-CORRECT.html  # Bulk product upload utility
├── README.md                           # This file
│
└── Images/                             # Product images directory
    ├── craveme-logo.jpeg              # Brand logo
    ├── WhatsApp Image 2026-03-09 at 6.07.12 PM.jpeg
    ├── WhatsApp Image 2026-03-09 at 6.07.14 PM.jpeg
    ├── ... (41 product images total)
    └── WhatsApp Image 2026-03-10 at 9.36.54 AM.jpeg
```

---

## 🚀 Quick Start

### Prerequisites
- A Supabase account (free tier works)
- A Vercel account (for deployment)
- GitHub account

### 1. Database Setup

**Create Supabase Table:**

```sql
-- Create the products table
CREATE TABLE products (
  id BIGINT PRIMARY KEY,
  name TEXT NOT NULL,
  category TEXT NOT NULL,
  price TEXT NOT NULL,
  description TEXT NOT NULL,
  img TEXT NOT NULL,
  sizes TEXT[] NOT NULL,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- Enable Row Level Security
ALTER TABLE products ENABLE ROW LEVEL SECURITY;

-- Create policies for public access
CREATE POLICY "Allow public read access"
  ON products FOR SELECT TO public USING (true);

CREATE POLICY "Allow public insert access"
  ON products FOR INSERT TO public WITH CHECK (true);

CREATE POLICY "Allow public update access"
  ON products FOR UPDATE TO public USING (true) WITH CHECK (true);

CREATE POLICY "Allow public delete access"
  ON products FOR DELETE TO public USING (true);
```

### 2. Configure Supabase

**Update Supabase credentials in all HTML files:**

```javascript
const SUPABASE_URL = 'YOUR_SUPABASE_URL';
const SUPABASE_ANON_KEY = 'YOUR_SUPABASE_ANON_KEY';
```

**Files to update:**
- `index.html` (lines ~251-252)
- `admin.html` (lines ~186-187)
- `upload-products-FINAL-CORRECT.html` (lines ~41-42)

### 3. Upload Products

1. Open `upload-products-FINAL-CORRECT.html` in your browser
2. Click **"📤 Upload All 41 Products"**
3. Wait for confirmation: "✅ UPLOAD COMPLETE! Successfully uploaded: 41 products"

### 4. Deploy to Vercel

**Option A: GitHub Integration (Recommended)**

1. Push this repository to your GitHub
2. Go to [vercel.com](https://vercel.com)
3. Click **"New Project"**
4. Import your GitHub repository
5. Click **"Deploy"**
6. Your site will be live in ~30 seconds! 🎉

**Option B: Vercel CLI**

```bash
npm install -g vercel
vercel
```

### 5. Test Everything

✅ **Customer Website:**
- Visit your Vercel URL
- Verify all 41 products display
- Test category filters (Panties, Sleepwear, Lingerie, Men's)
- Click "Order on WhatsApp" and verify it opens WhatsApp

✅ **Admin Panel:**
- Visit `yoursite.vercel.app/admin.html`
- Login: `admin@craveme.com` / `admin123`
- Try adding, editing, and deleting products
- Verify changes appear on main website immediately

---

## 📦 Product Categories

| Category | Count | Price Range | Description |
|----------|-------|-------------|-------------|
| **Panties** | 7 products | ₦1,500 - ₦3,500 | Individual panties and sets with lace, cotton, and premium fabrics |
| **Sleepwear** | 19 products | ₦12,000 | Pajama sets, cami sets, silk wraps, and loungewear |
| **Lingerie** | 13 products | ₦8,000 - ₦9,000 | Luxury lingerie sets, bodysuits, and lace collections |
| **Men's** | 2 products | ₦8,000 - ₦12,000 | Premium boxers and loungewear |

---

## 🎨 Tech Stack

### Frontend
- **HTML5** - Semantic markup
- **CSS3** - Custom animations, flexbox, grid
- **Vanilla JavaScript** - No frameworks needed
- **Google Fonts** - Playfair Display, Cormorant Garamond, Montserrat

### Backend
- **Supabase** - PostgreSQL database
- **Supabase Auth** - API authentication
- **Row Level Security** - Database security

### Deployment
- **Vercel** - Automatic deployments from GitHub
- **GitHub** - Version control and image hosting

### Integrations
- **WhatsApp Business API** - Direct customer orders
- **TikTok** - Social media presence

---

## 🔐 Security Notes

### Current Configuration
⚠️ The database currently has **public access** for ease of setup. This is fine for testing but not recommended for production.

### Production Recommendations

1. **Update Admin Credentials:**
```javascript
// In admin.html, line 208:
if (email === 'YOUR_EMAIL' && password === 'YOUR_STRONG_PASSWORD') {
```

2. **Enable Supabase Auth** (Optional but recommended):
```sql
-- Update RLS policies to require authentication
CREATE POLICY "Authenticated users only"
  ON products FOR ALL TO authenticated
  USING (true) WITH CHECK (true);
```

3. **Environment Variables:**
Consider using Vercel environment variables for sensitive data:
```bash
SUPABASE_URL=your_url
SUPABASE_ANON_KEY=your_key
```

---

## 🛠️ Customization Guide

### Update Brand Colors

```css
:root {
  --gold: #C9A84C;        /* Primary brand color */
  --gold-light: #E8C97A;  /* Hover states */
  --black: #0A0A0A;       /* Background */
  --charcoal: #1A1A1A;    /* Cards */
  --cream: #F8F3EC;       /* Text */
}
```

### Update Social Media Links

**WhatsApp:**
```html
<!-- Line 131 in index.html -->
<a href="https://wa.me/YOUR_WHATSAPP_NUMBER" class="nav-whatsapp">
```

**TikTok:**
```html
<!-- Line 147 in index.html -->
<a href="https://www.tiktok.com/@YOUR_USERNAME" class="btn-secondary">
```

### Add New Products

Two ways to add products:

**Option 1: Admin Panel (Recommended)**
1. Login to admin panel
2. Click "Add New Product"
3. Fill in product details
4. Save - appears instantly on website!

**Option 2: Bulk Upload**
1. Edit `upload-products-FINAL-CORRECT.html`
2. Add product to the `products` array
3. Upload product images to `/Images/` folder on GitHub
4. Run the upload file

---

## 📊 Database Schema

```javascript
{
  id: 1,                    // Product ID (unique)
  name: "Product Name",     // Display name
  category: "panties",      // panties | sleepwear | lingerie | mens
  price: "₦1,500",         // Display price with symbol
  description: "...",       // Product description
  sizes: ["S","M","L"],     // Available sizes array
  img: "https://...",       // Full GitHub raw URL
  created_at: "2026-03-12"  // Auto-generated timestamp
}
```

---

## 🐛 Troubleshooting

### Products Not Showing

**Solution:**
1. Check browser console (F12) for errors
2. Verify Supabase credentials are correct
3. Confirm products table has data (check Supabase dashboard)
4. Hard refresh: `Ctrl+Shift+R` (Windows) or `Cmd+Shift+R` (Mac)

### Images Not Loading

**Solution:**
1. Verify image exists in `/Images/` folder on GitHub
2. Check image URL encoding (spaces = `%20`, parentheses = `%28` and `%29`)
3. Example correct URL:
   ```
   https://raw.githubusercontent.com/USERNAME/REPO/main/Images/WhatsApp%20Image%202026-03-09%20at%206.07.12%20PM.jpeg
   ```

### Admin Panel Login Not Working

**Solution:**
1. Default credentials: `admin@craveme.com` / `admin123`
2. Check if you changed credentials in `admin.html` line 208
3. Clear browser cache and try again

### WhatsApp Orders Not Opening

**Solution:**
1. Verify phone number format: `https://wa.me/2348100778348`
2. Must include country code (234 for Nigeria)
3. No spaces, dashes, or plus signs in URL

---

## 📈 Performance Optimizations

- **Lazy Loading:** All product images load only when visible
- **GPU Acceleration:** Animations use `transform` and `opacity`
- **Minimal Dependencies:** No heavy frameworks
- **CDN Delivery:** Fonts and libraries from CDN
- **Optimized Images:** Proper aspect ratios and object-fit

---

## 🔄 Version History

### v2.0.0 (Current) - March 2026
- ✅ Migrated from Firebase to Supabase
- ✅ Redesigned hero section with animations
- ✅ Simplified footer to WhatsApp + TikTok only
- ✅ Fixed all product image URLs
- ✅ Added brand logo throughout site
- ✅ Improved mobile responsiveness

### v1.0.0 - March 2026
- ✅ Initial launch with Firebase
- ✅ 41 products across 4 categories
- ✅ Admin panel for product management
- ✅ WhatsApp order integration

---

## 📞 Contact & Support

- **Website:** [cravemebyashakky.vercel.app](https://cravemebyashakky.vercel.app)
- **WhatsApp:** [+234 810 077 8348](https://wa.me/2348100778348)
- **TikTok:** [@cravemebyashakky1](https://www.tiktok.com/@cravemebyashakky1)
- **Email:** admin@craveme.com

---

## 📄 License

© 2026 Crave Me by Ashakky. All rights reserved.

This project is proprietary and confidential. Unauthorized copying, modification, distribution, or use of this software, via any medium, is strictly prohibited without explicit permission from Crave Me by Ashakky.

---

## 🙏 Acknowledgments

- **Design Inspiration:** Luxury lingerie brands worldwide
- **Icons:** Unicode emojis for simplicity
- **Fonts:** Google Fonts (Playfair Display, Cormorant Garamond, Montserrat)
- **Backend:** Supabase for reliable database services
- **Deployment:** Vercel for seamless hosting

---

## 🚀 Future Enhancements

### Planned Features
- [ ] Product search functionality
- [ ] Customer wishlist
- [ ] Multiple product images per item
- [ ] Size guide modal
- [ ] Customer testimonials submission form
- [ ] Newsletter subscription
- [ ] Discount codes system
- [ ] Order tracking
- [ ] Payment gateway integration (Paystack/Flutterwave)
- [ ] Inventory stock tracking
- [ ] Product reviews and ratings
- [ ] Related products recommendations

### Potential Integrations
- [ ] Instagram Shop integration
- [ ] Email marketing (Mailchimp)
- [ ] Analytics (Google Analytics)
- [ ] Live chat support
- [ ] SMS notifications for orders

---

## 💡 Tips for Success

1. **Update Product Images Regularly** - Fresh content keeps customers engaged
2. **Monitor Admin Panel** - Check daily for any needed updates
3. **Engage on Social Media** - Drive traffic from TikTok and Instagram
4. **Customer Service** - Respond to WhatsApp orders promptly
5. **Seasonal Collections** - Add new products for holidays and special events
6. **Pricing Strategy** - Keep prices competitive while maintaining quality perception
7. **Mobile Optimization** - Most customers shop on mobile - test regularly
8. **Loading Speed** - Optimize images before uploading to GitHub

---

## 📱 Mobile App Coming Soon?

While this is currently a web-based platform, the design is Progressive Web App (PWA) ready. Customers can:
- Add the site to their home screen
- Get an app-like experience
- Shop offline (with cached products)

---

**Built with 💛 for premium intimate apparel**

---

*For technical issues or feature requests, please contact the development team or create an issue in this repository.*
