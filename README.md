# HabibWeb — Premium Glassmorphic Web Design & Development Portfolio & CMS

A complete, production-ready, international digital agency portfolio website built for **Md. Habibur Rahman** (Web Designer & Full Stack Web Developer).

Built with **Laravel 12 / MVC Architecture**, **Bootstrap 5**, **MySQL**, **Vanilla JavaScript**, **GSAP Animations**, **Swiper.js**, and a custom **Glassmorphism Visual System**.

---

## 🌟 Key Features

### 1. Public Portfolio & Agency Frontend
- **Glassmorphism Visual System**: Transparent glass cards, `backdrop-filter: blur(16px)`, floating ambient gradient blobs, soft glowing borders, dark/light theme switcher.
- **Interactive Motion System**: Custom mouse cursor (dot + outer ring follower + viewport spotlight glow), 3D card tilt on hover, magnetic buttons, scroll reveal animations, floating particle canvas.
- **Hero Section**: Animated statistics counters (4+ Years Experience, 100+ Projects, 50+ Happy Clients, 24/7 Support), glass floating UI panels, primary & secondary CTAs.
- **Services Showcase**: 12 custom service cards (Website Design, Web Development, WordPress, E-commerce, Landing Page, Business Website, Corporate Website, Portfolio, Laravel Development, Redesign, SEO, Speed Optimization) with feature checklists.
- **Portfolio & Case Studies**: AJAX category filter tabs (All, Business, Corporate, E-commerce, WordPress, Landing Page, Portfolio, Custom Development), interactive case study modal & dedicated page, live website links.
- **Work Process Timeline**: 7-step visual workflow (01 Discovery → 07 Support).
- **Testimonials Slider**: Swiper.js client review carousel with star ratings and client logos.
- **Pricing Packages**: 4 transparent investment tiers with popular badge highlights.
- **Blog System**: Dynamic articles with categories, tags, search, and reading view.
- **Contact & Lead Intake**: AJAX lead form with real-time feedback, service dropdown, budget picker, and floating direct WhatsApp chat generator.

### 2. Admin CMS Panel (`/admin`)
- **Glassmorphic Admin UI**: Responsive glass sidebar with quick navigation.
- **Analytics Dashboard**: Real-time counter metrics for Projects, Services, Articles, Testimonials, Leads, Unread Messages, and Total Platform Views.
- **Lead Pipeline Manager**: Filter leads by status (`New`, `Contacted`, `In Discussion`, `Converted`, `Lost`), quick WhatsApp reply links, status updates, search & deletion.
- **Website Settings Manager**: Change website title, logo, email, phone, WhatsApp number, address, social media links, and theme colors without touching code.
- **Hero & About Managers**: Update hero headings, CTAs, counters, bio, skill tags, and profile photo.
- **Content CRUD Managers**: Manage Services, Portfolio Projects & Case Studies, Testimonials, Pricing Packages, Blog Articles, and Custom Pages.
- **Media Library**: Upload and manage image assets (JPG, PNG, WEBP, SVG) with alt tags.
- **SEO Manager**: Meta Title, Description, Keywords, Canonical URLs, OpenGraph image, Google Analytics ID, and Search Console verification.

---

## 🔑 Admin Login Credentials

- **Admin URL**: `http://localhost/Habibweb/public/admin/login`
- **Default Email**: `admin@habibweb.com`
- **Default Password**: `admin123`

*Note: You can change the admin password anytime from the Admin Panel or `.env` configuration file.*

---

## 🚀 Local Installation Guide (XAMPP & Apache)

### Step 1: Create Database in XAMPP
1. Open XAMPP Control Panel and start **Apache** and **MySQL**.
2. Open your web browser and go to `http://localhost/phpmyadmin`.
3. Click **New** and create a database named `habibweb_db` with `utf8mb4_unicode_ci` collation.

### Step 2: Run Setup Commands
Open Command Prompt or PowerShell inside `c:\xampp\htdocs\Habibweb` and run:

```bash
# 1. Install Composer dependencies
composer install

# 2. Generate application key
php artisan key:generate

# 3. Create database tables and load demo content
php artisan migrate --force
php artisan db:seed --force

# 4. Create storage link for uploaded images
php artisan storage:link
```

*(Alternatively, if you prefer importing SQL manually into phpMyAdmin, click **Import** in phpMyAdmin and select `database/schema.sql`)*

### Step 3: Access the Website
- **Public Website**: `http://localhost/Habibweb/public/`
- **Admin Panel**: `http://localhost/Habibweb/public/admin/login`

*(Or run `php artisan serve` and open `http://127.0.0.1:8000`)*

---

## 🌐 cPanel Deployment Guide

When deploying to a live shared hosting server or cPanel:

1. **Upload Files**: Upload the entire project to your cPanel directory (e.g. `public_html/habibweb` or main root).
2. **Configure Public Root**: Point your domain document root to the `public` folder of the project.
3. **Import Database**: Create a MySQL database in cPanel MySQL Database Wizard. Go to phpMyAdmin and import `database/schema.sql` (or run `php artisan db:seed`).
4. **Update `.env`**:
   ```ini
   APP_ENV=production
   APP_DEBUG=false
   APP_URL=https://yourdomain.com
   DB_HOST=127.0.0.1
   DB_DATABASE=cpanel_user_habibweb
   DB_USERNAME=cpanel_user_dbuser
   DB_PASSWORD=your_secure_password
   ```
5. **Optimize Cache**:
   ```bash
   php artisan config:cache
   php artisan route:cache
   php artisan view:cache
   ```

---

## 📁 Project Structure

```
Habibweb/
├── app/
│   ├── Http/
│   │   ├── Controllers/
│   │   │   ├── FrontendController.php
│   │   │   └── Admin/
│   │   │       ├── AuthController.php
│   │   │       ├── DashboardController.php
│   │   │       ├── LeadController.php
│   │   │       ├── ServiceController.php
│   │   │       ├── PortfolioController.php
│   │   │       └── ...
│   │   └── Middleware/
│   │       └── AdminAuth.php
│   └── Models/
├── bootstrap/
├── config/
├── database/
│   ├── migrations/
│   ├── seeders/
│   └── schema.sql
├── public/
│   ├── assets/
│   │   ├── css/style.css & admin.css
│   │   ├── js/main.js & admin.js
│   │   └── images/
│   ├── uploads/
│   └── index.php
├── resources/
│   └── views/
│       ├── frontend/
│       ├── admin/
│       └── errors/
├── routes/
│   └── web.php
├── .env
├── .env.example
├── artisan
├── composer.json
└── README.md
```

---

## 🛡️ Security & Performance Standards

- **CSRF Protection**: CSRF tokens enforced on all contact forms, AJAX endpoints, and admin actions.
- **SQL Injection Prevention**: Eloquent ORM prepared statements across all database queries.
- **XSS Protection**: HTML escaping applied on all user input rendering.
- **Speed Target**: WebP images, minified assets, and browser caching designed for 90+ Lighthouse performance scores.
