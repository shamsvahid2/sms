# PRD — Quality & Compliance Dashboard  
نسخه: 1.0  
ماژول: Quality & Compliance (کیفیت و انطباق سازمانی)

---

# 1. مقدمه (Introduction)

ماژول **Quality & Compliance** بخش مهمی از سامانه هوانوردی است که بر فعالیت‌های مربوط به ممیزی (Audit)، نواقص کشف‌شده (Findings)، اقدامات اصلاحی و پیشگیرانه (CAPA)، و انطباق با قوانین (Compliance) تمرکز دارد.

به زبان ساده، این بخش کمک می‌کند سازمان مطمئن شود:

- کارها طبق قانون انجام می‌شود  
- استانداردهای EASA, ICAO و MOE رعایت شده  
- خطاها یا مشکلات شناسایی و اصلاح شده‌اند  
- کیفیت فرآیندها در سطح مطلوب قرار دارد  

این صفحه برای تیم کیفیت، مدیران و برنامه‌ریزان بسیار حیاتی است.

---

# 2. هدف (Purpose)

### اهداف اصلی داشبورد:

### 1. نمایش وضعیت ممیزی‌های داخلی و خارجی  
- ممیزی‌های انجام‌شده  
- ممیزی‌های برنامه‌ریزی‌شده  
- ممیزی‌های در انتظار پاسخ  

### 2. مدیریت Findings  
نشان‌دادن:

- نواقص باز  
- نواقص بسته  
- نواقص در آستانه Deadline  
- شدت Finding (Major/Minor/Observation)

### 3. مدیریت CAPA  
برای هر Finding اقدامات زیر لازم است:

- تعیین Root Cause  
- تعریف Corrective Action  
- تعریف Preventive Action  
- پیگیری زمان‌بندی و اثربخشی

### 4. پایش انطباق با MOE و Part-145  
مدیر کیفیت بتواند ببیند:

- کدام فرآیند با قانون انطباق ندارد  
- کدام فرآیند نیاز به اصلاح دارد  
- روند انطباق در طول زمان چگونه است

### 5. تولید گزارش مدیریتی و هشدارها  
برای تصمیم‌گیری سریع مدیران.

---

# 3. کاربران اصلی (User Types)

| نقش | نیاز |
|------|-----|
| **Quality Manager** | مدیریت Findings و CAPA، پیگیری ممیزی‌ها |
| **Compliance Manager** | بررسی انطباق با قوانین و MOE |
| **Auditors** | ثبت Findings در ممیزی‌ها |
| **Process Owners** | پاسخ‌دهی و رفع Findings |
| **Top Management** | مشاهده KPI کیفیت و سلامت سازمان |

---

# 4. داده‌هایی که باید نمایش داده شود (UI Data Requirements)

## 4.1. Audit Overview (نمای کلی ممیزی‌ها)

| فیلد | توضیح |
|------|--------|
| Audit Name | نام ممیزی |
| Type | Internal / External / Regulatory |
| Auditor | ممیز |
| Department | بخش مورد ممیزی |
| Planned Date | تاریخ برنامه‌ریزی |
| Status | Planned / Ongoing / Completed |
| Findings Count | تعداد Findings |
| CAPA Required | آیا نیاز به CAPA دارد؟ |

---

## 4.2. Findings Dashboard (داشبورد نواقص)

### برای هر Finding:

| فیلد | توضیح |
|------|--------|
| Finding Number | شماره نقص |
| Description | شرح مشکل |
| Category | Major / Minor / Observation |
| Process | فرایند مرتبط |
| Department | بخش مربوطه |
| Auditor | ثبت‌کننده |
| Detection Date | تاریخ کشف |
| Due Date | آخرین مهلت |
| Status | Open / In Progress / Closed |
| Severity Color | رنگ هشدار (قرمز/زرد/سبز) |
| Attachments | مستندات |

---

## 4.3. CAPA Dashboard (اقدامات اصلاحی و پیشگیرانه)

### برای هر CAPA:

| فیلد | توضیح |
|------|--------|
| CAPA ID | شماره اقدام |
| Root Cause | علت ریشه‌ای |
| Corrective Action | اقدام اصلاحی |
| Preventive Action | اقدام پیشگیرانه |
| Owner | مسئول |
| Due Date | تاریخ سررسید |
| Effectiveness Check | نتیجه اثربخشی |
| Status | Planned / In Progress / Implemented / Verified |
| Related Finding | ارتباط با Finding |

---

## 4.4. Compliance Tracker (ردیابی انطباق)

### شامل موارد زیر:

| داده | توضیح |
|-------|--------|
| Regulation Reference | قانون مرتبط (مثلاً MOE 2.4, Part-145.A.50) |
| Process | فرایند مرتبط |
| Compliance Status | Compliant / Non-Compliant |
| Last Audit | زمان آخرین بررسی |
| Required Action | نیاز به اصلاح؟ |
| Evidence | فایل یا پیوست |

---

## 4.5. Quality KPIs (شاخص‌های کیفیت)

صفحه باید KPIهای زیر را نمایش دهد:

- تعداد Findings باز  
- میانگین زمان بستن Finding  
- CAPA On-Time Completion %  
- Compliance Score (درصد انطباق)  
- تعداد ممیزی‌های انجام‌شده در ماه  
- تعداد Non-Conformities تکراری  

---

# 5. ورودی‌های کاربر (User Inputs)

## 5.1. ورودی‌های ممیزی (Audit Inputs)

| ورودی | کاربرد |
|--------|--------|
| Create Audit | ایجاد ممیزی جدید |
| Edit Audit | ویرایش اطلاعات ممیزی |
| Attach Reports | بارگذاری گزارش |
| Add Finding | ثبت نقص در ممیزی |

---

## 5.2. ورودی‌های مربوط به Findings

| ورودی | کاربرد |
|--------|--------|
| Update Status | تغییر وضعیت Finding |
| Add Attachment | بارگذاری عکس/سند |
| Assign Owner | تعیین مسئول رفع مشکل |
| Add Comment | اضافه کردن یادداشت |

---

## 5.3. ورودی‌های مربوط به CAPA

| ورودی | کاربرد |
|--------|--------|
| Create CAPA | ایجاد اقدام اصلاحی ~ پیشگیرانه |
| Add Root Cause | وارد کردن علت اصلی |
| Assign Owner | تعیین مسئول اقدام |
| Update Progress | تغییر وضعیت |
| Verify Effectiveness | تایید اثربخشی |

---

## 5.4. ورودی‌های مربوط به Compliance

| ورودی | کاربرد |
|--------|--------|
| Mark Compliant | تأیید انطباق |
| Mark Non-Compliant | ثبت عدم انطباق |
| Upload Evidence | بارگذاری مدرک |
| Assign Corrective Task | ایجاد کار اصلاحی |

---

## 5.5. ورودی‌های عمومی

| ورودی | کاربرد |
|--------|--------|
| Search | جستجو |
| Filter | فیلتر براساس وضعیت/بخش/Severity |
| Sort | مرتب‌سازی |
| Export | خروجی Excel/PDF |
| View Details | مشاهده جزئیات آیتم |

---

# پایان سند
