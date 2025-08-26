# React Node JS Berry – Starter بسيط لمشروعي

واجهة **React** مبنية على تصميم **Berry Dashboard** فوق مكتبة **MUI** مع إدارة حالة عبر **Redux**، وخلفية **Node.js/Express** مع **JWT** للمصادقة وتخزين **SQLite** عبر **TypeORM**. مناسب للانطلاق بسرعة وبناء لوحة تحكم حديثة.

## المزايا

* تصميم حديث وجاهز من Berry (CodedThemes)
* تسجيل/دخول/خروج عبر JWT
* REST API نظيف مع Express و TypeScript
* تخزين خفيف بقاعدة بيانات SQLite (قابلة للاستبدال لاحقًا)

## المتطلبات

* Node.js 14+
* Git
* Python 3 (مطلوب لبعض الأدوات)

## بدء التشغيل

> يتم تشغيل الواجهة الأمامية والخلفية بشكل مستقل.

### 1) الواجهة الأمامية (React)

```bash
cd react-ui
npm i   # أو yarn
npm run start   # أو yarn start
```

> ستعمل على `http://localhost:3000`

### 2) الخادم الخلفي (Node.js API)

```bash
cd api-server-nodejs
npm i   # أو yarn
# تنفيذ ترحيل قواعد البيانات (TypeORM)
npm run typeorm migration:run  # أو yarn typeorm migration:run
# تشغيل وضع التطوير
npm run dev   # أو yarn dev
```

> الخادم يعمل على المنفذ المحدد في ملف `.env` (الافتراضي 5000).

## ملف البيئة `.env` (مثال)

ضع هذا الملف داخل مجلد `api-server-nodejs`:

```env
PORT=5000
JWT_SECRET=change_me
SQLITE_PATH=./dev.sqlite
```

## بنية المجلدات (مختصر)

```
api-server-nodejs/
  src/
    config/        # الإعدادات وتهيئة Passport-JWT
    migration/     # ملفات ترحيل قاعدة البيانات
    models/        # نماذج TypeORM (User, ActiveSession)
    routes/        # مسارات المستخدم/المصادقة
    index.ts       # نقطة دخول API
react-ui/
  src/             # تطبيق React + MUI + Redux
```


