# GOOSIQ WALLET

## الملفات
- index.html: تسجيل الدخول وإنشاء الحساب واستعادة كلمة المرور.
- dashboard.html: واجهة المستخدم.
- admin.html: لوحة الإدارة.
- workers/r2-upload-worker.js: Worker لرفع/عرض صور R2.
- firebase-rules.json: نموذج أولي للقواعد.

## قبل الاستخدام
1. فعّل Email/Password في Firebase Authentication.
2. أنشئ مستخدم الإدارة ثم اجعل role الخاص به `admin` داخل users/UID.
3. اربط Cloudflare Worker بـ R2 Binding باسم MY_BUCKET.
4. انشر Worker الجديد بدل Worker العرض فقط.

## تحذير أمني مهم
هذا المشروع نموذج كامل للواجهة والمنطق الأولي، لكنه ليس نظامًا مصرفيًا جاهزًا للإنتاج.
عمليات الرصيد والتحويل والموافقة يجب نقلها إلى Backend موثوق (Cloudflare Worker مع Authentication/Secrets أو Firebase Cloud Functions) مع قواعد تمنع الكتابة المباشرة على balances من المتصفح.
