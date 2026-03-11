# Craveme by Ashakky - Lingerie E-Commerce Website

A premium lingerie and intimate apparel e-commerce website featuring 41 products across 3 main categories.

## 🎨 Features

- **Responsive Design**: Mobile-first, works beautifully on all devices
- **Product Categories**: 
  - Intimates (7 products)
  - Sleepwear & Loungewear (19 products)
  - Luxury Lingerie (15 products)
- **Smart Filtering**: Category-based product filtering
- **Professional UI**: Elegant design with smooth animations
- **Product Images**: Direct integration with GitHub repository images
- **Shopping Cart**: Add-to-cart functionality (ready for backend integration)

## 📦 Products Included

### Intimates (₦1,500 - ₦3,500)
- Individual Panties
- Panty Sets
- Cotton Comfort styles
- Lace designs

### Sleepwear & Loungewear (₦12,000)
- Pajama Sets (15 styles)
- Cami Sets
- Silk Wraps
- Short Sets
- Men's Boxers

### Luxury Lingerie (₦8,000 - ₦9,000)
- Designer Lingerie Sets
- Bodysuits
- Premium Lace Collections
- Men's Premium Boxers

## 🚀 Deploying to Vercel

### Method 1: GitHub Integration (Recommended)

1. **Push your code to GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit - Craveme by Ashakky website"
   git branch -M main
   git remote add origin https://github.com/Temmygabriel/Cravemebyashakky-Lingerie-Business-Website.git
   git push -u origin main
   ```

2. **Deploy on Vercel**
   - Go to [vercel.com](https://vercel.com)
   - Click "New Project"
   - Import your GitHub repository
   - Vercel will auto-detect it's a static site
   - Click "Deploy"
   - Your site will be live in ~30 seconds!

### Method 2: Vercel CLI

1. **Install Vercel CLI**
   ```bash
   npm install -g vercel
   ```

2. **Deploy**
   ```bash
   vercel
   ```
   Follow the prompts and your site will be deployed instantly.

### Method 3: Drag & Drop

1. Go to [vercel.com](https://vercel.com)
2. Drag and drop the `index.html` file
3. Instant deployment!

## 📁 File Structure

```
├── index.html          # Main website file (complete and standalone)
├── Images/            # Product images (in your GitHub repo)
└── README.md          # This file
```

## 🔧 Customization

### Updating Products

All product data is embedded in the `index.html` file in the `productsData` JavaScript object. To add/edit products:

1. Locate the `<script>` section near the bottom of `index.html`
2. Find the `productsData` object
3. Add/modify products following this structure:

```javascript
{
    "Category": "Luxury",
    "Product Type": "Lingerie Set",
    "Gender": "Female",
    "Product Name": "Your Product Name",
    "Price": 8000,
    "Image File Path": "Images/your-image.jpeg",
    "Refined Category": "Luxury Lingerie",
    "Image URL": "https://raw.githubusercontent.com/Temmygabriel/Cravemebyashakky-Lingerie-Business-Website/main/Images/your-image.jpeg"
}
```

### Adding New Images

1. Upload images to your GitHub repository's `Images/` folder
2. Update the product's `Image File Path` and `Image URL` accordingly
3. Image URLs use this format:
   ```
   https://raw.githubusercontent.com/USERNAME/REPO-NAME/main/Images/FILENAME.jpeg
   ```

### Changing Colors

Edit the CSS variables in the `:root` section:

```css
:root {
    --primary-color: #d4af37;      /* Gold accent */
    --secondary-color: #2c1810;    /* Dark brown */
    --accent-color: #8b4513;       /* Medium brown */
    --light-bg: #faf8f5;           /* Off-white background */
}
```

## 🎯 Improvements Made

Based on industry best practices and competitor research, I've:

1. **Enhanced Category Names**:
   - "Panties" → "Intimates" (more professional)
   - "Premium Sets" → "Sleepwear & Loungewear" (more descriptive)
   - "Luxury" → "Luxury Lingerie" (clearer positioning)

2. **Refined Product Names**:
   - More evocative and descriptive
   - Better SEO optimization
   - Luxury-focused naming conventions

3. **Professional Design**:
   - Elegant color scheme (gold, dark brown, warm tones)
   - Smooth animations and transitions
   - High-end aesthetic matching luxury lingerie brands

4. **Better User Experience**:
   - Easy category filtering
   - Clear product hierarchy
   - Mobile-responsive design
   - Fast loading times

## 💡 Next Steps for Full E-Commerce

To make this a complete e-commerce site, consider adding:

1. **Backend Integration**
   - Node.js + Express server
   - Database (MongoDB/PostgreSQL)
   - Payment gateway (Paystack, Flutterwave for Nigeria)

2. **Features to Add**
   - User authentication
   - Shopping cart with persistent storage
   - Checkout process
   - Order management
   - Admin panel for product management
   - Size selection
   - Product reviews
   - Wishlist functionality

3. **Marketing Features**
   - Newsletter subscription
   - Discount codes
   - Product recommendations
   - Related products
   - Customer testimonials

## 📱 Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers

## 📞 Support

For questions or issues with the website, contact:
- Email: info@cravemebyashakky.com
- GitHub: [Your Repository Issues](https://github.com/Temmygabriel/Cravemebyashakky-Lingerie-Business-Website/issues)

## 📄 License

© 2026 Craveme by Ashakky. All rights reserved.

---

**Note**: All product images are loaded directly from your GitHub repository. Make sure the Images folder in your repository remains public for the images to display correctly.
