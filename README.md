# [MY NAME] — Personal Brand Website

موقع شخصي عصري (Dark + Glassmorphism + Aurora Glow) جاهز للتشغيل مباشرة بدون أي أدوات بناء (Build Tools) — مجرد HTML/CSS/JS خالص.

## 🚀 التشغيل

افتح `index.html` في المتصفح مباشرة، أو استخدم أي static server (اختياري):

```bash
npx serve .
```

## ✏️ التعديل — مكان واحد فقط

كل بيانات الموقع (الاسم، الصورة، الـ Bio، الاهتمامات، وحسابات السوشيال ميديا) موجودة في **مكان واحد**:

```
js/main.js  →  const CONFIG = { ... }
```

مثال:

```js
const CONFIG = {
  name: "Seif",
  role: "Digital Creator",
  profileImage: "assets/profile.jpg", // ضع صورتك في مجلد assets واكتب اسمها هنا
  shortBio: "...",
  about: "...",
  interests: ["Gaming", "Photography", "Music", "Travel"],
  socials: {
    instagram: { url: "...", username: "@...", description: "..." },
    snapchat:  { url: "...", username: "@...", description: "..." },
    discord:   { userId: "...", description: "..." },
    facebook:  { url: "", username: "", description: "" }, // أضف الرابط هنا لاحقًا
    whatsapp:  { number: "201125316970", message: "..." },
  },
};
```

لن تحتاج لتعديل أي شيء آخر في الكود — كل الأقسام (Hero, About, Socials, Footer) تُبنى تلقائيًا من هذا الكائن.

## 🖼️ الصورة الشخصية

- صورتك الحقيقية موجودة بالفعل في `assets/profile.jpg` ومربوطة في `CONFIG.profileImage` — تظهر في الـ Hero (ID Card) وفي الأڤاتار الصغير جوه About Me.
- الصورة اتعمللها Crop مربّع (1:1) احترافي يخلي الوجه والجزء العلوي من الجسم ظاهرين بوضوح، مع الحفاظ الكامل على ملامح الوجه بدون أي تعديل أو AI.
- لو عايز تغيّرها لاحقًا: استبدل ملف `assets/profile.jpg` بصورة جديدة (يُفضّل مربعة 1:1)، أو غيّر مسار `profileImage` في الـ CONFIG لصورة تانية.
- حوالين الصورة فيه Glow خفيف بلون الـ Accent (بنفسجي↔سماوي) بينبض ببطء، وده بيتطبق تلقائيًا على أي صورة تحطها.

## 🌐 My Website / Projects

قسم "My Website" بيعرض كارت لموقعك الشخصي، وبياناته في نفس الـ CONFIG:

```js
website: {
  name: "Saif Aldin Website",
  url: "https://saif-aldin-site-production.up.railway.app/index.html",
  description: "Check out my personal website and explore more about me.",
  previewImage: "", // اختياري: ضع مسار صورة Screenshot هنا (مثلاً "assets/website-preview.jpg")
}
```

- لو سبت `previewImage` فاضي، هيظهر بدلها placeholder مصمم (أيقونة globe + Glow) متناسق مع باقي الموقع.
- الضغط على "Visit Website" بيفتح الرابط في تاب جديدة دايمًا.
- لو مسحت الـ `url`، الكارت مش هيظهر خالص.

## 💬 Discord

نظراً لأن Discord لا يوفر رابط بروفايل عام من الـ User ID فقط، تم استخدام:

```
https://discord.com/users/<USER_ID>
```

هذا الرابط يفتح صفحة البروفايل الخاصة بك داخل تطبيق/موقع Discord مباشرة لأي شخص مسجّل دخول بالفعل — وهو أفضل حل متاح بدون رابط دعوة مخصص.

## 📱 WhatsApp

يستخدم `https://wa.me/<number>?text=<message>` بحيث يفتح المحادثة مباشرة (تطبيق على الموبايل / WhatsApp Web على الكمبيوتر) بدون أي نسخ يدوي للرقم.

## 🗂️ هيكل المشروع

```
portfolio/
├── index.html      ← البنية + الأقسام + الميتاداتا (SEO/OG)
├── css/style.css   ← كل التصميم، المتغيرات (Design Tokens)، الأنيميشن
├── js/main.js      ← CONFIG (بياناتك) + منطق الموقع بالكامل
├── assets/         ← ضع صورك هنا (بروفايل، OG cover...)
└── README.md
```

## ⚡ ملاحظات أداء

- لا توجد أي مكتبات خارجية ثقيلة — فقط Google Fonts.
- الأنيميشن كله CSS/JS خفيف (لا Canvas ثقيل ولا مكتبات particles ضخمة).
- الموقع يحترم `prefers-reduced-motion` تلقائيًا.
- الـ Custom Cursor وتأثير الـ Mouse-glow يعملان فقط على الأجهزة اللي بها فأرة حقيقية (لا تؤثر على الموبايل/التابلت).
