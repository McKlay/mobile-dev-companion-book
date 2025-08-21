---
hide:
  - toc
---

# Chapter 8: Your First Native Build

---

After setting up EAS, it’s time to cross the threshold from Expo Go into the world of true native builds. This chapter will guide you through creating your first native build using EAS, installing it on your device, and understanding the differences between dev, preview, and production builds.

## Running `eas build -p android --profile development`

### Starting with Android

We’ll begin with Android, since generating an APK is often the fastest way to see your app outside Expo Go. From your project root, run:

```bash
eas build -p android --profile development
````

Here’s what this command does:

* **`-p android`** → Targets Android platform.
* **`--profile development`** → Uses the `development` profile from `eas.json`.

EAS will upload your project, run the build in the cloud, and provide a download link once it’s ready.

### First-Time Prompts

On your first run, EAS may ask you about credentials (keystore for Android, provisioning profiles for iOS). Expo can manage these for you automatically, which is ideal when starting out.

## Installing and Testing the Dev Client APK

Once the build is complete, you’ll get a link to download the APK. Install it on your device:

* On Android → Open the link in your browser and install the APK directly.
* On iOS → You’ll need to use a simulator or TestFlight (since direct sideloading is restricted).

When you open the Dev Client app, it will look like your project but with one major difference: it can now load **custom native modules** beyond what Expo Go supports.

### Testing Workflow

1. Run your Metro bundler in Dev Client mode:

   ```bash
   expo start --dev-client
   ```

2. Open the Dev Client app.

3. Connect it to Metro using the QR code or deep link.

At this point, your app is running in a build that mirrors production more closely.

## Differences Between Dev, Preview, and Production Builds

### Development Builds

* Includes debugging tools and development menus.
* Great for local testing with custom native modules.
* Distributed internally—never to actual users.

### Preview Builds

* Used for testers or staging environments.
* Distribution is internal, but optimized more like production.
* Often used before final release.

### Production Builds

* Optimized, signed, and ready for app stores.
* No developer menus or debugging overlays.
* Must meet store requirements (icons, splash screens, signing keys).

Knowing which profile to use keeps your workflow smooth: dev for building features, preview for testing with colleagues, and production for the real release.

## Conclusion: The First Step Into Native Land

Running `eas build` for the first time marks a milestone—you’re no longer limited to Expo Go, but working with real native binaries. Installing and testing your Dev Client gives you confidence that your app will run as expected outside the sandbox.

In the next chapter, we’ll connect your Dev Client to Metro more deeply, exploring tunnels, hotspots, and USB fallback methods to keep your feedback loop fast and reliable.

---
