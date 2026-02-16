<div dir="rtl">

# ابزار بررسی کیفیت و محدودیت اینترنت ایران  
**IRAN Internet Quality Tester** (نسخه وب)

</div>

<div dir="ltr" align="center">

[![GitHub license](https://img.shields.io/github/license/saeed9400/IRAN_Internet_Quality?style=flat-square)](https://github.com/saeed9400/IRAN_Internet_Quality/blob/main/LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/saeed9400/IRAN_Internet_Quality?style=flat-square)](https://github.com/saeed9400/IRAN_Internet_Quality/stargazers)
[![GitHub issues](https://img.shields.io/github/issues/saeed9400/IRAN_Internet_Quality?style=flat-square)](https://github.com/saeed9400/IRAN_Internet_Quality/issues)

</div>

### لینک‌های مستقیم استفاده (بدون نیاز به نصب)

| نسخه              | توضیحات                              | لینک مستقیم                                                                 |
|:-------------------:|:--------------------------------------:|-----------------------------------------------------------------------------:|
| نسخه ۱ (اصلی)     | تست دانلود واقعی + مسیر IPv4/IPv6   | [https://saeed9400.github.io/IRAN_Internet_Quality/](https://saeed9400.github.io/IRAN_Internet_Quality/)     |
| نسخه ۲ (پیشرفته) | تست جامع + پینگ + QUIC + DoH + WebRTC + DNS Hijack + اتصال عمومی | [https://saeed9400.github.io/IRAN_Internet_Quality/v2](https://saeed9400.github.io/IRAN_Internet_Quality/v2) |

---

### هدف پروژه

این ابزار **بدون نیاز به نصب** و فقط با باز کردن صفحه در مرورگر، به شما کمک می‌کند بفهمید:

- آیا مسیر دانلود شما **واقعاً باز** است یا فقط به‌خاطر CORS مرورگر بلاک به نظر می‌رسد؟
- آیا **DNS Hijacking** (دستکاری DNS) در سطح ISP شما رخ می‌دهد؟
- سرعت تقریبی پینگ به سرورهای بین‌المللی چقدر است؟
- آیا پروتکل‌های مدرن (**QUIC / HTTP/3**، **DNS over HTTPS**، **WebRTC**) کار می‌کنند؟
- IPv6 شما فعال است یا خیر؟
- اتصال عمومی به CDNها و سرورهای معروف (Google, Cloudflare, GitHub و ...) چگونه است؟

این ابزار به‌خصوص برای کاربران ایرانی که با محدودیت‌ها و فیلترینگ پویا مواجه هستند بسیار کاربردی است.

---

### تفاوت نسخه ۱ و نسخه ۲

| ویژگی                               | نسخه ۱ (اصلی) | نسخه ۲ (پیشرفته) |
|--------------------------------------|----------------|---------------------|
| دانلود واقعی فایل (چند منبع)       | ✓              | ✓                   |
| نمایش IP دیده‌شده (v4 + v6)         | ✓              | ✓                   |
| خلاصه نهایی کیفیت اینترنت          | ✓              | ✓                   |
| لینک دستی در صورت بلاک CORS         | ✓              | ✓                   |
| تست پینگ / Jitter به چند سرور       | —              | ✓                   |
| تست DNS Hijack (شناسایی IPهای مشکوک) | —              | ✓                   |
| تست پشتیبانی QUIC / HTTP/3          | —              | ✓                   |
| تست پشتیبانی DNS over HTTPS (DoH)   | —              | ✓                   |
| تست WebRTC (STUN)                    | —              | ✓                   |
| تست اتصال عمومی / CDN / IP          | —              | ✓                   |
| استفاده از پراکسی در صورت بلاک CORS | —              | ✓ (allorigins)      |
| تعداد کل تست‌ها                     | ~۶–۸           | ~۱۲–۱۶              |

→ **پیشنهاد**: اگر فقط می‌خواهید سریع بدانید دانلود باز است یا نه → **نسخه ۱**  
→ اگر می‌خواهید **تحلیل جامع‌تری** از وضعیت اینترنت خود داشته باشید → **نسخه ۲**

---

### نحوه کارکرد (Technical Overview)

- **نسخه ۱**  
  عمدتاً بر پایه دانلود واقعی فایل‌های کوچک تا متوسط از منابع معتبر (GitHub, jsDelivr, unpkg, OpenWrt, SourceForge و ...) کار می‌کند.  
  اگر fetch به‌خاطر CORS بلاک شود → لینک دستی نمایش داده می‌شود.

- **نسخه ۲**  
  علاوه بر دانلودها، تست‌های زیر را هم انجام می‌دهد:
  - چندین درخواست no-cors برای تخمین پینگ و جتر
  - درخواست DoH به dns.google برای بررسی دستکاری DNS
  - بررسی nextHopProtocol برای تشخیص QUIC
  - ایجاد RTCPeerConnection برای تست WebRTC
  - تست اتصال به چند CDN و API معروف

---

### چطور به پروژه کمک کنیم؟

هر نوع کمکی خوشحال‌کننده است:

- گزارش باگ و پیشنهاد بهبود
- اضافه کردن منبع دانلود / تست جدید
- ترجمه به زبان‌های دیگر
- بهبود ظاهر و تجربه کاربری (UI/UX)
- اضافه کردن تست‌های جدید (مثلاً تست MTU، WebSocket پایداری، ...)

.

---

### توسعه‌دهنده

- **saeed9400**  
  GitHub: https://github.com/saeed9400  
  پروژه مرتبط دیگر: [IRAN_Passwall2](https://github.com/saeed9400/IRAN_Passwall2)

---

<div dir="rtl" align="center">

با تشکر از همه کسانی که در بهبود وضعیت اینترنت ایران تلاش می‌کنند.

</div>
