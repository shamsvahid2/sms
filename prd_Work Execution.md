# PRD — Work Execution Dashboard  
نسخه: 1.0  
ماژول: Work Execution (اجرای تعمیرات و مدیریت WO/Job Cards)

---

# 1. مقدمه (Introduction)

ماژول **Work Execution** بخشی از سامانه نگهداری هوانوردی است که مسیر کامل اجرای یک کار تعمیراتی را مدیریت می‌کند.  
این ماژول شامل Work Orderها (WO) و Job Cardهای داخل آنهاست و به کاربران اجازه می‌دهد مراحل تعمیرات را به‌صورت گام‌به‌گام انجام دهند، ثبت کنند و امضا بزنند.

این صفحه اصلی‌ترین ابزار برای **Maintenance Technician** و **Inspector** است و به زبان ساده نشان می‌دهد:  
- چه کارهایی باید انجام شود  
- چه کسی مسئول انجام هر مرحله است  
- کدام مراحل تکمیل شده  
- چه زمانی WO قابل بستن است  

---

# 2. هدف (Purpose)

### هدف این داشبورد:
1. **نمایش لیست Work Orders**  
   شامل وضعیت، هواپیما، Job Cardها و درصد پیشرفت.

2. **ارائه گردش‌کار مرحله‌به‌مرحله**  
   تکنسین بتواند Job Card را باز کرده و هر Step را تکمیل کند.

3. **مدیریت امضاهای فنی**  
   امضاهای Performer (مجری)، Inspector و Release (CRS) قابل ثبت باشد.

4. **نمایش نیازمندی‌های قطعات و ابزار**  
   سیستم مشخص کند چه قطعاتی مصرف شده یا چه ابزاری نیاز هست.

5. **ثبت کامل تاریخچه تعمیرات**  
   پس از تکمیل، WO باید سابقه عملیاتی هواپیما را به‌روزرسانی کند.

---

# 3. کاربران اصلی (User Types)

| نقش | نیاز اصلی |
|------|-----------|
| **Maintenance Technician** | انجام مراحل Job Card، ثبت Step، مصرف قطعه |
| **Inspector / Certifying Staff** | بررسی Stepها و ثبت امضای بازرسی |
| **Maintenance Planner** | بررسی پیشرفت اجرای WO |
| **Quality Auditor** | دیدن رکوردها و امضاها |
| **CAMO Staff** | کنترل تطبیق با AMP و ثبت تاییدهای نهایی |

---

# 4. داده‌هایی که باید نمایش داده شود (UI Data Requirements)

## 4.1. لیست Work Orders  
هر سطر باید شامل فیلدهای زیر باشد:

| فیلد | توضیح |
|------|--------|
| WO Number | شماره WO |
| Aircraft | شماره هواپیما |
| Status | Open / In Progress / Waiting for Inspection / Closed |
| Source | AMP / Defect / AD/SB / Unscheduled |
| Progress | درصد پیشرفت |
| Open Date | تاریخ باز شدن |
| Target Close Date | تاریخ هدف بسته‌شدن |
| Assigned Technicians | تکنسین‌های مسئول |
| Criticality | میزان اهمیت تعمیر |

---

## 4.2. جزئیات Work Order (WO Detail View)

| بخش | نمایش |
|------|--------|
| Summary | اطلاعات هواپیما، دلیل باز شدن WO |
| Job Cards | لیست کارت‌ها درون WO |
| Required Tools | ابزار موردنیاز |
| Required Parts | قطعات موردنیاز |
| Consumed Parts | قطعات مصرف‌شده |
| Signatures | Performer, Inspector, Release |
| Attachments | عکس، فایل، گزارش تست، Form 1 |

---

## 4.3. Job Card Data Requirements

### برای هر Job Card:

| فیلد | توضیح |
|------|--------|
| Job Card Code | کد کارت |
| Description | شرح کار |
| Steps | مراحل گام‌به‌گام |
| Required Skills | مهارت لازم (مثلاً B1, B2) |
| Required Tools | لیست ابزار |
| Estimated Time | زمان تخمینی |
| Signatures | امضاهای لازم |

---

## 4.4. Step Data Requirements

### برای هر Step از Job Card:

| فیلد | توضیح |
|------|--------|
| Step Number | شماره مرحله |
| Description | شرح مرحله |
| Status | Done / In Progress / Pending |
| Started At | زمان شروع |
| Completed At | زمان پایان |
| Performer Signature | امضای انجام‌دهنده |
| Inspector Signature | امضای بازرس (در صورت نیاز) |

---

## 4.5. بخش Consumption (مصرف قطعه)

برای هر WO باید نمایش داده شود:

| فیلد | توضیح |
|------|--------|
| Component | قطعه مصرف‌شده |
| Part No | شماره قطعه |
| Serial No | سریال قطعه |
| Form 1 | لینک گواهی |
| Installed On | تاریخ نصب |
| Removed From | (در صورت تعویض قطعه) |
| Batch/Lot | اطلاعات انبار |

---

# 5. ورودی‌های کاربر (User Inputs)

## 5.1. ورودی‌های مربوط به WO

| ورودی | کاربرد |
|--------|--------|
| انتخاب WO | باز کردن جزئیات کار |
| تغییر وضعیت | In Progress / Waiting for Inspection |
| افزودن قطعه مصرفی | انتخاب از انبار |
| ثبت ابزار استفاده‌شده | انتخاب از لیست ابزار |
| ضمیمه اضافه‌کردن | آپلود عکس یا PDF |
| ثبت امضای Release | تایید نهایی CRS |

---

## 5.2. ورودی‌های مربوط به Job Card

| ورودی | کاربرد |
|--------|--------|
| باز کردن Job Card | ورود به مراحل |
| شروع Job | Start Job |
| تکمیل Job | Complete Job |
| ثبت امضای Performer | امضای انجام‌دهنده |
| ثبت امضای Inspector | امضای بازرس |
| ثبت یادداشت | Notes/Comments |

---

## 5.3. ورودی‌های مربوط به هر Step

| ورودی | کاربرد |
|--------|--------|
| Mark as Done | تکمیل مرحله |
| Mark as In Progress | شروع مرحله |
| Upload Photo | ثبت عکس از کار انجام‌شده |
| Add Measurement | ثبت اندازه‌گیری (مثلاً Torque) |
| Signature | امضای کاربر |

---

# پایان سند
