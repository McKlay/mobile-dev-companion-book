---
hide:
  - toc
---

# Chapter 4: Running Your App on Web and Device

---


After scaffolding your first Expo project, the next natural step is to see it in action. Unlike the web, where you simply refresh a browser tab, mobile development involves simulators, physical devices, and even browsers for testing. Expo bridges these worlds, letting you iterate quickly and test broadly. This chapter walks you through Expo’s development workflow, explains Fast Refresh and Live Reload, and helps you decide when to use Expo Go versus a custom Dev Client. You’ll also learn best practices for testing on both web and device, and how to debug efficiently.


## Fast Refresh & Live Reload Basics

### The Developer Feedback Loop

In web projects, you’re used to hitting save and seeing instant changes in your browser. Expo provides a similar experience through **Fast Refresh** and **Live Reload**:

- **Fast Refresh**: Only re-renders the files you edited, preserving app state when possible. For example, editing the text inside a component updates the UI instantly without losing the current screen. This is ideal for tweaking UI, fixing typos, or adjusting logic without losing your place in the app.
- **Live Reload**: Reloads the entire app when files change, ensuring a full refresh but resetting state. Useful if you make structural changes that Fast Refresh can’t handle, such as editing navigation or configuration files.

These tools make mobile development feel much closer to web development—fast, iterative, and forgiving. You can experiment, break things, and recover quickly.

**Tip:** You can toggle Fast Refresh and Live Reload from the Expo Developer Tools in your browser or from the in-app developer menu (shake your device or press `d` in the terminal).


### Example in Action

1. Run your app with:

   ```bash
   npm start
   ```

2. Open it on your device, simulator, or web browser (press `w` for web, `a` for Android, `i` for iOS simulator).
3. Edit `App.js`—for example, change the default text or add a new component.

Your changes appear within seconds, either preserving your current screen (Fast Refresh) or fully reloading (Live Reload). This rapid feedback loop is essential for productive mobile development.


## Running with Expo Go on Physical Devices

### What is Expo Go?

Expo Go is a sandbox app available on the **App Store** and **Google Play**. It lets you open your project instantly by scanning a QR code from the terminal or Expo Developer Tools in your browser. No builds, no Xcode, no Android Studio required. It includes all Expo SDK modules, so you can test most features instantly.

### Workflow

1. Install Expo Go on your phone (search "Expo Go" in your app store).
2. Run:

   ```bash
   npm start
   ```

3. Scan the QR code with Expo Go (from the terminal or browser window).
4. Your project runs on your actual device, with hot reloading and debugging tools available.

This workflow is invaluable for testing touch, camera, and performance on real hardware. You can share the QR code with teammates or clients for instant previews.

**Tip:** You can also run your app in a web browser with `npm run web` or by pressing `w` in the Expo CLI.

### Limitations of Expo Go

While Expo Go is fantastic for quick iteration, it only supports modules included in the Expo SDK. If you need custom native code or third-party modules not in the SDK, you’ll need to move to a **Dev Client**. Expo Go is not suitable for testing features like custom Bluetooth, payments, or AR libraries.


## When and Why to Switch to Dev Client

### Dev Client Defined

A **Dev Client** is a custom build of your app with Expo’s development runtime and any extra native modules you include. It bridges the gap between the ease of Expo Go and the flexibility of full native builds. You get the same fast feedback loop, but with support for custom native code and third-party libraries.

### When to Use It

- You’ve installed a native dependency not supported by Expo Go (e.g., advanced Bluetooth, payments, AR libraries).
- You need to debug issues closer to the native layer (e.g., native crashes, device-specific bugs).
- You’re preparing for production and want a build that mirrors your final app, including all customizations.

**Example:** If you add a library like `react-native-maps` or a custom camera module, you’ll need a Dev Client to test those features.

### How to Get It

You’ll create Dev Clients using **EAS Build**, which we’ll cover in detail in Part IV. For now, just remember: Expo Go is for speed, Dev Client is for power and flexibility. EAS Build lets you generate custom clients in the cloud, install them on your device, and continue developing with hot reloading.


## Conclusion: Testing Across Web and Device

In this chapter, you learned how Expo’s feedback loop keeps development smooth with Fast Refresh and Live Reload. You saw how Expo Go enables real-device testing without heavy setup, and when to graduate to Dev Client builds for advanced features. With these tools, your workflow is flexible: iterate quickly, test broadly, and escalate only when necessary.

**Best Practices:**

- Test on both simulators and real devices to catch platform-specific issues.
- Use Fast Refresh for UI tweaks, Live Reload for bigger changes.
- Share QR codes for easy collaboration and feedback.
- Switch to Dev Client as soon as you need custom native code.

This concludes Part II. In the next part, we’ll face the unavoidable realities of mobile development—dependency hell—and learn how to survive it with the right tools and mindset.

---