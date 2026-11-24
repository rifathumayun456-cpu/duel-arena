DUEL — PWA ইনস্টল করার নির্দেশনা

এই ZIP-এ DUEL-এর installable PWA সংস্করণ আছে। GitHub Pages-এ প্রকাশ করলে Android Chrome থেকে অ্যাপ হিসেবে Install করা যাবে।

গুরুত্বপূর্ণ: আগের Local HTML ফাইলে থাকা প্রতিযোগিতার ডেটা নতুন HTTPS ওয়েবসাইটে নিজে থেকে চলে আসবে না। কারণ file:// এবং https:// আলাদা browser storage origin। তাই আগে পুরোনো DUEL খুলে Settings → Data Management → Export Backup (JSON) দিয়ে ব্যাকআপ নিন। নতুন প্রকাশিত DUEL খুলে Settings → Import Backup দিয়ে সেই JSON ফাইলটি ইমপোর্ট করুন।

GitHub Pages-এ প্রকাশ:
১. ZIP Extract করুন।
২. GitHub-এ একটি নতুন Public repository তৈরি করুন; নাম দিতে পারেন duel-arena।
৩. ZIP-এর ভেতরের ফাইলগুলো (index.html, manifest.json, service-worker.js এবং icons ফোল্ডার) repository-র root-এ আপলোড করুন। ZIP ফাইলটিকে একা আপলোড করবেন না।
৪. Repository → Settings → Pages-এ যান।
৫. Build and deployment থেকে Deploy from a branch নির্বাচন করুন।
৬. Branch: main এবং Folder: /(root) নির্বাচন করে Save দিন।
৭. GitHub Pages চালু হলে URL হবে এ রকম:
   https://YOUR-USERNAME.github.io/duel-arena/
৮. Android ফোনে Google Chrome দিয়ে URL খুলুন।
৯. Chrome-এর ⋮ মেনু থেকে Install app নির্বাচন করুন। কিছু সংস্করণে Add to Home screen দেখা যেতে পারে।

প্রথমবার ওয়েবসাইটটি অনলাইনে খুলুন, যাতে অ্যাপের ফাইলগুলো offline ব্যবহারের জন্য cache হতে পারে। এরপর DUEL অফলাইনেও চালু হবে।

মনে রাখবেন:
• সরাসরি index.html ফাইল (file://) খুলে PWA ইনস্টল করা যাবে না।
• ডেটা এই ব্রাউজার/ডিভাইসের LocalStorage-এ থাকবে; একাধিক ডিভাইসে স্বয়ংক্রিয়ভাবে sync হবে না।
• Chrome-এর site data মুছে ফেললে লোকাল ডেটা হারাতে পারেন। নিয়মিত Export Backup নিন।
• ভবিষ্যতে ফাইল আপডেট করলে service-worker.js-এর CACHE_NAME-এর version বাড়াতে হবে।
