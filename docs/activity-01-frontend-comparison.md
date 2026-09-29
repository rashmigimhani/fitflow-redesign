# Activity 01: Comparison of Mobile Development Frameworks

## 1.1 Introduction

FitFlow requires a mobile technology that supports rapid development, reusable code, good performance, real-time functionality, AI/ML integration, security and a consistent experience across platforms. Flutter, React Native, Kotlin Multiplatform and Swift/SwiftUI were compared using the criteria specified in the lab sheet.

## Technology Comparison

| Criterion | Flutter | React Native | Kotlin Multiplatform | Swift / SwiftUI |
|---|---|---|---|---|
| Development Speed | High – hot reload and widget system | Very high – fast TypeScript/React workflow | Medium – shared logic but native UI work | Medium – strong for Apple but separate platforms |
| Code Reusability | Very high | High | Medium-high | Low outside Apple |
| Performance | Very good | Good to very good | Very high | Excellent |
| Ecosystem Support | Large | Very large | Growing | Excellent for Apple |
| Learning Curve | Moderate; Dart required | Low-moderate for React developers | Steeper; Kotlin and interop | Moderate; Swift/SwiftUI |
| Web Compatibility | Good | Very good with React web/React Native Web | Limited/less mature | Very limited |
| AI/ML Integration | Good | Good | Good to very good | Excellent |
| Real-Time Features | Good | Excellent | Good | Excellent |
| Maintenance Cost | Low-medium | Low-medium | Medium | High for cross-platform |
| Security | Good with secure native practices | Good with proper dependency/native security | Very good | Excellent |

## 1.3 Flutter

- Provides a single Dart codebase and a large widget library.
- Supports rapid development through hot reload and is suitable for animation-heavy interfaces.
- Can integrate with Firebase, WebSockets, camera features and machine-learning services.
- Requires the team to learn Dart and some web scenarios may require additional optimization.

**Suitability for FitFlow:** Strong candidate, particularly for consistent cross-platform UI and animation performance.

## 1.4 React Native

- Uses JavaScript/TypeScript and provides strong code reuse between Android and iOS.
- Has a large React and npm ecosystem for APIs, camera, notifications and real-time functionality.
- Works naturally with a React-based web application and a TypeScript backend.
- Performance-critical camera or platform-specific functionality may require native modules.

**Suitability for FitFlow:** Strong fit for a cross-platform application that needs rapid delivery and an extensive ecosystem.

## 1.5 Kotlin Multiplatform

- Allows business logic to be shared while retaining native platform capabilities.
- Provides strong performance and direct access to Android and iOS APIs.
- Has a smaller multiplatform ecosystem than React Native and Flutter.
- The web story and shared UI options require more platform-specific consideration.

**Suitability for FitFlow:** Suitable where native platform control is a priority, but it introduces more complexity for a seamless web target.

## 1.6 Swift / SwiftUI

- Provides excellent native iOS performance and integration with Apple technologies.
- Offers strong access to HealthKit, Core ML and other Apple APIs.
- Does not provide a unified Android and web solution.
- Using it as the primary framework would require separate development for other platforms.

**Suitability for FitFlow:** Useful for platform-specific Apple modules but not appropriate as the main cross-platform framework.

## 1.7 Decision Matrix

| Criterion | Weight | Flutter | React Native | Kotlin Multiplatform | Swift/SwiftUI |
|---|---:|---:|---:|---:|---:|
| Development Speed | 15% | 5 | 5 | 3 | 4 |
| Code Reusability | 15% | 5 | 5 | 4 | 2 |
| Performance | 15% | 5 | 4 | 5 | 5 |
| Ecosystem | 10% | 4 | 5 | 4 | 5 |
| Learning Curve | 10% | 4 | 4 | 3 | 3 |
| Web Compatibility | 10% | 5 | 4 | 3 | 1 |
| AI/ML Integration | 10% | 4 | 4 | 4 | 5 |
| Real-Time Capability | 5% | 5 | 5 | 4 | 4 |
| Maintenance | 5% | 5 | 5 | 4 | 2 |
| Security | 5% | 4 | 4 | 5 | 5 |
| **Weighted Score** | **100%** | **4.65/5** | **4.50/5** | **3.85/5** | **3.60/5** |

The weighted calculation uses a 1–5 scale. React Native is selected as the primary mobile framework because it provides strong cross-platform reuse, a large ecosystem, rapid development and good compatibility with the proposed TypeScript-based backend. React can be used for the web client, while native Kotlin/Swift modules can be introduced only when platform-specific functionality requires them.

## 1.8 Recommended Technology

**Recommended approach:** React Native with TypeScript for iOS and Android, complemented by React/Next.js for the web. Native Swift or Kotlin modules may be used selectively for HealthKit/Health Connect, camera processing or other platform-specific capabilities. This hybrid approach keeps the main application cross-platform while preserving access to native APIs.
