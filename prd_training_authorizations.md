# PRD — Training & Authorizations Dashboard  
نسخه: 1.0  
ماژول: Training & Authorizations (آموزش‌ها و مجوزهای پرسنل)

---

# 1. مقدمه (Introduction)

ماژول **Training & Authorizations** بخشی از سامانه نگهداری هوانوردی است که مسئولیت مدیریت آموزش‌ها، سوابق دوره‌های فنی، و مجوزهای کاری پرسنل را بر عهده دارد.  
در یک سازمان هوانوردی، هر تکنسین باید دوره‌های خاصی مثل:

- Human Factors  
- EWIS  
- Fuel Tank Safety (FTS)  
- Type Training  
- Continuation Training  

را گذرانده باشد و مجوزهای مرتبط با نقش خود را نیز داشته باشد.

این داشبورد به زبان ساده کمک می‌کند بفهمیم:

- چه کسی چه دوره‌ای را گذرانده؟  
- چه مجوزهایی معتبر هستند؟  
- چه کسانی آموزش یا مجوز در حال انقضا دارند؟  
- آیا فرد اجازه امضا و کار روی هواپیمای خاص را دارد یا خیر؟  

---

# 2. هدف (Purpose)

### هدف این داشبورد شامل موارد زیر است:

### 1. نمایش کامل وضعیت آموزشی پرسنل  
هر فرد تمام دوره‌های گذرانده، نمرات، تاریخ اعتبار و گپ‌های آموزشی را می‌بیند.

### 2. پایش مجوزها (Company Authorizations)  
مثل:  
- A Category Auth  
- B1/B2 Type Authorization  
- Engine Run Permit  
- CRS Release Authority  

### 3. جلوگیری از انجام کار توسط افراد بدون صلاحیت  
چنانچه پرسنل آموزش یا مجوز معتبر نداشته باشند:

- سیستم نباید اجازه امضا بدهد  
- باید هشدار بدهد که فرد صلاحیت ندارد  

### 4. کمک به برنامه‌ریزی آموزش‌های آینده  
داشبورد باید لیست افراد با آموزش‌های نزدیک به انقضا را نشان دهد.

---

# 3. کاربران اصلی (User Types)

| نقش | نیاز |
|------|------|
| **Training Manager** | ثبت دوره، ایجاد کلاس، برنامه‌ریزی آموزش |
| **Quality Manager** | کنترل Compliance پرسنل |
| **Maintenance Engineer** | مشاهده وضعیت دوره‌ها و مجوزهای خود |
| **Certifying Staff (B1/B2/C)** | بررسی صلاحیت امضا |
| **HR / Admin** | مدیریت اطلاعات پرسنل |

---

# 4. داده‌هایی که باید نمایش داده شود (UI Data Requirements)

## 4.1. لیست پرسنل
برای هر فرد باید موارد زیر نمایش داده شود:

| فیلد | توضیح |
|------|--------|
| نام و نام خانوادگی | شناسه فرد |
| کد پرسنلی | شماره داخلی شرکت |
| نقش/سمت | Technician, Engineer, Inspector |
| سطح مهارت (License Category) | B1/B2/C |
| وضعیت آموزش‌ها | درصد کامل‌شدن |
| وضعیت مجوزها | Valid / Expiring / Expired |
| هشدارها | Items close to expiry |

---

## 4.2. Training Records (سوابق آموزشی)

### برای هر فرد نمایش داده شود:
| فیلد | توضیح |
|------|--------|
| Course Name | نام دوره |
| Course Type | HF/EWIS/FTS/Type/Continuation |
| Provider | برگزارکننده |
| Completion Date | تاریخ انجام |
| Valid Until | تاریخ پایان اعتبار |
| Certificate File | فایل مدرک |
| Status | Valid / Expiring (<=30 days) / Expired |

---

## 4.3. Company Authorizations (مجوزهای شرکت)

### برای هر فرد:

| فیلد | توضیح |
|------|--------|
| Authorization Code | کد مجوز |
| Description | شرح |
| Scope | دامنه کار (مثلاً A320 B1) |
| Issued Date | تاریخ صدور |
| Expiry Date | تاریخ انقضا |
| Status | Valid / Expiring / Expired |
| Signoff Permission | چه چیزی اجازه امضا دارد؟ |
| Attachment | فایل مجوز |

---

## 4.4. Training Gap Panel (کمبودهای آموزشی)

این بخش باید نمایش دهد:

- دوره‌های الزامی که فرد هنوز نگذرانده  
- دوره‌هایی که کمتر از ۳۰ روز تا انقضا دارند  
- درصد کلی Compliance تیم فنی  
- نمودار Gauge برای وضعیت کلی آموزش سازمان  

---

## 4.5. Upcoming Expiries (آموزش‌های نزدیک انقضا)

جدولی شامل:

| ستون | توضیح |
|-------|--------|
| Person | فرد مربوطه |
| Course | دوره در حال انقضا |
| Days Remaining | تعداد روز باقی‌مانده |
| Status | Expiring / Urgent |
| Action | ایجاد Reminder |

---

## 4.6. نمودارها و ویژوال‌ها

- **Radar Chart**: مقایسه وضعیت آموزشی تیم‌ها  
- **Bar Chart**: تعداد دوره‌های Expiring در ماه آینده  
- **Pie Chart**: توزیع مجوزهای معتبر/باطل‌شده  
- **Timeline**: تاریخ‌های انقضا  

---

# 5. ورودی‌های کاربر (User Inputs)

## 5.1. ورودی‌های Training Manager

| ورودی | کاربرد |
|--------|--------|
| Add Training Record | ثبت دوره جدید |
| Edit Training | ویرایش تاریخ‌ها/مدرک |
| Upload Certificate | اضافه‌کردن فایل PDF/IMG |
| Mark as Completed | تکمیل دوره |
| Assign Person to Course | اضافه‌کردن فرد به کلاس آموزشی |

---

## 5.2. ورودی‌های Authorization Manager

| ورودی | کاربرد |
|--------|--------|
| Issue Authorization | صدور مجوز |
| Renew Authorization | تمدید |
| Upload Attachment | بارگذاری فایل مجوز |
| Change Status | Valid/Expired |

---

## 5.3. ورودی‌های عمومی کاربران دیگر

| ورودی | کاربرد |
|--------|--------|
| Search | جستجوی فرد |
| Filter | براساس نقش، وضعیت، دوره |
| Sort | براساس تاریخ انقضا یا تکمیل |
| View Profile | مشاهده جزئیات آموزش یک فرد |
| Download Certificate | دانلود مدرک |

---

# پایان سند
