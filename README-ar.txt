وين تلقاه؟ — الملفات النهائية (النسخة v1.1 — نوفمبر 2026)
==========================================================
هذي هي النسخة الوحيدة المعتمدة. تجاهل أي ملفات أقدم منها.

محتوى المجلد
------------
site/        ← هذي هي ملفات الموقع. ترفعها كلها على GitHub (مستودع Wain-talgah):
   index.html             التطبيق كامل (الشعار والأيقونة مدمجين)
   privacy.html           سياسة الخصوصية
   terms.html             شروط الاستخدام (جديد في v1.1)
   sw.js                  عامل الخدمة (للتثبيت على الشاشة)
   manifest.webmanifest   إعدادات التثبيت
   icon-180.png / icon-192.png / icon-512.png   أيقونات التثبيت
   README.md              وصف قصير للمستودع
database/
   database.sql           قاعدة البيانات الكاملة. تُشغَّل في Supabase فقط. لا ترفعها على GitHub.
logos/        ← نسخ الشعار (رئيسية، بروفايل، شفافة للخلفيات الداكنة). للإعلانات والصفحات.

الإعدادات الحالية (جاهزة داخل index.html)
-----------------------------------------
مشروع Supabase: gqneciyfwpwyjmyytggg
رقم واتساب الإدارة: 0940510551
بريد الإدارة: waintalgah@gmail.com
سعر الاشتراك المبدئي: 10 دينار (يتغيّر من لوحة الإدارة)

خطوات التشغيل من الصفر
----------------------
1) Supabase → SQL Editor → New query → الصق database/database.sql كامل → Run.
2) Authentication → Sign In / Providers → فعّل Allow anonymous sign-ins → Save.
3) Authentication → Users → Add user → إيميل وكلمة مرور للإدارة + Auto Confirm.
4) SQL Editor → استعلام جديد:
   insert into admins (user_id) select id from auth.users where email = 'ايميل-الادارة';
5) GitHub → المستودع → Add file → Upload files → ارفع كل ملفات مجلد site (8 ملفات + الأيقونات) → Commit changes.
6) Settings → Pages → Deploy from a branch → main → / (root) → Save.
7) رابط التطبيق:  https://hsamalhdar1-cell.github.io/Wain-talgah/
   لوحة الإدارة:  https://hsamalhdar1-cell.github.io/Wain-talgah/#admin

مهم
---
- لا ترفع database.sql ولا أي مفتاح سري (secret / service_role) على GitHub.
- المفتاح الموجود في index.html هو المفتاح العام (publishable) ومصمم يكون ظاهر.
- بعد أي تحديث للملف على GitHub، افتح الرابط مع ?v=رقم جديد لتجاوز الكاش.

جديد في v1.1
------------
- زر «🚩 إبلاغ» على الطلبات والمحلات والعروض، وبلاغات الإدارة تظهر في لوحة الإدارة.
- «حذف كل طلباتي» و«حذف هذا الطلب» للزبون، و«حذف محلي وبياناته» للتاجر.
- موافقة إجبارية على شروط الاستخدام قبل إرسال طلب أو تسجيل محل.
- أزرار التواصل مع الإدارة (واتساب + إيميل) أسفل كل الصفحات.
- لازم تعيد تشغيل database/database.sql في Supabase مرة وحدة (آمن، ما يمسح بياناتك) عشان جدول البلاغات وصلاحية الحذف.
