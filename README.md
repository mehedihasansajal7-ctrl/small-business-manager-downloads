# small-business-manager-downloads

Public APK downloads for the **Small Business Manager** Android app — small business management **plus** the farming module, made for 2–5 business partners in Bangladesh. Offline-first, no paid service anywhere.

## ⬇️ Download

**Direct link (v0.1.0, 74.9 MB):**

```
https://github.com/mehedihasansajal7-ctrl/small-business-manager-downloads/releases/download/v0.1.0/SmallBusinessManager-v0.1.0.apk
```

- Latest release page: [Releases](https://github.com/mehedihasansajal7-ctrl/small-business-manager-downloads/releases/latest)
- SHA-256 of this build: `0B34C6E0CEFD2ECD1E9B6592C09922328B5F1F80875B44671A473EA0DB51C140`
- Signed with APK Signature Scheme **v2** (required to install on Android 11+), certificate `CN=Android Debug` — a side-loaded build, not a Google Play release.

## Install on Android

1. Download the `.apk` file.
2. Tap the downloaded file. Android will ask once to allow installing from this source — allow it.
3. If Play Protect says *"unknown developer"*, choose **Install anyway**. The app is side-loaded; it is deliberately not on Google Play (publishing there costs money).

## ⚠️ First run: set the server address

The app is a client — it talks to a **Small Business Manager API**. On the sign-in screen:

1. Expand **Advanced: which server?**
2. Type the address of your server, for example `http://192.168.0.20:8787` (the computer running the API, on the same Wi-Fi).
3. Tap **Test and save this server**. You should see *"Reachable"*.
4. Now sign in with your email and password.

This build was baked with the default `http://192.168.0.20:8787`, which is only a placeholder — **always test the address first**. If the server cannot be found, the app shows exactly that instead of pretending your password is wrong.

> The APK permits plain **HTTP** servers on a local network on purpose (self-hosted / LAN setup). Once your API is served over HTTPS, that exception should be removed.

## বাংলা — ইনস্টল করার নিয়ম

1. উপরের **Download** লিংক থেকে `.apk` ফাইলটি ডাউনলোড করুন।
2. ফাইলটিতে ট্যাপ করুন। Android একবার জিজ্ঞেস করবে এই সোর্স থেকে ইনস্টল করার অনুমতি দিতে — অনুমতি দিন।
3. Play Protect যদি *"unknown developer"* সতর্কতা দেয়, **Install anyway** চাপুন। অ্যাপটি Google Play-তে নেই (সেখানে প্রকাশ করতে টাকা লাগে)।
4. অ্যাপ খুলে সাইন-ইন স্ক্রিনে **Advanced: which server?** অংশটি খুলুন, সার্ভারের ঠিকানা লিখুন (যেমন `http://192.168.0.20:8787`), **Test and save this server** চাপুন, তারপর ইমেইল-পাসওয়ার্ড দিয়ে সাইন-ইন করুন।
5. সাইন-ইন করার পর অ্যাপটি **অফলাইনেও** কাজ করে — দোকানের বিক্রি, ক্রয়, খরচ, খামারের কাজ সব ফোনে সেভ থাকে এবং ইন্টারনেট ফিরলে নিজে থেকেই সার্ভারে সিঙ্ক হয়।

## What the app does

| | |
|---|---|
| **Business** | Sales/POS, purchases, inventory, customers, suppliers, cash/bank/Mobile-Financial-Service accounts, transfers, income/expenses, partner capital, receivables/payables, reports (profit & loss, balance sheet, trial balance, cash flow) |
| **Farming** | Crop, horticulture/greenhouse, livestock, poultry, fish — plots/sheds/ponds, production cycles, input issue, labour, medicine/feed, observations, mortality, harvest, batch costing, shared-cost allocation, cycle profit |
| **Partners** | 2–5 people, each with their own login and role (owner/admin/manager/cashier/inventory manager/farm manager/viewer), server-enforced permissions, invite codes, audit log |
| **Offline** | SQLite mirror + durable outbox; each change is applied exactly once on the server; conflicts are shown and resolvable |
| **AI assistant** | Works with **no paid service**: a model you run yourself (Ollama), or any free OpenAI-compatible endpoint, or the built-in offline rule engine with curated Bangladesh government (DAE/BRRI/BARI/DLS/DoF) and FAO links |
| **Language** | Bangla and English, light and dark theme, BDT (৳) money formatting |

## How this APK is built

`.github/workflows/android-apk.yml` in the (private) source repository builds it on a GitHub runner:

1. JDK 17 + the runner's Android SDK (`platforms;android-35`, `build-tools;35.0.0`).
2. `expo prebuild --platform android`, then `./gradlew :app:assembleRelease` (the JS bundle is embedded, so the app does not need Metro).
3. `apksigner verify` + the artifact is uploaded, then published here as a Release asset.

No Expo account, no EAS subscription and no Play Console are involved — only GitHub's free Actions minutes.

## Honest limitations

- Side-loaded APK, **not** on Google Play. Updating means installing a newer APK over the old one.
- The app needs a reachable API server to be useful; see `DEPLOYMENT_FREE.md` in the private source repository for the zero-cost hosting path.
- First sign-in and accepting an invitation need the server; after that the app runs offline.
- Photos attached to a record are stored on the server and reach other partners only after they sync.
- This is self-hosted, zero-cost software: it is **not** tax or audit software, and no regulatory compliance is claimed.

## Source

The source lives in the private repository `mehedihasansajal7-ctrl/small-business-manager`. Ask the owner for access.