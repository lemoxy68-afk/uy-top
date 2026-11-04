UY TOP ilovasi (Capacitor, Android APK)

1) GitHub'da yangi repo oching (masalan uytop-app) va shu papkadagi hamma fayllarni yuklang
   (www/, .github/, package.json, capacitor.config.json).
2) www/firebase-config.js ga Firebase web sozlamalarini qo'ying (Uy top uchun ochilgan YANGI Firebase loyihasining
   web sozlamalari; Render'dagi FIREBASE_JSON_UYTOP ham shu loyihadan bo'lishi kerak).
3) Firebase -> Firestore -> Rules ga "sales" uchun o'qishni qo'shing (yozish faqat serverda qoladi):
     match /sales/{id} { allow read: if true; allow write: if false; }
4) GitHub -> Actions -> "Build APK" -> Run workflow. 5-8 daqiqadan keyin Artifacts ichidan uytop-apk ni yuklab oling.
5) Birinchi marta ochganda ekranda "The query requires an index" xatosi chiqsa, xabardagi havolani brauzerda
   oching va "Create index" ni bosing (bir martalik, 2-3 daqiqa).

Paket nomi: uz.uytop.app.
Play Market: Actions -> "Release AAB (Play Market)" (imzo kaliti GitHub Secrets'da: KEYSTORE_BASE64,
KEYSTORE_PASSWORD, KEY_ALIAS, KEY_PASSWORD). Loyiha Capacitor 8 (Android 16 / API 36), Play shuni talab qiladi.
