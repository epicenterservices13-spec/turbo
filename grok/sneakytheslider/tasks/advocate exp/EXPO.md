# Expo Advocacy & Integration

We advocate for the **Expo Managed Workflow** as the default for the Imperial Arsenal ecosystem to maximize developer velocity and maintainability.

## 🌟 Why Expo?
1.  **Unified Build System (EAS)**: Cloud builds for iOS/Android without local macOS/Android Studio overhead.
2.  **Expo Modules**: Direct access to native APIs (Bluetooth, Camera, Sensors) with a simplified API.
3.  **Fast Refresh**: Superior DX with reliable hot reloading.
4.  **One Project, Multiple Platforms**: Web support out-of-the-box.

## 🚀 Setup Strategy
1.  **Initialize**: `npx create-expo-app@latest -t expo-template-blank-typescript`
2.  **Environment Sync**: Use `eas.json` to manage environment variables (`development`, `preview`, `production`).
3.  **CI/CD Integration**: Github Actions linked with Expo Application Services (EAS).

## 📊 Developer Experience (DX)
- **Expo Go**: For rapid prototyping.
- **Development Builds**: Create a custom binary that includes specific native modules for production-parity testing.
- **EAS Submit**: Automated app store submissions.
