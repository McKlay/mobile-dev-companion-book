---
hide:
  - toc
---

# Chapter 7: Introduction to EAS (Expo Application Services)

---


Up to this point, Expo Go has made development feel light and fast. You scan a QR code, and your app runs instantly. But sooner or later, you’ll hit its limitations: perhaps you want to integrate a payment SDK, test push notifications properly, or prepare an actual App Store build. At that point, Expo Go isn’t enough. You’ll need **Expo Application Services (EAS)**—Expo’s cloud-based build and deployment platform.

This chapter introduces why EAS exists, how to set it up, and how to configure build profiles through `eas.json`. You’ll also learn best practices for managing credentials, understanding build types, and preparing for real-world deployment.


## Why Expo Go Is Not Enough

### The Limits of Expo Go

Expo Go is great for early development, but it comes with restrictions:

- Only supports libraries included in the Expo SDK.
- Cannot add custom native code or certain third-party modules (such as payment SDKs, advanced analytics, or custom Bluetooth integrations).
- Isn’t suitable for creating production-ready binaries (APK/IPA) for app stores.
- No access to app signing, store credentials, or advanced build configuration.

So while Expo Go gets you moving quickly, you’ll eventually need to graduate to custom builds that represent your actual app and meet store requirements.

### Enter EAS

EAS solves this problem by giving you:

- **EAS Build** – Cloud-based builds for iOS and Android, without needing Xcode or Android Studio locally. Supports custom native code, third-party modules, and advanced configuration.
- **EAS Submit** – Tools to upload builds directly to the App Store or Play Store, handling credentials and store requirements.
- **EAS Update** – Over-the-air (OTA) updates, letting you ship bug fixes and features instantly without resubmitting to app stores.

In short, EAS is your bridge from local prototyping to professional, production-ready deployment. It’s the missing link between Expo’s fast development workflow and the realities of app distribution.


## Installing and Configuring EAS CLI

### Installation

To start using EAS, install the CLI globally:

```bash
npm install -g eas-cli
```

Verify installation:

```bash
eas --version
```

**Tip:** Keep EAS CLI up to date for the latest features and bug fixes.

### Authentication

You’ll need an Expo account to use EAS. Log in via the CLI:

```bash
eas login
```

This links your local environment with Expo’s cloud services. You can manage multiple projects and teams from a single account.

**Best Practice:** Use environment variables or the Expo dashboard to manage sensitive credentials securely.


## Understanding `eas.json` Build Profiles

At the heart of EAS configuration is the **`eas.json`** file in your project root. It defines build profiles—different sets of rules for development, preview, and production builds. This file lets you customize how your app is built, signed, and distributed for different scenarios.

**Example `eas.json`:**

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

- **Development** – For testing with Dev Clients. Includes debugging tools, hot reloading, and is not intended for public release.
- **Preview** – For sharing with testers, QA, or stakeholders. Not a full production build, but close to release quality.
- **Production** – Optimized for release; ready to upload to stores. Includes minification, signing, and all production optimizations.

Each profile can specify options like distribution type, Gradle/Xcode settings, environment variables, or even custom build scripts. You can add more profiles for staging, QA, or other workflows as needed.

**Best Practices:**

- Use descriptive profile names for clarity.
- Store secrets and signing credentials securely (never commit them to version control).
- Review the EAS documentation for advanced configuration options.


## Conclusion: Setting the Stage for Native Builds

EAS is more than just a build tool—it’s the infrastructure that carries your project from sandbox to store. By understanding why Expo Go isn’t enough, installing the CLI, and learning how build profiles work, you’ve taken the first step into serious mobile development.

**Key Takeaways:**

- EAS unlocks custom native code, advanced modules, and production-ready builds.
- The CLI and `eas.json` give you fine-grained control over your build process.
- Build profiles let you tailor builds for development, testing, and release.

In the next chapter, we’ll put this knowledge into practice by creating your first native build and running it on a device.

---
