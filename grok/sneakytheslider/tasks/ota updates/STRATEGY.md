# Over-The-Air (OTA) Update Strategy

This strategy ensures rapid deployment of bug fixes and features without waiting for App Store/Play Store reviews.

## 🛠️ Tooling: Expo Updates (EAS Updates)
We utilize **EAS Updates** as our primary OTA delivery mechanism.

## 🔄 Delivery Workflow
1.  **Release Channels**: 
    - `development`: Internal testing.
    - `preview`: Staging/QA.
    - `production`: Live users.
2.  **Versioning**: 
    - **Runtime Version**: Fixed for each native build. OTA updates only target builds with the same runtime version.
    - **App Version**: Incremented for major native changes (new native modules, permissions).
3.  **Triggering Updates**:
    - Automated: `eas update --branch production` triggered on PR merge.
    - Manual: CLI-based pushes for critical hotfixes.

## 🛡️ Safety & Rollback Plan
- **Phased Rollouts**: Deliver updates to 10% of users first.
- **Emergency Rollback**: Use `eas update:rollback` to revert the branch to a previous successful state.
- **Force Update**: Implement a "Check for Update" hook in the App root to force users to download critical patches immediately.

## 📦 What can be updated OTA?
- JavaScript/TypeScript code.
- Assets (images, fonts).
- CSS/Styles.
- **Cannot update**: Native modules (requires a new store build).
