# small-business-manager-downloads

Public APK downloads for the **Small Business Manager** Android app — small business management **plus** the farming module, made for 2–5 business partners in Bangladesh. Offline-first, no paid service anywhere.

## Download

**[➜ Latest APK](https://github.com/mehedihasansajal7-ctrl/small-business-manager-downloads/releases/latest)**

After a release exists, the direct link looks like:

```
https://github.com/mehedihasansajal7-ctrl/small-business-manager-downloads/releases/download/v0.1.0/SmallBusinessManager-v0.1.0.apk
```

All versions: [Releases](https://github.com/mehedihasansajal7-ctrl/small-business-manager-downloads/releases)

## Install on Android

1. Download the `.apk` file from the latest release.
2. Tap the downloaded file. Android will ask once to allow installing from this source — allow it.
3. If Play Protect says *"unknown developer"*, choose **Install anyway**. The app is side-loaded; it is deliberately not on Google Play (publishing there costs money).

## ⚠️ First run: set the server address

The app is a client — it talks to a **Small Business Manager API**. On the sign-in screen:

1. Expand **Advanced: which server?**
2. Type the address of your server, for example `http://192.168.0.20:8787` (the computer running the API, on the same Wi-Fi).
3. Tap **Test and save this server**. You should see *"Reachable"*.
4. Now sign in with your email and password.

If you skip this, the app will try the address that was baked in at build time and will fail to find a server — which looks exactly like a wrong password, so always test the address first.

> The APK permits plain **HTTP** servers on a local network on purpose (a self-hosted or LAN setup). Once your API is served over HTTPS, that exception should be removed.

## বাংলা — ইনস্টল করার নিয়ম

1. **Latest APK** লিংক থেকে `.apk` ফাইলটি ডাউনলোড করুন।
2. ফাইলটিতে ট্যাপ করুন। Android একবার জিজ্ঞেস করবে এই সোর্স থেকে ইনস্টল করার অনুমতি দিতে — অনুমতি দিন।
3. Play Protect যদি *"unknown developer"* সতর্কতা দেয়, **Install anyway** চাপুন। অ্যাপটি Google Play-তে নেই (সেখানে প্রকাশ করতে টাকা লাগে)।
4. অ্যাপ খুলে সাইন-ইন স্ক্রিনে **Advanced: which server?** অংশটি খুলুন, সার্ভারের ঠিকানা লিখুন (যেমন `http://192.168.0.20:8787`), **Test and save this server** চাপুন, তারপর ইমেইল-পাসওয়ার্ড দিয়ে সাইন-ইন করুন।
5. সাইন-ইন করার পর অ্যাপটি **অফলাইনেও** কাজ করে — দোকানের বিক্রি, ক্রয়, খরচ, খামারের কাজ সব সেভ থাকে এবং ইন্টারনেট ফিরলে নিজে থেকেই সিঙ্ক হয়।

## What the app does

| | |
|---|---|
| **Business** | Sales/POS, purchases, inventory, customers, suppliers, cash/bank/Mobile-Financial-Service accounts, transfers, income/expenses, partner capital, receivables/payables, reports (profit & loss, balance sheet, trial balance, cash flow) |
| **Farming** | Crop, horticulture/greenhouse, livestock, poultry, fish — plots/sheds/ponds, production cycles, input issue, labour, medicine/feed, observations, mortality, harvest, batch costing, shared-cost allocation, cycle profit |
| **Partners** | 2–5 people, each with their own login and role (owner/admin/manager/cashier/inventory manager/farm manager/viewer), server-enforced permissions, invite codes, audit log |
| **Offline** | SQLite mirror + durable outbox; each change is applied exactly once on the server; conflicts are shown and resolvable |
| **AI assistant** | Works with **no paid service**: a model you run yourself (Ollama), or any free OpenAI-compatible endpoint, or the built-in offline rule engine with curated Bangladesh government (DAE/BRRI/BARI/DLS/DoF) and FAO links |
| **Language** | Bangla and English, light and dark theme, BDT (৳) money formatting |

## Honest limitations

- Side-loaded APK, **not** published on Google Play. Updating means installing the newer APK over the old one (same signing key, so your data stays).
- The app is useless without a reachable API server. If you want a hosted setup, see `DEPLOYMENT_FREE.md` in the main (private) repository.
- The first sign-in and accepting an invitation need the server; after that the app runs offline.
- Photos attached to a record are stored on the server and reach other partners only after they sync.
- This is a self-hosted, zero-cost project: it is **not** tax or audit software, and no regulatory compliance is claimed.

## Source

The source code lives in a private repository (`mehedihasansajal7-ctrl/small-business-manager`). Ask the owner for access.