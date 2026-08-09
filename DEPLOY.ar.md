# رفع موقع GitHub Pages — شرح مفصّل

المجلد `gh-pages/` جاهز كموقع مستقل (هوية مختلفة عن pubgredeemerbot.com).  
بعد الرفع سيظهر على:

**https://aliothman123.github.io/spark-uc-midasbuy-api/**

---

## الطريقة الموصى بها: فرع `gh-pages`

تنسخ محتويات المجلد إلى فرع اسمه `gh-pages` في مستودع  
[spark-uc-midasbuy-api](https://github.com/aliothman123/spark-uc-midasbuy-api)  
بحيث يكون `index.html` في **جذر** الفرع (مش داخل مجلد فرعي).

### أ) من جهازك (Git)

افتح PowerShell أو Terminal:

```bash
# 1) انسخ الريبو (أو حدّثه إن كان عندك)
git clone https://github.com/aliothman123/spark-uc-midasbuy-api.git
cd spark-uc-midasbuy-api

# 2) أنشئ فرع gh-pages فارغ (أو انتقل له إن موجود)
git checkout --orphan gh-pages
git rm -rf . 2>/dev/null || true

# 3) انسخ كل ملفات موقع Pages إلى جذر الفرع
# عدّل المسار حسب مكان مشروع البوت عندك:
# Windows مثال:
# xcopy /E /I /Y "C:\Users\Ali\Desktop\مشاريع بايثون\pubg_activator_bot\gh-pages\*" .
# أو يدوياً: انسخ محتويات gh-pages داخل مجلد الريبو وأنت على فرع gh-pages

git add .
git commit -m "Add Spark UC API GitHub Pages developer hub"
git push -u origin gh-pages
```

على Windows إذا `xcopy` مزعج، انسخ المجلد يدوياً:

1. افتح `pubg_activator_bot\gh-pages`
2. انسخ **كل ما بداخله** (index.html, recipes.html, bot.html, assets, …)
3. الصقه في جذر الريبو وأنت على فرع `gh-pages`
4. ثم `git add .` → `commit` → `push`

### ب) تفعيل Pages من إعدادات GitHub

1. افتح المستودع على GitHub  
2. **Settings** → **Pages** (من القائمة الجانبية)  
3. تحت **Build and deployment**:
   - **Source**: Deploy from a branch  
   - **Branch**: `gh-pages`  
   - **Folder**: `/ (root)`  
4. اضغط **Save**  
5. انتظر دقيقة–دقائق حتى تظهر رسالة خضراء بالرابط:

`https://aliothman123.github.io/spark-uc-midasbuy-api/`

---

## طريقة بديلة: مجلد `/docs` على فرع `main`

إذا تفضّل عدم استخدام فرع منفصل:

1. على فرع `main` أنشئ مجلد `docs/`  
2. انسخ **محتويات** `gh-pages/` داخل `docs/`  
3. Settings → Pages → Branch: `main` → Folder: `/docs` → Save  

الرابط يبقى نفسه:  
`https://aliothman123.github.io/spark-uc-midasbuy-api/`

---

## بعد النشر — SEO وفهرسة Google

1. افتح الموقع وتأكد الصفحات الثلاث تعمل والصور تظهر.  
2. في [Google Search Console](https://search.google.com/search-console) أضف الخاصية إن لزم، ثم **URL Inspection** لـ:
   - `https://aliothman123.github.io/spark-uc-midasbuy-api/`
   - `.../recipes.html`
   - `.../bot.html`  
   واطلب **Request indexing**.  
3. من موقعك الرسمي أضف رابط dofollow واضح مثلاً في  
   `https://www.pubgredeemerbot.com/midasbuy-api.html`  
   نحو GitHub Pages + نحو الريبو (هذا يسرّع أرشفة Google أكثر من انتظار github.com لوحده).  
4. في README المستودع أضف في الأعلى:

```md
## Developer hub (GitHub Pages)
https://aliothman123.github.io/spark-uc-midasbuy-api/
```

5. اختياري: Bing Webmaster → Submit URL لنفس الروابط.

---

## محتويات الموقع

| ملف | الوظيفة |
|---|---|
| `index.html` | الصفحة الرئيسية للمطوّرين + SEO + JSON-LD |
| `recipes.html` | وصفات تكامل (متجر / ريسيلر / Python) |
| `bot.html` | صفحة ترويج البوت تيليجرام |
| `404.html` | صفحة خطأ |
| `robots.txt` + `sitemap.xml` | زحف وفهرسة |
| `assets/` | CSS, JS, أيقونة, OG, صور الشاشات |

---

## تعديل الروابط لاحقاً

كل الروابط الـ canonical و الـ sitemap مضبوطة على:

`https://aliothman123.github.io/spark-uc-midasbuy-api/`

إذا غيّرت اسم المستخدم أو الريبو، حدّث:
- `link rel="canonical"` في كل HTML  
- `og:url` / `og:image`  
- `sitemap.xml` و `robots.txt`  
- سكربتات JSON-LD  

---

## تجربة محلية قبل الرفع

من داخل مجلد `gh-pages`:

```bash
# Python
python -m http.server 8080
```

ثم افتح: http://127.0.0.1:8080/

---

## ملاحظات مهمة

- لا ترفع المجلد باسم `gh-pages/index.html` داخل الفرع؛ ارفع **المحتويات** للجذر.  
- الموقع **متعمداً** مختلف عن الموقع الرسمي (ألوان فوسفور / تيبوغرافيا Sora) حتى ما يصير duplicate content.  
- الصور منسوخة محلياً داخل `assets/img` — ما تعتمد على هوتلينك للموقع الرسمي.  
- للدعم: [@sparkuc_support](https://telegram.me/sparkuc_support)
