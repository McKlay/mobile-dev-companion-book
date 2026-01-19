---
hide:
  - toc
---

# Chapter 8: Your First Native Build

---


After setting up EAS, it’s time to cross the threshold from Expo Go into the world of true native builds. This chapter will guide you through creating your first native build using EAS, installing it on your device, and understanding the differences between dev, preview, and production builds. You’ll also learn best practices for troubleshooting builds, managing credentials, and testing on real hardware.


## Running `eas build -p android --profile development`

### Starting with Android

We’ll begin with Android, since generating an APK is often the fastest way to see your app outside Expo Go. From your project root, run:

```bash
eas build -p android --profile development
```

Here’s what this command does:

- **`-p android`** → Targets Android platform.
- **`--profile development`** → Uses the `development` profile from `eas.json`.

EAS will upload your project, run the build in the cloud, and provide a download link once it’s ready. You can monitor build progress in the terminal or on the Expo dashboard.

**Tip:** You can also build for iOS with `-p ios`, but iOS builds require an Apple Developer account and additional setup.

### First-Time Prompts

On your first run, EAS may ask you about credentials (keystore for Android, provisioning profiles for iOS). Expo can manage these for you automatically, which is ideal when starting out. You can also provide your own credentials for more control or advanced workflows.

**Best Practice:** Let Expo handle credentials unless you have a specific reason to manage them yourself. Always back up any credentials you generate.


## Installing and Testing the Dev Client APK

Once the build is complete, you’ll get a link to download the APK. Install it on your device:

- **On Android** → Open the link in your browser and install the APK directly. You may need to enable "Install unknown apps" in your device settings.
- **On iOS** → You’ll need to use a simulator or TestFlight (since direct sideloading is restricted by Apple). EAS can help automate TestFlight uploads with `eas submit`.

When you open the Dev Client app, it will look like your project but with one major difference: it can now load **custom native modules** beyond what Expo Go supports. This is essential for testing features like custom SDKs, advanced navigation, or device integrations.

### Testing Workflow

1. Run your Metro bundler in Dev Client mode:

  ```bash
  expo start --dev-client
  ```

2. Open the Dev Client app on your device.
3. Connect it to Metro using the QR code or deep link provided in the terminal or Expo Developer Tools.

At this point, your app is running in a build that mirrors production more closely. You can test custom native code, debug with React DevTools, and iterate quickly.

**Troubleshooting:**

- If the app can’t connect to Metro, check your network, firewall, or try using tunnel mode (`expo start --dev-client --tunnel`).
- For persistent issues, clear caches with `npx expo start -c` and rebuild.


## Differences Between Dev, Preview, and Production Builds

Understanding build types is key to a smooth workflow and successful releases.

### Development Builds

- Includes debugging tools and development menus (like the Expo Dev Menu).
- Great for local testing with custom native modules and rapid iteration.
- Distributed internally—never to actual users or app stores.
- Not optimized for performance or size.

### Preview Builds

- Used for testers, QA, or staging environments.
- Distribution is internal, but optimized more like production (minified, fewer debug tools).
- Often used before final release to catch last-minute bugs.
- Can be shared with stakeholders for feedback.

### Production Builds

- Optimized, signed, and ready for app stores.
- No developer menus or debugging overlays.
- Must meet store requirements (icons, splash screens, signing keys, privacy policies).
- Should be thoroughly tested before submission.

**Best Practice:**

- Use dev builds for feature development, preview builds for team testing, and production builds for public release. Keep your `eas.json` profiles organized and document their intended use.


## Conclusion: The First Step Into Native Land

Running `eas build` for the first time marks a milestone—you’re no longer limited to Expo Go, but working with real native binaries. Installing and testing your Dev Client gives you confidence that your app will run as expected outside the sandbox.

**Key Takeaways:**

- EAS builds unlock custom native code and real-world testing.
- Dev, preview, and production builds serve different purposes—use them wisely.
- Always test on real devices before releasing to users.

In the next chapter, we’ll connect your Dev Client to Metro more deeply, exploring tunnels, hotspots, and USB fallback methods to keep your feedback loop fast and reliable.

---
