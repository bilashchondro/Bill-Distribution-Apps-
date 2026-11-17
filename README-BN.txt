# Bill Distribution Apps — PWA files

এই ফোল্ডারের সব ফাইল একই GitHub repository-র root-এ রাখুন:
- index.html
- manifest.webmanifest
- service-worker.js
- icons/ (চারটি PNG আইকন)

তারপর GitHub Pages চালু করুন (Settings → Pages → Deploy from a branch → main → /(root))।
HTTPS-এ সাইট খুললে Service Worker নিবন্ধিত হবে। প্রথমবার অনলাইনে অ্যাপ খুলে কিছুক্ষণ অপেক্ষা করুন; এরপর সমর্থিত ব্রাউজারে Install app / Add to Home screen ব্যবহার করুন।

গুরুত্বপূর্ণ:
- PWA ইনস্টল ও অফলাইন অ্যাপ-শেল HTTPS বা localhost-এ কাজ করে; GitHub Pages HTTPS দেয়।
- অফলাইনে অ্যাপের মূল HTML/CSS/JS খোলা যাবে। Excel import/export-এর জন্য `xlsx.full.min.js` আলাদা লোকাল ফাইল হিসেবে একই root-এ যোগ করতে হবে; না হলে প্রথমবার/অফলাইনে Excel লাইব্রেরি না থাকলে সেই ফিচার কাজ নাও করতে পারে।
- ব্যবহারকারীর তথ্য ব্রাউজারের LocalStorage/IndexedDB-তে থাকে। PWA ইনস্টল করলেই পুরোনো ব্রাউজারের ডেটা স্বয়ংক্রিয়ভাবে অ্যাপে চলে আসবে—এমন নিশ্চয়তা নেই। আগে অ্যাপের Backup নিন।
- Manifest থেকে OS নিজস্ব launch splash screen তৈরি করে; আলাদা কাস্টম splash screen সব Android-এ একইভাবে নিয়ন্ত্রণ করা যায় না।
