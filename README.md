# Civil Master Pro v4.0

اپلیکیشن تخصصی محاسبات مهندسی عمران — آفلاین، دو زبانه (دری/فارسی + انگلیسی)

> **Comprehensive offline civil engineering calculation suite for engineers.**
> Bilingual (Dari/Persian + English) with full RTL support. Built as a Progressive Web App (PWA), installable on Android via TWA (Trusted Web Activity).

---

## ابزارها / Features

- **تست پروکتور** — Proctor Compaction Test (MDD/OMC)
- **FDT** — Field Density Test
- **CBR** — California Bearing Ratio calculator
- **برآورد کانکریت** — Concrete Estimator
- **برآورد خشت و مصاله** — Brick & Mortar Estimator
- **ماشین حساب** — Standard Calculator
- **تبدیل واحدات** — Unit Converter (length, area, weight, volume, pressure)
- **تبدیل تاریخ** — Date Converter (Gregorian ↔ Solar Hijri)
- **آب تراز** — Bubble Spirit Level (uses device sensors)
- **خط‌کش** — Digital Ruler
- **دایره‌المعارف مهندسی** — Engineering Encyclopedia (offline)
- **درباره** — About / Contact

250+ engineering constants, 765 formulas, 200+ unit conversions.

---

## 📁 ساختار پروژه / Project Structure

```
.
├── www/                          # PWA web assets (deployed to GitHub Pages)
│   ├── index.html                # Main app (React + Tailwind + Chart.js + Dexie)
│   ├── manifest.json             # PWA manifest (TWA-ready)
│   ├── sw.js                     # Service Worker (offline cache)
│   └── icons/
│       ├── icon-192.png
│       ├── icon-512.png
│       └── icon-512-maskable.png
├── twa-manifest.json             # TWA config for Bubblewrap (Android wrapper)
├── .github/
│   └── workflows/
│       └── build-apk.yml         # GitHub Actions: auto-build signed APK
├── .gitignore
└── README.md
```

---

## 🚀 راه‌اندازی / Setup

### مرحله ۱: Push به GitHub

```bash
cd "C:\Users\SC\Documents\Compaction test App"
git init
git add .
git commit -m "Civil Master Pro v4.0"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/civil-master-pro.git
git push -u origin main
```

### مرحله ۲: فعال‌سازی GitHub Pages

1. توی Repo → **Settings** → **Pages**
2. **Source**: `Deploy from a branch`
3. **Branch**: `main` / **Folder**: `/www`  ← **مهم: www رو انتخاب کن**
4. **Save**
5. ۱-۲ دقیقه صبر کن
6. URL: `https://YOUR_USERNAME.github.io/civil-master-pro/`

### مرحله ۳: آپدیت `twa-manifest.json`

توی فایل `twa-manifest.json`، `YOUR_GITHUB_USERNAME` رو با username واقعیت عوض کن:

```json
"host": "YOUR_GITHUB_USERNAME.github.io"   ← اینجا
```

Commit و push کن.

---

## 📱 ساخت APK اندروید (۲ روش)

### روش ۱: خودکار با GitHub Actions ⭐ پیشنهادی

بعد از push، توی GitHub:

1. **Actions** tab → **Build Android APK** (سمت چپ)
2. **Run workflow** (سمت راست)
3. ورودی‌ها:
   - `github_username`: نام کاربریت
   - `repo_name`: `civil-master-pro` (پیش‌فرض)
   - `build_type`: `release` (پیش‌فرض)
4. **Run** بزن
5. ۵-۱۰ دقیقه صبر کن (بار اول طولانی‌تره)
6. همین‌جا پایین → **Artifacts** → **civil-master-pro-apk** دانلود کن
7. فایل `.apk` رو روی گوشی Android نصب کن

### روش ۲: دستی با PWABuilder.com

1. URL GitHub Pages رو باز کن: `https://YOUR_USERNAME.github.io/civil-master-pro/`
2. برو https://www.pwabuilder.com
3. URL رو وارد کن
4. **Package For Stores** → **Android**
5. `.apk` و `.aab` رو دانلود کن

---

## 🧪 تست محلی / Local Test

برای تست PWA قبل از deploy:

```bash
# با Python
cd www
python -m http.server 8000

# یا با Node.js
npx serve www

# یا با PHP
cd www && php -S localhost:8000
```

بعد برو `http://localhost:8000`.

---

## 🔧 تنظیمات مهم / Important Settings

### Package ID (Android)
`com.yadgari.civilmasterpro` — اگه میخوای عوض کنی، باید در:
- `twa-manifest.json` (`packageId`)
- GitHub Actions workflow (`--packageId=...`)
هر دو رو با هم عوض کنی.

### Theme color
`#fbbf24` (طلایی) — هماهنگ با `index.html` و `manifest.json`

### App version
`4.0.0` (code: 40) — توی `twa-manifest.json`. هر بار release جدید، این رو زیاد کن.

---

## تکنالوژی / Tech Stack

- **Frontend**: React 18 (UMD), Tailwind CSS, Chart.js, Dexie (IndexedDB)
- **Icons**: FontAwesome 6
- **Font**: Vazirmatn (Persian/Dari)
- **PWA**: Service Worker + Web App Manifest
- **Android**: TWA (Trusted Web Activity) via Bubblewrap
- **CI/CD**: GitHub Actions

---

## سازنده / Author

**انجنیر احمد فیروز یادگاری** — Eng. Ahmad Feroz Yadgari
📞 0789215451

---

## مجوز / License

این اپلیکیشن به شکل آزمایشی می‌باشد و جهت جمع‌آوری نظرات و پیشنهادات منتشر شده است.
This is a trial version for feedback and testing purposes.
