# PRD — Inventory & Tooling Dashboard  
نسخه: 1.0  
ماژول: Inventory & Tooling (انبار قطعات و مدیریت ابزار)

---

# 1. مقدمه (Introduction)

ماژول **Inventory & Tooling** یک بخش کلیدی در سیستم نگهداری هوانوردی است که وظیفه مدیریت:

- قطعات (Spare Parts)  
- ابزارهای ویژه (Special Tools)  
- ابزارهای کالیبراسیونی (Calibration Tools)  
- وضعیت انبار  
- ردیابی مصرف قطعات  
- کنترل عمر قطعات حساس (LLP / Life-Limited Parts)  

را بر عهده دارد.

این ماژول تضمین می‌کند که:

- قطعات موردنیاز برای عملیات تعمیر موجود باشند  
- ابزارهای موردنیاز برای اجرای کار در دسترس باشند  
- هیچ ابزار یا قطعه‌ای بدون اعتبار قانونی استفاده نشود  
- انبار همیشه وضعیت سالم و مطابق مقررات داشته باشد  

به زبان ساده:  
**بخش Inventory & Tooling کمک می‌کند بدانیم چه قطعات و ابزارهایی داریم، کجا هستند، آیا معتبر هستند و چه زمانی باید جایگزین شوند.**

---

# 2. هدف (Purpose)

### اهداف اصلی ماژول عبارت‌اند از:

### 1. مدیریت موجودی قطعات  
نمایش تعداد، محل نگهداری، وضعیت سرویس‌پذیری، و سوابق قطعات.

### 2. مدیریت ابزارها (Tools)  
اطمینان از اینکه ابزارهای ضروری:

- موجود  
- سالم  
- کالیبره  
- و قانونی هستند

### 3. جلوگیری از نصب قطعه بدون مدرک قانونی  
مثلاً قطعه‌ای که Form 1 معتبر ندارد نباید قابل انتخاب باشد.

### 4. ردیابی نصب/برداشت قطعات  
سوابق دقیق نصب و برداشتن باید ثبت شود.

### 5. مدیریت قطعات LLP  
قطعاتی که عمر محدود دارند باید به‌صورت هوشمند ردیابی شوند.

### 6. هشدار برای انقضا  
- انقضای ابزار کالیبراسیون  
- انقضای Shelf Life قطعه  
- کمبود موجودی  

---

# 3. کاربران اصلی (User Types)

| نقش | نیاز |
|------|-----|
| **Storekeeper (انباردار)** | مدیریت ورود و خروج قطعات و ابزار |
| **Maintenance Technician** | درخواست قطعه/ابزار برای WO |
| **Maintenance Engineer** | بررسی وضعیت LLP و قطعات بحرانی |
| **Production Planning** | سنجش موجودی برای برنامه تعمیرات |
| **Quality Manager** | بررسی اعتبار Form 1 و Calibration |
| **Procurement Team** | مشاهده اقلام کم‌موجودی |

---

# 4. داده‌هایی که باید نمایش داده شود (UI Data Requirements)

## 4.1. لیست قطعات (Inventory Items)

برای هر قطعه نمایش داده شود:

| فیلد | توضیح |
|------|--------|
| Part Number | شماره قطعه |
| Description | توضیح |
| Serial Number (در صورت وجود) | شماره سریال |
| Quantity | تعداد موجود |
| Location | محل نگهداری (Rack/Shelf/Bin) |
| Condition | Serviceable / Unserviceable / Repairable |
| Shelf Life Date | تاریخ انقضا (برای مواد و اقلام حساس) |
| LLP Remaining Life | عمر باقی‌مانده برای LLP |
| Form 1 Status | فعال / منقضی |
| Manufacturer | سازنده |
| Aircraft Compatibility | نوع هواپیما |

---

## 4.2. سوابق ورود/خروج (Stock Movements)

برای هر عمل:

| فیلد | توضیح |
|------|--------|
| Transaction Type | Issue / Return / Scrap / Receive |
| WO Number | مرتبط با کدام WO |
| Quantity | تعداد |
| Date | تاریخ |
| User | شخص انجام‌دهنده |
| Remarks | توضیحات |

---

## 4.3. قطعات LLP (Life-Limited Parts)

نمایش موارد زیر:

- Remaining Cycles  
- Remaining Hours  
- Remaining Days  
- Red/Yellow/Green Codes  
- Installation History  
- Expiry Forecast  

---

## 4.4. ابزارها (Tooling List)

برای هر ابزار نمایش داده شود:

| فیلد | توضیح |
|------|--------|
| Tool ID | شناسه ابزار |
| Description | توضیحات |
| Calibration Due Date | تاریخ سررسید کالیبراسیون |
| Condition | Serviceable / Unserviceable |
| Location | محل ابزار |
| Usage Logs | سوابق استفاده |
| Assigned to WO | آیا به WO لینک شده؟ |
| Certificate File | مدرک کالیبراسیون |

---

## 4.5. Tool Calibration Records

برای هر ابزار نمایش داده شود:

- Calibration Certificate  
- Calibration Provider  
- Calibration Date  
- Next Due Date  
- Attachments  

---

## 4.6. هشدارها و اعلان‌ها (Alerts)

باید شامل موارد زیر باشد:

- ابزارهای در آستانه انقضای کالیبراسیون  
- قطعات نزدیک به اتمام Shelf Life  
- LLP نزدیک به پایان عمر  
- قطعاتی که Form 1 معتبر ندارند  
- کمبود موجودی (Below Minimum Stock Level)  

---

# 5. ورودی‌های کاربر (User Inputs)

## 5.1. ورودی‌های مربوط به قطعه

| ورودی | کاربرد |
|--------|--------|
| Add Part | اضافه‌کردن قطعه جدید |
| Receive Shipment | ثبت ورود قطعه |
| Issue to WO | تحویل قطعه به WO |
| Return to Store | برگشت از WO |
| Update Location | تغییر محل |
| Attach Form 1 | بارگذاری گواهی |
| Scrap Part | خارج از رده‌کردن (Scrap) |

---

## 5.2. ورودی‌های مربوط به LLP

| ورودی | کاربرد |
|--------|--------|
| Update FH/FC | ثبت مصرف جدید |
| Mark as Expired | تغییر وضعیت پس از پایان عمر |
| Install on Aircraft | نصب |
| Remove from Aircraft | برداشتن |

---

## 5.3. ورودی‌های مربوط به ابزارها (Tooling)

| ورودی | کاربرد |
|--------|--------|
| Add Tool | اضافه‌کردن ابزار |
| Check-Out Tool | تحویل ابزار به تکنسین |
| Check-In Tool | برگشت ابزار |
| Update Calibration | ثبت اطلاعات کالیبراسیون |
| Upload Certificate | بارگذاری مدرک |
| Mark as Unserviceable | تغییر وضعیت ابزار |

---

## 5.4. ورودی‌های انبار (Stock Movements)

| ورودی | کاربرد |
|--------|--------|
| Log Transaction | ثبت ورود/خروج |
| Assign WO | ارتباط دادن قطعه/ابزار به WO |
| Add Remark | یادداشت |

---

## 5.5. ورودی‌های عمومی

| ورودی | کاربرد |
|--------|--------|
| Search | جستجوی قطعه/ابزار |
| Filter | سرویس‌پذیری، انقضا، LLP، وضعیت انبار |
| Sort | براساس تاریخ، Part No، انقضا |
| Export | خروجی اکسل یا PDF |
| View Details | مشاهده جزئیات |

---

# پایان سند
