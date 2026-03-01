![Flutter](https://img.shields.io/badge/Flutter-3.x-blue)
![Firebase](https://img.shields.io/badge/Firebase-Enabled-orange)
![License](https://img.shields.io/badge/License-Proprietary-red)

# 🕌 Quran App — Beautiful Digital Mushaf

A modern, ad-free, AI-enhanced Quran application built with Flutter.

This app provides a premium digital Mushaf experience with clean architecture, offline support, AI reflection, Tafsir integration, and secure Firebase backend.

---

## ✨ Features

- 📖 Full 114 Surahs (Uthmani script)
- 📄 Page-by-page Mushaf layout
- 🔍 Arabic + English Search
- 🎧 Audio Recitation (Streaming + Offline-ready)
- 📚 Tafsir Module
- 🤖 AI Reflection (Cloud Functions)
- 📿 Tasbeeh Counter
- 🔖 Cloud Sync Bookmarks
- 💎 Subscription-ready (Stripe/Firebase)
- 🌙 Beautiful Gold Islamic UI Theme
- 🚫 No Ads (Donation / Premium Model)

---

## 🏗 Architecture

This project follows a **Clean Architecture + Feature-based structure**.

```
lib/
 ├── app/
 ├── core/
 ├── data/
 ├── domain/
 ├── features/
```

### Layers

- **Presentation** → UI + Providers
- **Domain** → Entities + UseCases
- **Data** → Models + Repositories + DataSources
- **Core** → Shared services & utilities

This keeps the app scalable and testable.

---

## 📦 Tech Stack

- **Flutter 3.x**
- **Riverpod** (state management)
- **Firebase**
  - Auth
  - Firestore
  - Cloud Functions
- **Isar DB** (local storage + search indexing)
- **Just Audio** (recitation playback)
- **Dio** (downloads)
- **GoRouter** (navigation)

---

## 🚀 Getting Started

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/yourusername/quran_app.git
cd quran_app
```

---

### 2️⃣ Install Dependencies

```bash
flutter pub get
```

---

### 3️⃣ Setup Firebase

1. Create a project in the Firebase Console.
2. Add Android, iOS, and Web apps.
3. Download:
   - `google-services.json` → android/app/
   - `GoogleService-Info.plist` → ios/Runner/
4. Run:

```bash
flutterfire configure
```

---

### 4️⃣ Firestore Rules

Deploy included rules:

```bash
firebase deploy --only firestore:rules
```

---

### 5️⃣ Run the App

```bash
flutter run
```

---

## 📂 Assets Setup

Place required assets inside:

```
assets/json/quran_uthmani.json
assets/json/tafsir.json
assets/fonts/UthmanicHafs.ttf
```

Update `pubspec.yaml` accordingly.

---

## 🔐 Environment Configuration

For AI Reflection Cloud Function:

Create a Firebase HTTPS callable function:

```js
exports.generateReflection = onCall(async (request) => {
  const text = request.data.text;
  return { reflection: "AI response here" };
});
```

Deploy:

```bash
firebase deploy --only functions
```

---

## 🎧 Audio Setup

Recitation audio can be:

- Streamed from CDN
- Downloaded locally using Dio
- Cached in app directory

Recommended structure:

```
audio/{reciter}/{surah}_{ayah}.mp3
```

---

## 💎 Subscription Model

Premium unlocks:

- Unlimited AI reflections
- Offline high-quality audio
- Advanced Tafsir
- Custom themes

Subscription status stored in:

```
subscriptions/{uid}
```

Stripe webhook updates Firestore.

---

## 📈 Performance Considerations

- Use pagination for Mushaf rendering
- Index search data with Isar
- Cache AI responses
- Preload next audio ayah
- Lazy-load Tafsir content

Designed to scale to 100k+ users.

---

## 🧪 Testing

Run tests:

```bash
flutter test
```

Recommended coverage:

- UseCases
- Repository layer
- Search functionality

---

## 🌍 Web Build

```bash
flutter build web --release
```

Deploy to Firebase Hosting:

```bash
firebase deploy --only hosting
```

---

## 📱 Build Release

### Android

```bash
flutter build appbundle --release
```

### iOS

```bash
flutter build ios --release
```

---

## 🛡 Security

Firestore rules enforce:

- Users can only access their own data
- Subscription writes are restricted
- Auth required for protected collections

Never store API keys in the app.

---

## 🕌 Vision

To provide the most beautiful, distraction-free, AI-enhanced digital Mushaf experience for Muslims worldwide.

---

## 📄 License

Private / Proprietary  
All rights reserved.

---

## 🤝 Contribution

This is a production project.  
For contributions, open a structured issue first.

---

## 🌙 Bismillah

Built with intention, clarity, and ihsan.