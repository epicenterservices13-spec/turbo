# React Native Mobile Architecture (Imperial Arsenal Standard)

This document defines the standard mobile architecture for the SneakyTheSlider / Imperial Arsenal ecosystem.

## 🏛️ Core Principles
- **Atomic Design**: Components are divided into Atoms, Molecules, and Organisms.
- **Feature-Based Modularization**: Code is grouped by feature rather than layer (e.g., `features/auth/`, `features/scanner/`).
- **Type Safety**: TypeScript-first development.
- **State Management**: React Context for small state; TanStack Query for server state; Zustand for complex client state.

## 📁 Directory Structure (Scaffolding)

```text
src/
├── assets/          # Images, fonts, icons
├── components/      # Shared UI components (Atoms, Molecules)
├── config/          # Environment variables, constants
├── features/        # Business logic grouped by feature
│   └── [feature]/
│       ├── components/
│       ├── hooks/
│       ├── services/
│       ├── state/
│       └── [Feature]Screen.tsx
├── hooks/           # Global shared hooks
├── navigation/      # React Navigation stacks and types
├── services/        # API clients (Axios/Fetch), local DB (WatermelonDB)
├── store/           # Global zustand stores
├── theme/           # UI styles (colors, spacing, typography)
└── utils/           # Helper functions
```

## 🛠️ Tech Stack Recommendations
- **Framework**: Expo (Managed Workflow)
- **Styling**: NativeWind (Tailwind for React Native) or Styled Components.
- **Navigation**: Expo Router (File-based) or React Navigation.
- **Icons**: Lucide React Native.
- **Form Management**: React Hook Form + Zod.

## 🔋 Performance & Optimization
1. **Memoization**: Use `useMemo` and `useCallback` for expensive operations.
2. **Image Optimization**: Use `expo-image` for high-performance caching and blurred placeholders.
3. **List Rendering**: Use `FlashList` from Shopify for smoother scrolling.
4. **Native Modules**: Use `expo-modules-core` to write Swift/Kotlin if native bridges are needed.
