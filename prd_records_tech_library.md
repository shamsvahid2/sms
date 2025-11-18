# PRD — Records & Tech Library Dashboard  
نسخه: 1.0  
ماژول: Records & Technical Library (سوابق فنی و کتابخانه مستندات)

---

# 1. مقدمه (Introduction)

ماژول **Records & Tech Library** فضایی برای مدیریت، نگهداری و جستجوی تمام اسناد فنی، عملیاتی و قانونی مرتبط با هواپیما و عملیات نگهداری است.  
در سازمان‌های هوانوردی، مدارک بسیار مهمی وجود دارد مانند:

- AMM (Aircraft Maintenance Manual)  
- CMM (Component Maintenance Manual)  
- SRM (Structural Repair Manual)  
- IPC (Illustrated Parts Catalog)  
- MPL / MEL / CDL  
- Tech Logs  
- Form 1 و سایر تأییدیه‌ها  
- گزارش‌های WO و Job Cards  
- سوابق نصب و برداشتن قطعات (Install/Removal Records)  

این داشبورد کمک می‌کند همه این مدارک به‌صورت دیجیتال، قابل جستجو و ساختاریافته در یک محل جمع‌آوری شوند تا تیم نگهداری بتواند سریع به آنها دسترسی داشته باشد.

---

# 2. هدف (Purpose)

### اهداف اصلی این ماژول عبارت‌اند از:

### 1. فراهم‌کردن دسترسی سریع به اسناد حیاتی  
تکنسین یا مهندس باید بتواند هنگام اجرای تعمیرات،  
**سریعا** بخش مربوطه از AMM یا CMM را پیدا کند.

### 2. مدیریت سوابق فنی (Records Management)  
تمام کارهای انجام‌شده روی هر هواپیما باید دارای سابقه قابل ردیابی باشد، مانند:

- Work Orders  
- Job Cards  
- CRS Releases  
- Defect Rectifications  
- Part Installations  

### 3. جلوگیری از استفاده سند منسوخ‌شده  
نسخه‌های جدید اسناد OEM باید جایگزین نسخه‌های قدیمی شوند.

### 4. ایجاد لینک بین اسناد و عملیات  
مثلاً WO باید امکان لینک شدن به پاراگراف مربوطه در AMM داشته باشد.

### 5. مدیریت دسترسی و امنیت  
هر فایل باید با سطح دسترسی مناسب محافظت شود.

---

# 3. کاربران اصلی (User Types)

| نقش | نیاز |
|------|-----|
| **Maintenance Technician** | دسترسی سریع به AMM/CMM در حین کار |
| **Maintenance Engineer** | بررسی سوابق تعمیرات و نصب قطعات |
| **Quality Manager** | بررسی نسخه اسناد و انطباق با MOE |
| **CAMO Staff** | ارزیابی تاریخچه فنی هواپیما |
| **Library Manager** | مدیریت نسخه‌های اسناد و بارگذاری فایل‌ها |
| **Auditors** | بررسی ردیابی و سوابق نگهداری |

---

# 4. داده‌هایی که باید نمایش داده شود (UI Data Requirements)

## 4.1. Document Library (کتابخانه اسناد)
لیست اسناد باید شامل فیلدهای زیر باشد:

| فیلد | توضیح |
|------|--------|
| Document Title | عنوان سند (AMM, CMM, IPC…) |
| Document Type | نوع: Manual / Procedure / Record / Certificate |
| Aircraft Type | مدل مربوطه |
| Chapter/Section | فصل و بخش |
| Version | نسخه فعلی |
| Effective Date | تاریخ اعمال نسخه |
| Expiry Date | تاریخ انقضا (در صورت وجود) |
| Status | Active / Superseded |
| File Attachments | فایل PDF یا ZIP |
| Linked Systems | ارتباط با هواپیماها یا قطعات |

---

## 4.2. Technical Records (سوابق فنی هواپیما)

### برای هر هواپیما نمایش داده شود:

| داده | توضیح |
|------|--------|
| WO History | لیست کامل Work Orderها |
| Job Card History | مراحل تعمیراتی انجام‌شده |
| CRS Records | گواهی‌های Release to Service |
| Component Change Logs | تاریخچه نصب/برداشت |
| Defect Records | گزارش‌های رفع ایراد |
| Flight/Technical Logbook | لاگ‌های روزانه |

---

## 4.3. Document Viewer

امکاناتی که باید نمایش داده شود:

- نمایش PDF داخل سیستم  
- Zoom / Search / Go to page  
- Highlighting (اختیاری)  
- نمایش Metadata سند  
- امکان نمایش چند بخش کنار هم (Split View)  

---

## 4.4. Smart Search

جستجو باید شامل:

- جستجوی متن کامل (Full-text search)  
- جستجو براساس Chapter / ATA Code  
- فیلتر براساس Aircraft Type  
- جستجو در میان WO، Job Card، AMM و CMM  

نمونه جستجو:
