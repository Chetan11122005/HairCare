# HairCare (haiRcure) 🌿💆‍♂️

> An intelligent, AI-powered iOS companion for holistic hair health, scalp recovery, and personalized wellness routines.

[![Swift](https://img.shields.io/badge/Swift-5.9+-orange.svg?style=flat&logo=swift)](https://swift.org)
[![iOS](https://img.shields.io/badge/iOS-17.0+-blue.svg?style=flat&logo=apple)](https://developer.apple.com/ios/)
[![SwiftUI](https://img.shields.io/badge/SwiftUI-Latest-purple.svg?style=flat&logo=swift)](https://developer.apple.com/xcode/swiftui/)
[![Supabase](https://img.shields.io/badge/Supabase-Backend-3ECF8E.svg?style=flat&logo=supabase)](https://supabase.com)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## 📱 About the App

**HairCare** is a modern iOS application built with SwiftUI that empowers users to understand, track, and improve their hair health through AI-driven insights, clinical-backed assessments, lifestyle tracking, and chemical ingredient analysis.

---

## ✨ Key Features

### 🔬 1. AI Scalp & Hair Analysis
- **Stage Classification**: Identifies hair thinning and loss stages (Stage 1 to 4) using intelligent image recognition.
- **Weekly Progress Scans**: Track scalp regrowth, density, and follicle health over time with side-by-side historical comparisons.
- **Scientific Recommendations**: Dynamic recovery roadmaps tailored to your specific hair profile and genetics.

### 📋 2. Comprehensive Onboarding & Assessment
- In-depth multi-step questionnaire covering lifestyle, genetics, diet, stress levels, and existing hair care routines.
- Generates a customized, actionable **Daily Recovery Protocol**.

### 🏠 3. Daily Protocol & Home Dashboard
- **Central Adherence Ring**: Real-time visual progress tracker for daily hair care tasks.
- **AI Hair Coach**: Interactive conversational AI assistant for instant hair and scalp advice.
- **Hydration Tracker**: Log daily water intake and view historical hydration patterns.
- **Sleep & Recovery**: Apple HealthKit sync to correlate sleep duration and recovery with hair vitality.

### 🧘‍♂️ 4. Wellness & MindEase
- **MindEase Mood Tracker**: Interactive mood logging featuring fluid Lottie animations (Calm, Anxious, Stressed, Tired) to monitor stress-induced hair shedding (Telogen Effluvium).
- **DietMate**: Hair-vital nutrient tracking (Biotin, Zinc, Iron, Protein, Vitamin D) to ensure internal nourishment.

### 🧴 5. Hair Insights & Product Scanner
- **Ingredient Barcode Scanner**: Scan hair product barcodes to fetch and analyze chemical formulations via **PubChem API**.
- **Toxicity & Safety Ratings**: Instant flags for harmful sulfates, parabens, silicones, and irritating alcohols.
- **"My Shelf"**: Organize your personal hair care inventory with usage frequency and compatibility tips.

---

## 🛠️ Architecture & Tech Stack

- **UI Framework**: SwiftUI (iOS 17+ Observable Pattern `@Observable`)
- **Backend & Auth**: [Supabase](https://supabase.com) (PostgreSQL, Row-Level Security, Auth)
- **AI Engine**: OpenRouter / LLM APIs for personalized health reasoning
- **Chemical Knowledge Base**: NCBI PubChem REST API
- **Health Integration**: Apple HealthKit (`HKHealthStore`)
- **Animations**: Lottie for iOS & CoreAnimation
- **Architecture Pattern**: MVVM with centralized DataStores and Services

---

## 📂 Project Structure

```text
HairCare/
├── App/
│   ├── Haircure.swift                  # App entry point
│   ├── ContentView.swift               # Root navigation & TabView
│   └── Config.xcconfig.example         # Environment template
├── Models/                             # Swift structs & data schemas
│   ├── UserModel.swift
│   ├── AssessmentModel.swift
│   ├── HairAnalysisModel.swift
│   ├── HairInsightsModel.swift
│   └── MindEaseModel.swift
├── DataStores/                         # ViewModels & reactive stores
│   ├── AppDataStore.swift
│   ├── AuthViewModel.swift
│   ├── HomeViewModel.swift
│   ├── AssessmentViewModel.swift
│   └── WeeklyScanViewModel.swift
├── Services/                           # Networking & integrations
│   ├── SupabaseManager.swift           # Supabase client configuration
│   ├── BackendService.swift            # Database queries & sync
│   ├── AIRecommendationService.swift  # AI/LLM integration
│   ├── PubChemService.swift            # Ingredient safety analysis
│   ├── HealthKitManager.swift          # Apple HealthKit integration
│   └── NotificationManager.swift       # Daily reminders & alerts
└── Views/                              # Modular SwiftUI views
    ├── Authentication/                 # Login, Sign Up, Guest mode
    ├── Assesments/                     # Onboarding & questionnaire
    ├── HairAnalysis/                   # Camera scan & photo analyzer
    ├── Home/                           # Protocol, Coach & Dashboard
    ├── Wellness/                       # MindEase & DietMate
    ├── HairInsights/                   # Barcode scanner & My Shelf
    └── Profile/                        # Settings & user profile
```

---

## 🚀 Getting Started

### Prerequisites
- macOS Sonoma (14.0+) or later
- Xcode 15.0+ or Xcode 16.0+
- iOS 17.0+ deployment target
- A free [Supabase](https://supabase.com) account
- An [OpenRouter](https://openrouter.ai) API key (for AI Coach features)

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Chetan11122005/HairCare.git
   cd HairCare
   ```

2. **Configure Environment Variables**:
   Copy the example configuration file and enter your API keys:
   ```bash
   cp HairCare/Config.xcconfig.example HairCare/Config.xcconfig
   ```
   Open `HairCare/Config.xcconfig` in Xcode or your editor and supply your credentials:
   ```xcconfig
   SUPABASE_URL = https://your-project.supabase.co
   SUPABASE_ANON_KEY = your-anon-key
   OPENROUTER_API_KEY = your-openrouter-api-key
   GOOGLE_CLIENT_ID = your-google-client-id
   GOOGLE_REVERSED_CLIENT_ID = your-google-reversed-client-id
   ```

3. **Open in Xcode**:
   ```bash
   open HairCare.xcodeproj
   ```

4. **Build and Run**:
   Select your target simulator (e.g., iPhone 15 Pro / iPhone 16 Pro) or a connected physical iOS device, and press `Cmd + R`.

---

## 🔒 Security & Privacy

- All sensitive keys (`Config.xcconfig`) are excluded from version control via `.gitignore`.
- User biometric and health data (HealthKit) remain strictly on-device or encrypted in compliant backend storage.

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
