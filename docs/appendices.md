---
hide:
  - toc
---

# 📑 Technical Appendices (Cheat Sheets & Guides)

---

This appendix serves as your quick-access toolkit—a set of references, cheat sheets, and flowcharts you can consult while building apps with React Native, Expo, and EAS. Think of it as the developer’s “survival pack,” condensing key commands and troubleshooting steps into one place.

---

## Appendix A: CLI Commands Reference (Expo, EAS, adb)

### Expo CLI

```bash
npx create-expo-app my-app        # Scaffold a new Expo app
npx expo start                    # Start development server
npx expo start -c                 # Start and clear Metro cache
npx expo install <package>        # Install library with Expo SDK alignment
npx expo-doctor                   # Diagnose version/dependency issues
````

### EAS CLI

```bash
npm install -g eas-cli            # Install EAS CLI globally
eas login                         # Authenticate with Expo account
eas build -p android --profile development   # Build for Android dev client
eas build -p ios --profile production        # Build for iOS production
eas submit -p android             # Submit build to Google Play
eas submit -p ios                 # Submit build to Apple App Store
```

### ADB (Android Debug Bridge)

```bash
adb devices                       # List connected Android devices
adb install myapp.apk             # Install APK on device
adb reverse tcp:8081 tcp:8081     # Forward Metro traffic via USB
adb logcat                        # Stream logs for debugging crashes
```

---

## Appendix B: Comparison – Expo vs CRA/Vite (for Web Devs Crossing into Mobile)

| Feature                | CRA / Vite (Web)              | Expo (Mobile)                        |
| ---------------------- | ----------------------------- | ------------------------------------ |
| **Setup**              | Instant scaffold              | Instant scaffold (`create-expo-app`) |
| **Development server** | Webpack / Vite Dev Server     | Metro bundler                        |
| **Hot reload**         | Built-in                      | Fast Refresh & Live Reload           |
| **Styling**            | CSS, Tailwind                 | React Native styles, NativeWind      |
| **Native APIs**        | Browser APIs                  | Device APIs (camera, sensors, GPS)   |
| **Deployment**         | Web hosting (Vercel, Netlify) | App stores (EAS + Play/App Store)    |
| **Distribution**       | Instant via URL               | Requires APK/IPA builds + reviews    |

---

## Appendix C: Troubleshooting Flowchart (Metro, Builds, Dependencies)

**Symptom:** Red error screen in Metro  
→ Check error text → If mentions **babel** → confirm `babel.config.js` setup.  
→ If mentions **worklet/UIManager** → check `react-native-reanimated` or `gesture-handler` versions.  
→ Clear cache with `npx expo start -c`.  
→ Still failing? Run `expo-doctor`.  

**Symptom:** Library won’t install / version mismatch  
→ Did you use `expo install` instead of `npm install`?  
→ Run `expo-doctor`.  
→ Align versions with current Expo SDK release.  

**Symptom:** Device won’t connect to Metro  
→ Ensure same Wi-Fi network.  
→ Try tunnel mode (`expo start --tunnel`).  
→ Use USB fallback with `adb reverse`.  

**Symptom:** Build fails in EAS  
→ Check `eas.json` for correct profile.  
→ Confirm credentials (keystore/provisioning).  
→ Re-run with `--clear-cache`.  
→ Search Expo forums for known SDK/version issues.  

---

## Appendix D: Starter Project Template (Expo + NativeWind)

A ready-to-use starter template structure:

```
my-app/
├── App.tsx
├── app.json
├── babel.config.js
├── package.json
├── tailwind.config.js
├── assets/
│   ├── icon.png
│   └── splash.png
└── components/
    ├── Button.tsx
    ├── Card.tsx
    └── Header.tsx
```

**Sample App.tsx**

```tsx
import { TailwindProvider } from "nativewind";
import { Text, View } from "react-native";

export default function App() {
  return (
    <TailwindProvider>
      <View className="flex-1 items-center justify-center bg-gray-100">
        <Text className="text-lg font-bold text-indigo-600">
          Hello, Expo + NativeWind!
        </Text>
      </View>
    </TailwindProvider>
  );
}
```
---

##  Recommended Resources

These are trusted external resources to help you explore deeper and learn more beyond this book:

| Topic                          | Resource                                                                 |
|-------------------------------|--------------------------------------------------------------------------|
| **React Native Docs**         | [reactnative.dev](https://reactnative.dev/docs/getting-started) |
| **Expo Documentation**        | [docs.expo.dev](https://docs.expo.dev/) |
| **React Navigation**          | [reactnavigation.org](https://reactnavigation.org/docs/getting-started) |
| **Babel Basics**              | [babeljs.io](https://babeljs.io/) |
| **Metro Bundler (GitHub)**    | [Metro GitHub / metro-bundler](https://github.com/facebook/metro) |

---

These resources complement the explanations in the book with official guides, API references, and deeper context. Bookmark them as your go-to for reliable documentation, community best practices, and the latest updates in your mobile development journey.

---

# ✅ Final Note

These appendices are designed for **speed and clarity**. Keep them close while building—whether you’re debugging a stubborn Metro error, recalling an EAS command, or scaffolding a fresh project with Tailwind.

They’re not meant to replace the detailed explanations from earlier chapters—but to give you a practical reference when you need answers fast.

---