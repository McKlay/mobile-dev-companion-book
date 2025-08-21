---
hide:
    - toc
---

## 🟢 Part IV: Building Natively with EAS

Up until now, Expo Go has given us an easy way to test apps without touching native code. But as your project grows, you’ll inevitably need more power—custom native modules, deeper debugging, and production-ready builds for the App Store and Play Store. This is where **Expo Application Services (EAS)** comes in. Part IV of this book guides you through the transition from Expo Go to native builds using EAS, helping you understand its tooling and workflows step by step.

### Chapter 7: Introduction to EAS (Expo Application Services)

This chapter explains why Expo Go alone isn’t enough for serious production apps. You’ll learn what EAS provides, how to install and configure the CLI, and how to work with `eas.json` to define different build profiles for development, preview, and production.

**Key points covered:**

* Why Expo Go can’t cover all production use cases.  
* Installing and configuring the EAS CLI.  
* Understanding build profiles in `eas.json`.  

### Chapter 8: Your First Native Build

Here, you’ll run your first actual native build with EAS. Starting with Android, we’ll cover how to generate a development build, install the resulting APK, and test it on your device. You’ll also learn the differences between dev, preview, and production builds so you can choose the right workflow for each stage.

**Key points covered:**

* Running `eas build -p android --profile development`.  
* Installing and testing a Dev Client APK.  
* Differences between dev, preview, and production builds.  

### Chapter 9: Connecting Dev Client to Metro

Once you’ve built and installed a Dev Client, you’ll need to connect it to your development server (Metro). This chapter covers how to launch Metro in Dev Client mode, use tunnels or hotspots for connectivity, and fall back to USB debugging if needed.

**Key points covered:**

* Running `expo start --dev-client`.  
* Handling network setups: tunnels, hotspots, and deep links.  
* Using `adb reverse` as a fallback for USB connections.  

---

By the end of Part IV, you’ll be comfortable building native versions of your app, running them on real devices, and connecting them to your development server for iteration. This knowledge bridges the gap between beginner-friendly Expo Go and professional, production-ready mobile development.  

---
