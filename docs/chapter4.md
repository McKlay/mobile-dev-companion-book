---
hide:
  - toc
---

# Chapter 4: Running Your App on Web and Device

---

After scaffolding your first Expo project, the next natural step is to see it in action. Unlike the web, where you simply refresh a browser tab, mobile development involves simulators, physical devices, and even browsers for testing. This chapter walks you through Expo’s development workflow, explains Fast Refresh and Live Reload, and helps you decide when to use Expo Go versus a custom Dev Client.

## Fast Refresh & Live Reload Basics

### The Developer Feedback Loop

In web projects, you’re used to hitting save and seeing instant changes in your browser. Expo provides a similar experience through **Fast Refresh** and **Live Reload**:

* **Fast Refresh**: Only re-renders the files you edited, preserving app state when possible. For example, editing the text inside a component updates the UI instantly without losing the current screen.  
* **Live Reload**: Reloads the entire app when files change, ensuring a full refresh but resetting state. Useful if you make structural changes that Fast Refresh can’t handle.  

These tools make mobile development feel much closer to web development—fast, iterative, and forgiving.

### Example in Action

1. Run your app with:

   ```bash
   npm start
````

2. Open it on your device or simulator.
3. Edit `App.js`—for example, change the default text.

Your changes appear within seconds, either preserving your current screen (Fast Refresh) or fully reloading (Live Reload).

## Running with Expo Go on Physical Devices

### What is Expo Go?

Expo Go is a sandbox app available on the **App Store** and **Google Play**. It lets you open your project instantly by scanning a QR code from the terminal or Expo Developer Tools in your browser. No builds, no Xcode, no Android Studio required.

### Workflow

1. Install Expo Go on your phone.

2. Run:

   ```bash
   npm start
   ```

3. Scan the QR code with Expo Go.

4. Your project runs on your actual device.

This workflow is invaluable for testing touch, camera, and performance on real hardware.

### Limitations of Expo Go

While Expo Go is fantastic for quick iteration, it only supports modules included in the Expo SDK. If you need custom native code or third-party modules not in the SDK, you’ll need to move to a **Dev Client**.

## When and Why to Switch to Dev Client

### Dev Client Defined

A **Dev Client** is a custom build of your app with Expo’s development runtime and any extra native modules you include. It bridges the gap between the ease of Expo Go and the flexibility of full native builds.

### When to Use It

* You’ve installed a native dependency not supported by Expo Go (e.g., advanced Bluetooth, payments, AR libraries).
* You need to debug issues closer to the native layer.
* You’re preparing for production and want a build that mirrors your final app.

### How to Get It

You’ll create Dev Clients using **EAS Build**, which we’ll cover in detail in Part IV. For now, just remember: Expo Go is for speed, Dev Client is for power.

## Conclusion: Testing Across Web and Device

In this chapter, you learned how Expo’s feedback loop keeps development smooth with Fast Refresh and Live Reload. You saw how Expo Go enables real-device testing without heavy setup, and when to graduate to Dev Client builds. With these tools, your workflow is flexible: iterate quickly, test broadly, and escalate only when necessary.

This concludes Part II. In the next part, we’ll face the unavoidable realities of mobile development—dependency hell—and learn how to survive it with the right tools and mindset.

---