# حسين عبيد — بورتفوليو (صفحة واحدة)

بورتفوليو ثنائي اللغة (عربي/إنجليزي) في ملف واحد، بدون مكتبات خارجية، مع CSS مجمّع مسبقاً وخطوط self-hosted.

---

## 1) ملفات النشر — ارفع هذه الستة فقط إلى جذر المستودع

| الملف | الوظيفة |
|---|---|
| `index.html` | الصفحة كاملة (HTML + CSS مجمّع + JS) |
| `hussein.webp` | صورتك الشخصية (22KB) |
| `og.jpg` | بطاقة المشاركة عند نشر الرابط (1200×630) |
| `apple-touch-icon.png` | أيقونة iOS عند "إضافة إلى الشاشة" |
| `fonts-grot.woff2` | خط Space Grotesk (لاتيني) self-hosted |
| `fonts-cairo.woff2` | خط Cairo (عربي) self-hosted |

> لا ترفع: أي ملف `in.css`/`out.css`/`node_modules` إن وجد — هذه أدوات بناء محلية فقط.

## 2) خطوات الرفع على GitHub Pages (دقيقة واحدة)

1. أنشئ/افتح المستودع باسم: **`devbyhussein.github.io`** (user site — يجب أن يكون بهذا الاسم تحديداً).
2. ارفع الملفات الستة إلى **جذر** الفرع الرئيسي (`main`).
3. Settings → Pages → Source: **Deploy from a branch** → Branch: `main` / `/ (root)` → Save.
4. انتظر ~دقيقة، ثم جرّب: **https://devbyhussein.github.io/**
5. لو ظهرت صفحة قديمة من الإقلاع: Ctrl+Shift+R (تحميل قسري).

## 3) تفعيل الإحصاء (اختياري — Cloudflare Web Analytics، مجاني وبلا كوكيز)

1. أنشئ حساباً على [dash.cloudflare.com](https://dash.cloudflare.com) → **Web Analytics** → *Add a site* → أدخل `devbyhussein.github.io`.
2. انسخ قيمة `token` من مقطع كود التثبيت الذي يعرضه.
3. افتح `index.html` وابحث عن `TOKEN=""` (قرب النهاية قبل `</body>`) والصقه بين علامتي التنصيص: `TOKEN="xxxxxxxx"`.
4. ارفع الملف من جديد. حتى تلك اللحظة لن يحمّل الموقع أي شيء إطلاقاً.

## 4) ما يتبقى عليك داخل `index.html` (ابحث في السكربت السفلي)

- **`CONFIG.projects`**: ضع الرابط الحقيقي في `url` لكل مشروع من الست (استخدم `"#"` للمؤقت).
- **عينات الشهادات**: استبدل نصوص مفاتيح `tst1..tst3` بآراء حقيقية (ابحث عن `TODO` فوق قسم Testimonials).

## 5) ما بعد النشر — قائمة تحقق سريعة

- [ ] شارك الرابط على واتساب وراقب بطاقة `og.jpg` (أول مشاركة تُبنى).
- [ ] حدّث الكاش إن لزم: [Sharing Debugger](https://developers.facebook.com/tools/debug/) للفيسبوك، أو [opengraph.xyz](https://www.opengraph.xyz/) للمعاينة.
- [ ] أعد Lighthouse من رابط حي: https://pagespeed.web.dev/
- [ ] سجّل الموقع في [Google Search Console](https://search.google.com/search-console) لتظهر في البحث أسرع.
- [ ] تحقق أن الروابط `whatsapp / email / socials` تعمل من الهاتف.

## 6) ملاحظة صيانة

- تعديل **نصوص/روابط/أفعال JS**: حرّر مباشرة — لا حاجة لأي إعادة تجميع.
- إضافة **فئة Tailwind جديدة** لم تُستخدم من قبل: تحتاج إعادة تجميع (`in.css` → `npx @tailwindcss/cli@4 -i in.css -o out.css --minify` ثم استبدال محتوى `<style id="tw">`).
