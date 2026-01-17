
In 2026, the Android Developer codelab library is categorized into Modern Android Development (MAD) (Jetpack Compose, Kotlin Multiplatform, and AI integration) and Legacy (XML/View-based) modules. Here's  a list of the key active codelabs available on developer.android.com/codelabs

### Important Notes for 2026 Development
- API 36 (Android 16): Modern codelabs now target API 36 as the "Compile SDK." If you are using a codelab that targets API 33 or lower, it likely contains legacy patterns (like XML or Fragments).

- The "(Deprecated)" Prefix: On the official site, any codelab involving Dagger (not Hilt), DataBinding, or Leanback is explicitly tagged as "Deprecated." These are kept only for developers maintaining apps built before 2023.

- 16 KB Page Size Compatibility: A new set of specialized codelabs was added in 2025 to help developers recompile native (C++) code for upcoming high-performance hardware architecture.



# Modern Android Development (MAD) 2026: Core Learning Path

This repository serves as a roadmap for mastering Android development in 2026. It focuses exclusively on the **Modern Android Development (MAD)** ecosystem, intentionally omitting legacy XML, Fragments, and Java-based modules to ensure a future-proof, conflict-free architecture.

---

## 🚀 The 2026 Modern Frameworks
The table below lists the essential codelabs and modules available on `developer.android.com/codelabs` that align with 2026 standards.

| Category | Codelab Topic | Key Technologies | Modern Benefit |
| :--- | :--- | :--- | :--- |
| **UI & UX** | [Jetpack Compose Essentials](https://developer.android.com/codelabs/jetpack-compose-basics) | Compose, Material 3, State | Declarative UI; replaces XML layouts. |
| **UI & UX** | [Adaptive Layouts for Large Screens](https://developer.android.com/develop/ui/views/layout/responsive-adaptive-design-with-views) | WindowSizeClass, Pane Layouts | Native support for foldables and tablets. |
| **Architecture** | [Architecture & State in Compose](https://developer.android.com/codelabs/jetpack-compose-state) | ViewModel, StateFlow, UDF | Reactive state management without `LiveData`. |
| **Architecture** | [Navigation in Jetpack Compose](https://developer.android.com/guide/navigation/navigation-3) | Compose Navigation, Type-safe | Replaces Fragment Transactions and NavGraph XML. |
| **Multiplatform** | [Get Started with KMP](https://developer.android.com/codelabs/kmp-get-started) | KMP, Shared Logic, SKIE | Share code between Android and iOS seamlessly. |
| **AI & ML** | [Generative AI with Gemini](https://developer.android.com/ai/gemini) | Gemini Pro API, AI SDK | Integrated on-device and cloud-based AI. |
| **Data & Sync** | [Room with Coroutines & Flow](https://developer.android.com/codelabs/android-room-with-a-view-kotlin) | Room, Flow, Repository | Asynchronous local persistence; no UI blocking. |
| **Performance** | [Optimizing for Android XR](https://developer.android.com/develop/xr/unity/performance) | Compose XR, Spatial Panels | Developing for the 2026 AR/VR hardware ecosystem. Unity App for Android|
| **Performance** | [Compose Performance](https://developer.android.com/codelabs/jetpack-compose-performance) | Baseline Profiles | Ensuring smooth 120Hz performance on modern chips. |

---

## 🏗️ Project Structure (Standard 2026)

To avoid conflicting legacy modules, your project directory should follow this modularized structure:

```text
root/
├── composeApp/            # Shared UI and logic (KMP support)
│   ├── src/commonMain     # Business logic, Repositories, ViewModels
│   ├── src/androidMain    # Android-specific Compose entry points
│   └── src/iosMain        # iOS-specific entry points
├── build-logic/           # Kotlin DSL for build management
├── core/
│   ├── network/           # Ktor or Retrofit (Modern config)
│   ├── database/          # Room (No SQLiteOpenHelper)
│   └── designsystem/      # Material 3 Theme & Composable components
└── gradle/                # Version Catalog (libs.versions.toml)
```


 ## Implementation Strategy for 2026
To maintain a codebase free of legacy conflicts, follow these 2026 Modern Standards:

- Language: Use Kotlin 2.1+ with the K2 compiler enabled by default.

- UI Toolkit: Jetpack Compose only. Do not include ConstraintLayout (XML) or CoordinatorLayout dependencies.

- Asynchrony: Use Kotlin Coroutines and Flow. Avoid RxJava or AsyncTask legacy wrappers.

- Dependency Injection: Use Hilt (built on Dagger) for compile-time safe DI that is Lifecycle-aware.

- Multi-Device: Prioritize Adaptive Layouts; 2026 development assumes a variety of form factors (Handheld, Foldable, XR).
