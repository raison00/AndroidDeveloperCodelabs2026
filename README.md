
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
| **Architecture** | [Architecture & State in Compose](https://developer.android.com/develop/ui/compose/architecture) | ViewModel, StateFlow, UDF | Reactive state management without `LiveData`. |
| **Architecture** | [Navigation in Jetpack Compose](https://developer.android.com/guide/navigation/navigation-3) | Compose Navigation, Type-safe | Replaces Fragment Transactions and NavGraph XML. |
| **Multiplatform** | [Get Started with KMP](https://developer.android.com/codelabs/kmp-get-started) | KMP, Shared Logic, SKIE | Share code between Android and iOS seamlessly. |
| **AI & ML** | [Generative AI with Gemini](https://developer.android.com/ai/gemini) | Gemini Pro API, AI SDK | Integrated on-device and cloud-based AI. |
| **Data & Sync** | [Room with Coroutines & Flow](https://developer.android.com/training/data-storage/room/creating-views) | Room, Flow, Repository | Asynchronous local persistence; no UI blocking. |
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

# Official Android Developer Codelabs (2026)

This repository contains a curated list of official Android developer codelabs, updated for 2026 standards.

| Codelab Title | Link | Last Updated | Summary | Target API |
| :--- | :---: | :--- | :--- | :---: |
| **Android XR Fundamentals: Part 1** | [🔗](https://developer.android.com/codelabs/xr-fundamentals-part-1#0) | Oct 2025 | Creating spatial panels and 3D orbiters for Android XR devices. | `34+` |
| **Android Automotive: Parked Apps** | [🔗](https://developer.android.com/codelabs/build-a-parked-app#0) | Oct 2025 | Designing video and gaming experiences for car infotainment screens. | `33+` |
| **Adaptive Apps with Jetpack Compose** | [🔗](https://developer.android.com/codelabs/codelab-adaptive-apps#0) | Jun 2025 | Optimizing UI for tablets, foldables, and desktop modes using Window Size Classes. | `31+` |
| **Keyboard Focus in Compose** | [🔗](https://developer.android.com/codelabs/compose-keyboard-focus) | Jun 2025 | Advanced D-pad and keyboard navigation for non-touch devices. | `21+` |
| **Compose for Wear OS (Material 3)** | [🔗](https://developer.android.com/codelabs/compose-for-wear-os#0) | May 2025 | Building power-efficient watch faces and apps with M3 Expressive. | `33+` |
| **Performance: Macrobenchmark** | [🔗](https://developer.android.com/codelabs/android-macrobenchmark-inspect#0) | Jun 2025 | Measuring app startup and frame drops to ensure 120Hz smoothness. | `29+` |
| **Build for Matter (Smart Home)** | [🔗](https://developer.android.com/codelabs/matter-sample-app#0) | Aug 2024 | Integrating IoT devices using the Google Home Mobile SDK. | `30+` |
| **Kotlin Multiplatform (KMP) Basics** | [🔗](https://developer.android.com/codelabs/kmp-get-started#0) | May 2025 | Sharing business logic and Room databases between Android and iOS. | `21+` |
| **Health Connect Integration** | [🔗](https://developer.android.com/codelabs/health-connect#0) | Oct 2025 | Reading and writing fitness data to the system-level Health storage. | `28+` |
| **Jetpack Compose Basics** | [🔗](https://developer.android.com/codelabs/jetpack-compose-basics#0) | Jan 2024 | The entry-level tutorial for declarative UI development. | `21+` |
| **Advanced Testing with Gemini** | [🔗](https://developer.android.com/codelabs/testing-with-gemini-code-assist#0) | May 2025 | Using Agentic AI to generate and run automated user journey tests. | `30+` |
