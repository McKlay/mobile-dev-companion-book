---
hide:
  - toc
---

# Chapter 7: Introduction to EAS (Expo Application Services)

---

Up to this point, Expo Go has made development feel light and fast. You scan a QR code, and your app runs instantly. But sooner or later, you’ll hit its limitations: perhaps you want to integrate a payment SDK, test push notifications properly, or prepare an actual App Store build. At that point, Expo Go isn’t enough. You’ll need **Expo Application Services (EAS)**—Expo’s cloud-based build and deployment platform.

This chapter introduces why EAS exists, how to set it up, and how to configure build profiles through `eas.json`.

## Why Expo Go Is Not Enough

### The Limits of Expo Go

Expo Go is great for early development, but it comes with restrictions:

* Only supports libraries included in the Expo SDK.  
* Cannot add custom native code or certain third-party modules.  
* Isn’t suitable for creating production-ready binaries (APK/IPA).  

So while Expo Go gets you moving quickly, you’ll eventually need to graduate to custom builds that represent your actual app.

### Enter EAS

EAS solves this problem by giving you:

* **EAS Build** – Cloud-based builds for iOS and Android, without needing Xcode or Android Studio locally.  
* **EAS Submit** – Tools to upload builds directly to the App Store or Play Store.  
* **EAS Update** – Over-the-air (OTA) updates, letting you ship bug fixes instantly without resubmitting to app stores.  

In short, EAS is your bridge from local prototyping to professional, production-ready deployment.

## Installing and Configuring EAS CLI

### Installation

To start using EAS, install the CLI globally:

```bash
npm install -g eas-cli
````

Verify installation:

```bash
eas --version
```

### Authentication

You’ll need an Expo account to use EAS. Log in via the CLI:

```bash
eas login
```

This links your local environment with Expo’s cloud services.

## Understanding `eas.json` Build Profiles

At the heart of EAS configuration is the **`eas.json`** file in your project root. It defines build profiles—different sets of rules for development, preview, and production builds.

Example `eas.json`:

```json
{
  "build": {
    "development": {
      "distribution": "internal",
      "developmentClient": true
    },
    "preview": {
      "distribution": "internal"
    },
    "production": {
      "distribution": "store"
    }
  }
}
```

### Profiles Explained

* **Development** – For testing with Dev Clients. Includes debugging tools.
* **Preview** – For sharing with testers, but not full production.
* **Production** – Optimized for release; ready to upload to stores.

Each profile can specify options like distribution type, Gradle/Xcode settings, or even custom build scripts.

## Conclusion: Setting the Stage for Native Builds

EAS is more than just a build tool—it’s the infrastructure that carries your project from sandbox to store. By understanding why Expo Go isn’t enough, installing the CLI, and learning how build profiles work, you’ve taken the first step into serious mobile development.

In the next chapter, we’ll put this knowledge into practice by creating your first native build and running it on a device.

---
