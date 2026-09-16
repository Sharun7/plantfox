# PlantFox Frontend

## 📁 Files Structure

```
frontend/
├── plantfox_landing.html       # Main landing page
├── plantfox_auth_landing.html  # Auth landing page
├── plantfox_login.html         # Login page
├── plantfox_register.html      # Registration page
├── plantfox_dashboard.html     # User dashboard
├── plantfox_splash.html        # Mobile splash screen
├── config.js                   # API configuration
├── vercel.json                 # Vercel deployment config
└── .vercelignore              # Files to ignore during deployment
```

## 🚀 Deployment to Vercel

### Step 1: Update config.js
Before deploying, update `config.js` with your cloudflare tunnel URL:

```javascript
const CONFIG = {
  API: "https://your-tunnel-url.trycloudflare.com"
};
```

### Step 2: Deploy to Vercel

**Option A: Using Vercel CLI**
```bash
cd frontend
vercel --prod
```

**Option B: Using Vercel Dashboard**
1. Go to https://vercel.com
2. Click "Add New Project"
3. Import your repository
4. Set root directory to `frontend`
5. Click "Deploy"

### Step 3: Access Your App

After deployment, your app will be available at:
- Landing: `https://your-app.vercel.app/`
- Auth: `https://your-app.vercel.app/auth`
- Login: `https://your-app.vercel.app/login`
- Register: `https://your-app.vercel.app/register`
- Dashboard: `https://your-app.vercel.app/dashboard`

## 🔧 Local Development

To test locally:
```bash
# Using Python
python -m http.server 5500

# Using Node.js
npx serve

# Using PHP
php -S localhost:5500
```

Then open: `http://localhost:5500/plantfox_landing.html`

## 📱 Mobile Experience

- Mobile devices (≤768px or touch) automatically redirect to splash screen
- Desktop users see the full landing page
- Splash screen auto-redirects to auth landing after 3 seconds

## 🔗 API Configuration

All API calls use the `CONFIG.API` variable from `config.js`:
- Login: `${CONFIG.API}/api/auth/login`
- Register: `${CONFIG.API}/api/auth/register`
- Dashboard: `${CONFIG.API}/api/*`

Make sure your backend is running and accessible through the cloudflare tunnel URL!
