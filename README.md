<div align="center">

<img src="assets/logo.png" alt="BANANA Market" width="120" />

<h3><b>BANANA Market</b></h3>
<p><b>A secondhand marketplace that blocks fraudulent listings before they go live.</b></p>

<p>
  <a href="#features"><strong>Features</strong></a> ·
  <a href="#tech-stack"><strong>Tech Stack</strong></a> ·
  <a href="#getting-started"><strong>Getting Started</strong></a> ·
  <a href="#screenshots"><strong>Screenshots</strong></a>
</p>

<p>

[![Flutter](https://img.shields.io/badge/Flutter-3.x-02569B?logo=flutter)](https://flutter.dev)
[![Dart](https://img.shields.io/badge/Dart-3.7-0175C2?logo=dart)](https://dart.dev)
[![Firebase](https://img.shields.io/badge/Firebase-cloud-FFCA28?logo=firebase&logoColor=black)](https://firebase.google.com)
[![MadCamp](https://img.shields.io/badge/MadCamp-Week%201-yellow)](https://madcamp.io)

</p>

</div>

---

## What & Why

BANANA Market is a Flutter app built during **MadCamp Week 1** that tackles a core trust problem in peer-to-peer commerce: sellers uploading images that have nothing to do with the item they're listing.

When a seller posts a product, **Google ML Kit analyzes every uploaded image** and compares the detected labels against the seller's chosen tags. If they don't match, the listing is rejected — before any buyer ever sees it.

> [!NOTE]
> This project is a fork of [banana-madcamp/banana](https://github.com/banana-madcamp/banana), developed as a one-week intensive at MadCamp.

---

## Features

<details>
<summary><b>AI-Powered Fraud Prevention</b></summary>

- Runs **Google ML Kit image labeling** on every uploaded photo at listing creation time
- Uses a 50% confidence threshold to filter low-quality label matches
- Blocks submission if image labels do not overlap with the seller's declared tags
- Validates each image in a listing independently

</details>

<details>
<summary><b>Product Listings</b></summary>

- Upload photos and short videos per product
- Attach searchable tags, title, description, price, and pickup location
- Tag autocomplete via a searchable dialog
- Skeleton loading states while images fetch

</details>

<details>
<summary><b>Browsing & Discovery</b></summary>

- Home feed with cached network images for fast scrolling
- Filter listings by tag
- Location-aware listing display

</details>

<details>
<summary><b>Checkout Flow</b></summary>

- Select delivery method (pickup / courier)
- Choose payment method
- Review total and confirm order

</details>

<details>
<summary><b>User Account</b></summary>

- Email sign-up and sign-in via Firebase Auth
- Secure token storage with flutter_secure_storage
- Wishlist / favorites management
- Profile page with transaction history and logout

</details>

---

## Tech Stack

| Layer | Technology |
|---|---|
| UI Framework | [Flutter](https://flutter.dev) |
| Language | [Dart](https://dart.dev) 3.7 |
| State Management | [GetX](https://pub.dev/packages/get) |
| Auth & Database | [Firebase Auth](https://firebase.google.com/products/auth) + [Cloud Firestore](https://firebase.google.com/products/firestore) |
| File Storage | [Firebase Storage](https://firebase.google.com/products/storage) + [Supabase](https://supabase.com) |
| AI / ML | [Google ML Kit Image Labeling](https://developers.google.com/ml-kit/vision/image-labeling) |
| Media | [image_picker](https://pub.dev/packages/image_picker) · [video_player](https://pub.dev/packages/video_player) |
| Caching | [cached_network_image](https://pub.dev/packages/cached_network_image) |

---

## Screenshots

| AI Validation | Product Detail | Checkout |
|:---:|:---:|:---:|
| ![AI filter](https://github.com/user-attachments/assets/2bb70e80-af5b-4818-822e-7f4f375deb42) | ![Detail](https://github.com/user-attachments/assets/b1160c66-093b-425f-8da6-3d93a87cce10) | ![Checkout](https://github.com/user-attachments/assets/964f5146-85ae-4219-8248-b47ac48373fc) |

| Wishlist | Profile |
|:---:|:---:|
| ![Wishlist](https://github.com/user-attachments/assets/24f0c15a-2669-41a9-bace-470df0e3215f) | ![Profile](https://github.com/user-attachments/assets/186a75d7-9361-44d8-a07d-d68df1b5c553) |

---

## Getting Started

### Prerequisites

- [Flutter SDK](https://docs.flutter.dev/get-started/install) >= 3.7
- [Firebase CLI](https://firebase.google.com/docs/cli) configured for the project
- Android SDK or Xcode (for iOS builds)

### Installation

```bash
git clone https://github.com/UnripePlum/banana.git
cd banana
flutter pub get
flutter run
```

> [!IMPORTANT]
> This app requires a Firebase project with Auth, Firestore, and Storage enabled. `firebase_options.dart` and `google-services.json` / `GoogleService-Info.plist` are not included. Run `flutterfire configure` against your own Firebase project to generate them.

### Download APK

A pre-built Android APK is available on [Google Drive](https://drive.google.com/file/d/1n4rfwgsRB4VU2vwcM1BsFHFFxoXC_52x/view?usp=share_link).

---

## How It Works

```
Seller uploads images + tags
        │
        ▼
Google ML Kit analyzes each image
(confidence threshold: 0.5)
        │
        ▼
Detected labels compared to seller tags
        │
      ┌─┴──────────────────┐
   Match                No match
      │                    │
      ▼                    ▼
Listing created      Submission blocked
  in Firestore        with error message
```

---

## Team

Built in one week at [MadCamp](https://madcamp.io) (Winter 2024/2025).

| Name | Affiliation |
|---|---|
| 박기람 | Hanyang University, Information Systems '22 |
| 김한준 | KAIST, School of Computing '21 |

---

## License

No license file is included. All rights reserved by the authors unless otherwise stated.
