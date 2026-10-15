# Small Business Manager — Android app

**English** · [বাংলা](#বাংলা--বাংলা-ভাষায়-নিচে)

Public APK downloads for the **Small Business Manager** app — small business management **plus** the full farming module, built for 2–5 business partners in Bangladesh. Offline-first. No paid service anywhere.

---

## English

#> **v0.1.3: the app now starts in English** (Bangla is one tap away). **v0.1.2 fixed sign-in on a device.** The session now arrives both as a cookie and as a token in the login response, and the server no longer marks the cookie `Secure` on plain HTTP. The language switcher is on the sign-in screen itself, before login.

## ⬇️ Download

**Direct link — v0.1.3 (74.9 MB, 78,550,698 bytes):**

```
https://github.com/mehedihasansajal7-ctrl/small-business-manager-downloads/releases/download/v0.1.3/SmallBusinessManager-v0.1.3.apk
```

- Latest release page: [Releases](https://github.com/mehedihasansajal7-ctrl/small-business-manager-downloads/releases/latest)
- SHA-256: `0ef99e8e6ed7f7aea121b985f7c318f70ebcf54eee26bd5daec3ef2be19f96bf`
- Signed with APK Signature Scheme **v2** (required to install on Android 11+), certificate `CN=Android Debug` — a side-loaded build, not a Google Play release.

### Install on Android

1. Download the `.apk` file.
2. Tap the downloaded file. Android will ask once to allow installing from this source — allow it.
3. If Play Protect says *"unknown developer"*, choose **Install anyway**.

### ⚠️ First run: set the server address

The app is a **client** — it talks to a Small Business Manager API. On the sign-in screen:

1. Expand **Advanced: which server?**
2. Type the address of your server, for example `http://192.168.0.20:8787` (the computer running the API, on the same Wi-Fi).
3. Tap **Test and save this server** — you should see *"Reachable"*.
4. Now sign in with your email and password.

This build was baked with the default `http://192.168.0.20:8787`, which is only a placeholder — **always test the address first**. If the server cannot be found the app says so, instead of pretending your password is wrong.

> The APK permits plain **HTTP** servers on a local network on purpose (self-hosted / LAN setup). Once your API is served over HTTPS, that exception should be removed.

### ভাষা - ইংরেজি ও বাংলা

অ্যাপটি সম্পূর্ণ দ্বিভাষিক এবং এখন **ইংরেজিতে শুরু হয়** (v0.1.3 থেকে); বাংলায় বদলানোর বোতামটি **সাইন-ইন স্ক্রিনেই** এবং **Settings → Language**-এ আছে।s, money is formatted as BDT (`৳12,34,567.89`) with Bangla digits available, and dates render in Bangla month names.

### What the app does

| | |
|---|---|
| **Business** | Sales/POS, purchases, inventory, customers, suppliers, cash / bank / Mobile Financial Service accounts, transfers, income & expenses, partner capital, receivables & payables, reports (profit & loss, balance sheet, trial balance, cash flow) |
| **Farming** | Crop, horticulture/greenhouse, livestock, poultry and fish — plots/sheds/ponds, production cycles, input issue, labour, medicine & feed, observations, mortality, harvest, batch costing, shared-cost allocation, cycle profit |
| **Partners** | 2–5 people, each with their own login and role (owner / admin / manager / cashier / inventory manager / farm manager / viewer), server-enforced permissions, expiring one-time invite codes, audit log |
| **Offline** | SQLite mirror + a durable outbox. Every change is saved on the phone first and applied on the server exactly once; conflicts are shown and can be resolved |
| **AI assistant** | Works with **no paid service**: a model you run yourself (Ollama), any free OpenAI-compatible endpoint, or the built-in offline rule engine with curated Bangladesh government (DAE / BRRI / BARI / DLS / DoF) and FAO links. It never invents a pesticide dose, and never posts a transaction |
| **Trust** | Money and quantities are exact decimals (never floating point); posted records are never edited — corrections are audited reversals |

### How this APK is built

`.github/workflows/android-apk.yml` in the (private) source repository does it on a GitHub runner:

1. JDK 17 + the runner's Android SDK (`platforms;android-35`, `build-tools;35.0.0`).
2. `expo prebuild --platform android`, then `./gradlew :app:assembleRelease` — the JavaScript bundle is embedded, so the app does not need a Metro dev server.
3. `apksigner verify`, upload the artifact, then publish it here as a Release asset.

No Expo account, no EAS subscription and no Play Console are involved — only GitHub's free Actions minutes.

### Honest limitations

- Side-loaded APK, **not** on Google Play. Updating means installing a newer APK over the old one.
- The app needs a reachable API server to be useful. See `DEPLOYMENT_FREE.md` in the private source repository for the zero-cost hosting path.
- The first sign-in and accepting an invitation need the server; after that the app runs offline.
- Photos attached to a record are stored on the server and reach other partners only after they sync.
- Self-hosted, zero-cost software: it is **not** tax or audit software, and no regulatory compliance is claimed.

---

## বাংলা — বাংলা ভাষায় নিচে

**ছোট ব্যবসা ম্যানেজার** অ্যাপের অ্যান্ড্রয়েড APK। এতে আছে ছোট ব্যবসার সম্পূর্ণ হিসাব **এবং** পূর্ণ কৃষি/খামার মডিউল — বাংলাদেশের ২–৫ জন অংশীদারের জন্য তৈরি। অফলাইনেও কাজ করে। কোনো টাকা লাগে না, কোনো paid সার্ভিস লাগে না।

### ⬇️ ডাউনলোড

**সরাসরি লিংক — v0.1.0 (৭৪.৯ MB):**

```
https://github.com/mehedihasansajal7-ctrl/small-business-manager-downloads/releases/download/v0.1.3/SmallBusinessManager-v0.1.3.apk
```

- সব ভার্সন একসাথে: [Releases](https://github.com/mehedihasansajal7-ctrl/small-business-manager-downloads/releases/latest)
- SHA-256: `0ef99e8e6ed7f7aea121b985f7c318f70ebcf54eee26bd5daec3ef2be19f96bf`

### অ্যান্ড্রয়েডে ইনস্টল করার নিয়ম

1. উপরের লিংক থেকে `.apk` ফাইলটি ডাউনলোড করুন।
2. ফাইলটিতে ট্যাপ করুন। Android একবার জিজ্ঞেস করবে "এই সোর্স থেকে ইনস্টল করার অনুমতি দেবেন?" — অনুমতি দিন।
3. Play Protect যদি *"unknown developer"* সতর্কতা দেখায়, **Install anyway** চাপুন। (অ্যাপটি Google Play-তে নেই, কারণ সেখানে প্রকাশ করতে টাকা লাগে — আমরা সেটা এড়িয়ে চলেছি।)

### ⚠️ প্রথমবার চালু করে সার্ভারের ঠিকানা দিতে হবে

এই অ্যাপটি একটি **ক্লায়েন্ট** — এটি Small Business Manager API-এর সাথে কথা বলে। তাই সাইন-ইন স্ক্রিনে:

1. **Advanced: which server?** অংশটি খুলুন।
2. আপনার সার্ভারের ঠিকানা লিখুন, যেমন `http://192.168.0.20:8787` (একই Wi-Fi-তে থাকা কম্পিউটার, যেটিতে API চলছে)।
3. **Test and save this server** চাপুন — *"Reachable"* দেখালে ঠিক আছে।
4. এখন ইমেইল ও পাসওয়ার্ড দিয়ে সাইন-ইন করুন।

এই বিল্ডে ডিফল্ট ঠিকানা হিসেবে `http://192.168.0.20:8787` দেওয়া আছে, যেটি কেবল একটি নমুনা — **তাই আগে ঠিকানা পরীক্ষা করে নিন**। সার্ভার না পাওয়া গেলে অ্যাপ সেটাই স্পষ্ট করে বলবে; ভুল পাসওয়ার্ড ভেবে বিভ্রান্ত করবে না।

> লোকাল নেটওয়ার্কে সাধারণ (HTTP) সার্ভার ব্যবহারের অনুমতি ইচ্ছাকৃতভাবে দেওয়া আছে। API একবার HTTPS-এ চলে গেলে এই অনুমতিটি সরিয়ে দেওয়া উচিত।

### ভাষা - ইংরেজি ও বাংলা

অ্যাপটি সম্পূর্ণ দ্বিভাষিক এবং এখন **ইংরেজিতে শুরু হয়** (v0.1.3 থেকে); বাংলায় বদলানোর বোতামটি **সাইন-ইন স্ক্রিনেই** এবং **Settings → Language**-এ আছে।** থেকে যেকোনো সময় ইংরেজিতে (বা আবার বাংলায়) বদলানো যায়। সব লেখা দুই ভাষাতেই আছে, টাকা বাংলা সংখ্যায় (৳১২,৩৪,৫৬৭.৮৯) দেখানো যায়, আর তারিখও বাংলা মাসের নামে আসে।

### অ্যাপটি কী কী কাজ করে

| | |
|---|---|
| **ব্যবসা** | বিক্রি/POS, ক্রয়, মজুদ (স্টক), কাস্টমার, সরবরাহকারী, নগদ / ব্যাংক / মোবাইল আর্থিক সেবা (বিকাশ-নগদ) হিসাব, এক হিসাব থেকে অন্য হিসাবে টাকা স্থানান্তর, আয় ও ব্যয়, অংশীদারদের পুঁজি, প্রাপ্য ও প্রদেয়, রিপোর্ট (লাভ-ক্ষতি, উদ্বৃত্তপত্র, রেওয়ামিল, নগদ প্রবাহ) |
| **কৃষি / খামার** | ফসল, উদ্যান/গ্রিনহাউস, পশুপালন, পোল্ট্রি ও মাছ চাষ — জমি/ঘর/পুকুর, উৎপাদন সাইকেল, ইনপুট (সার-বীজ-ফিড) ব্যবহার, শ্রম, ঔষধ, পর্যবেক্ষণ, মৃত্যু/ক্ষতি, ফসল কাটা, ব্যাচ খরচ, শেয়ার করা খরচ বণ্টন, সাইকেলের লাভ-ক্ষতি |
| **অংশীদার** | ২–৫ জন, প্রত্যেকের আলাদা লগইন ও নিজস্ব ভূমিকা (মালিক / অ্যাডমিন / ম্যানেজার / ক্যাশিয়ার / স্টোর কর্মকর্তা / খামার ব্যবস্থাপক / দর্শক), সার্ভারে নিয়ন্ত্রিত অনুমতি, মেয়াদসহ একবার-ব্যবহারযোগ্য ইনভাইট কোড, অডিট লগ |
| **অফলাইন** | ফোনে SQLite কপি + নিজস্ব outbox। প্রতিটি এন্ট্রি আগে ফোনে সেভ হয়, পরে সার্ভারে **ঠিক একবারই** যুক্ত হয়; সংঘাত (conflict) থাকলে দেখানো হয় ও মিটিয়ে দেওয়া যায় |
| **AI সহকারী** | **কোনো টাকা লাগে না**: নিজের চালানো মডেল (Ollama), বা যেকোনো ফ্রি OpenAI-সামঞ্জস্যপূর্ণ সার্ভিস, বা অ্যাপের ভেতরের নিয়ম-ভিত্তিক সহকারী — সাথে বাংলাদেশ সরকারের (DAE / BRRI / BARI / DLS / মৎস্য অধিদপ্তর) ও FAO-র অফিসিয়াল লিংক। এটি কোনো কীটনাশকের ডোজ বানিয়ে বলে না, আর নিজে থেকে কোনো লেনদেন পোস্ট করে না |
| **নির্ভরযোগ্যতা** | টাকা ও পরিমাণ হিসাব হয় exact (bigint ভিত্তিক) দশমিক দিয়ে — কখনো `float` নয়। পোস্ট হয়ে যাওয়া এন্ট্রি বদলানো যায় না; সংশোধন করতে হলে অডিটসহ উল্টো এন্ট্রি (reversal) দিতে হয় |

### APK কীভাবে তৈরি হয়

সোর্স কোডের (প্রাইভেট) রিপোজিটরিতে `.github/workflows/android-apk.yml` ফাইলটি GitHub-এর রানারে বিল্ড করে:

1. JDK 17 + রানারের Android SDK (`platforms;android-35`, `build-tools;35.0.0`)
2. `expo prebuild --platform android`, তারপর `./gradlew :app:assembleRelease` — JavaScript বান্ডলটি অ্যাপের ভেতরেই ঢুকিয়ে দেওয়া হয়, তাই Metro সার্ভার ছাড়াই অ্যাপ চলে
3. `apksigner verify` করে যাচাই, তারপর এখানে Release asset হিসেবে প্রকাশ

Expo অ্যাকাউন্ট, EAS সাবস্ক্রিপশন বা Play Console — কিছুই লাগে না; কেবল GitHub Actions-এর ফ্রি মিনিট।

### সৎ সীমাবদ্ধতা

- অ্যাপটি **side-load** করে ইনস্টল করতে হয়, Google Play-তে নেই। আপডেট করতে নতুন APK পুরোনোটির উপরে ইনস্টল করলেই হবে।
- অ্যাপটি কাজ করার জন্য একটি চালু API সার্ভার দরকার। বিনা খরচে হোস্ট করার নিয়ম আছে প্রাইভেট রিপোর `DEPLOYMENT_FREE.md` ফাইলে।
- প্রথম সাইন-ইন এবং ইনভাইট গ্রহণ করতে ইন্টারনেট লাগবে; এরপর অ্যাপ অফলাইনেও চলে।
- কোনো রেকর্ডে যুক্ত করা ছবি সার্ভারে থাকে; অন্য অংশীদার সেটি সিঙ্ক হওয়ার পর দেখতে পাবেন।
- এটি স্ব-হোস্ট করা, শূন্য-খরচের সফটওয়্যার — এটি কর বা অডিট সফটওয়্যার নয়, এবং কোনো সরকারি নিয়মনীতি মেনে চলার দাবি করে না।

---

### Source / সোর্স কোড

Private repository: `mehedihasansajal7-ctrl/small-business-manager`. Access on request — অ্যাক্সেসের জন্য মালিকের সাথে যোগাযোগ করুন।