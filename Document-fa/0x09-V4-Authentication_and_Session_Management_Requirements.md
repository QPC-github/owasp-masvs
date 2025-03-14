<div dir="rtl" markdown="1">

# V4: الزامات تصدیق هویت و مدیریت نشست

## هدف کنترل

در بیشتر موارد، ورود کاربران به یک سرویس از راه‌دور بخشی جدایی ناپذیر از معماری کلی برنامه موبایل است. حتی اگر بیشتر منطق در پایانه رخ دهد. MASVS برخی الزامات پایه در مورد چگونگی مدیریت نشست‌ها و حساب‌های کاربری را تعریف می‌نماید.

## الزامات وارسی امنیت

| # | شناسه-آزمون امنیتی برنامه‌ی کاربردی موبایل | شرح | سطح یک | سطح دو |
| -- | ---------- | ---------------------- | - | - |
| **4.1** | MSTG-AUTH-1 | اگر برنامه‌ی کاربردی برای کاربران، دسترسی به یک سرویس از راه‌دور را فراهم می‌کند، نوعی تصدیق هویت همانند نام کاربری و کلمه عبور باید در پایانه‌ی راه‌دور انجام شود. | x | x |
| **4.2** | MSTG-AUTH-2 | اگر از مدیریت نشست حالت ‌مند (stateful) استفاده شده است، پایانه‌ی راه دور باید بدون ارسال احراز هویت کاربر از شناسه‌های نشست تولید شده به‌طور تصادفی برای تصدیق هویت درخواست‌های سمت کاربر استفاده کند. | x | x |
| **4.3** | MSTG-AUTH-3 | اگر از تصدیق هویت مبتنی بر توکن بدون حالت (stateless) استفاده شده است، سرور باید توکنی را ارائه دهد که توسط یک الگوریتم امن امضا شده باشد. | x | x |
| **4.4** | MSTG-AUTH-4 | وقتی کاربر از سیستم خارج می‌شود، پایانه‌ی راه‌دور نشست فعلی را پایان می‌دهد. | x | x |
| **4.5** | MSTG-AUTH-5 | یک سیاست کلمه عبور وجود دارد و در سمت پایانه‌ی راه‌دور اعمال می‌شود. | x | x |
| **4.6** | MSTG-AUTH-6 | پایانه‌ی راه‌دور مکانیزمی را برای محافظت در برابر وارد کردن اطلاعات احراز هویت نادرست به دفعات زیاد پیاده‌سازی می‌کند. | x | x |
| **4.7** | MSTG-AUTH-7 | نشست‌ها پس از مدتی عدم فعالیت یا منقضی شدن توکن‌های دسترسی در سمت پایانه‌ی راه‌دور نامعتبر می‌شوند. | x | x |
| **4.8** | MSTG-AUTH-8 | تصدیق هویت بیومتریک نباید محدود به یک رویداد باشد (به‌عنوان نمونه استفاده از یک API که تنها True و False را باز می‌گرداند). به‌جای این، باید بر اساس گشودن keychain یا keystore باشد. | | x |
| **4.9** | MSTG-AUTH-9 | مرحله دومی از تصدیق هویت در پایانه‌ی راه‌دور وجود داشته باشد و الزامات تصدیق هویت دو مرحله‌ای همواره الزامی باشند.  | | x |
| **4.10** | MSTG-AUTH-10 | تراکنش‌های حساس نیازمند تصدیق هویت مرحله به مرحله باشند. | | x |
| **4.11** | MSTG-AUTH-11 | برنامه‌ی کاربردی کاربر را نسبت به تمام فعالیت‌های ورود به سیستم با حساب وی آگاه می‌سازد. کاربران قادرند لیستی از دستگاه‌هایی که از آن‌ها برای دسترسی به حساب استفاده شده است را مشاهده کنند و دستگاه‌های خاصی را مسدود نمایند. | | x |
| **4.12** | MSTG-AUTH-12 | مدل‌های صدور مجوز باید در سمت پایانه‌ی راه‌دور تعریف شده و اجباری شوند. | x | x |

## منابع

راهنمای وارسی امنیتی موبایل OWASP، دستورالعمل‌هایی مفصل برای تایید الزامات لیست شده در این بخش، فراهم می‌کند.

- عمومی: احراز هویت و مدیریت نشست - <https://github.com/OWASP/owasp-mastg/blob/master/Document/0x04e-Testing-Authentication-and-Session-Management.md>
- Android: تست احراز هویت داخلی - <https://github.com/OWASP/owasp-mastg/blob/master/Document/0x05f-Testing-Local-Authentication.md>
- iOS: تست احراز هویت داخلی - <https://github.com/OWASP/owasp-mastg/blob/master/Document/0x06f-Testing-Local-Authentication.md>

برای اطلاعات بیشتر همچنین مشاهده کنید:

- OWASP Mobile Top 10: M4 (احراز هویت نا امن) - <https://owasp.org/www-project-mobile-top-10/2016-risks/m4-insecure-authentication>
- OWASP Mobile Top 10: M6 (سطح درسترسی نا امن) - <https://owasp.org/www-project-mobile-top-10/2016-risks/m6-insecure-authorization>
- CWE 287 (احراز هویت نامناسب) - <https://cwe.mitre.org/data/definitions/287.html>
- CWE 307 (اعمال نامناسب منع دسترسی برای تلاش‌های زیاد) - <https://cwe.mitre.org/data/definitions/307.html>
- CWE 308 (استفاده از تایید هویت تک مرحله‌ای) - <https://cwe.mitre.org/data/definitions/308.html>
- CWE 521 (الزامات کلمه عبور ضعیف) - <https://cwe.mitre.org/data/definitions/521.html>
- CWE 604 (احراز هویت سمت کاربر) - <https://cwe.mitre.org/data/definitions/604.html>
- CWE 613 (انقضای نامناسب نشست) - <https://cwe.mitre.org/data/definitions/613.html>

</div>
