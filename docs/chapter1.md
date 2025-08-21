---
hide:
  - toc
---

# Chapter 1: Why Mobile Feels Different from Web

---

Before diving into code and project scaffolding, it’s worth pausing to reflect on why building for mobile feels fundamentally different from building for the web. Many developers enter React Native with strong React or JavaScript backgrounds, expecting a smooth continuation of familiar workflows. Yet, the mobile world comes with its own constraints, philosophies, and technical nuances. This chapter explores that mindset shift, introduces how React Native serves as a bridge between JavaScript and native UI, and clarifies Expo’s role in easing the developer journey.

## The Web vs. Mobile Mindset Shift

### The Web Developer’s Comfort Zone

On the web, developers are accustomed to a fast feedback loop: save your file, refresh the browser, and see immediate results. Browsers handle a remarkable amount of complexity for you—cross-platform rendering, network requests, caching, and even responsive design through CSS. You rarely need to worry about what’s happening under the hood of the operating system.

### Mobile Reality

Mobile apps, however, operate under different constraints:  

* **Performance budgets** are tighter—phones have limited memory, battery, and CPU.  
* **Platform guidelines** (iOS Human Interface Guidelines, Android Material Design) shape how apps should look and behave.  
* **Native APIs**—from the camera to GPS to push notifications—require bridging between JavaScript and the host OS.  
* **Distribution** happens through app stores, with review processes and update cycles that don’t exist on the open web.  

These differences demand a shift in mindset: you’re not just rendering UI anymore—you’re building for an ecosystem with strict rules and real-world limitations.

## React Native: Bridging JavaScript and Native UI

### The Bridge Concept

React Native enables developers to write JavaScript (and often TypeScript) while rendering native UI components under the hood. Instead of shipping a web view inside an app, React Native uses a “bridge” to connect your JavaScript logic to native modules. For example:  

* A `<Text>` component maps to a **UILabel** on iOS or a **TextView** on Android.  
* A `<View>` translates to **UIView** (iOS) or **ViewGroup** (Android).  

This approach ensures apps feel *native* in performance and look, while letting you leverage the reactivity of React.

### Benefits and Trade-offs

* **Pros**: Shared codebase across iOS/Android, strong React ecosystem, quicker iteration.  
* **Cons**: Occasional “bridge bottlenecks,” compatibility issues with some native libraries, and reliance on the health of the React Native ecosystem.  

Understanding this bridge model is crucial—it helps developers appreciate both the power and limitations of React Native.

## Understanding Expo’s Role

### Why Expo Exists

Expo sits on top of React Native, smoothing out many of the pain points new developers encounter. Instead of wrestling with Xcode or Android Studio configurations just to run a “Hello World” app, Expo provides:  

* **Expo SDK** – prebuilt modules for camera, notifications, sensors, and more.  
* **Expo Go app** – a lightweight way to preview your app instantly on a physical device without compiling native code.  
* **Unified tooling** – commands like `npx create-expo-app` simplify project setup.  

### Developer Experience Gains

For beginners, Expo provides a sandboxed environment that just works. For professionals, it streamlines prototyping and accelerates iteration. Eventually, when advanced customization is needed, you can “eject” to full native builds or transition into using **Expo Application Services (EAS)**.

## Conclusion: The Foundation Laid

This opening chapter laid out why building for mobile differs from the web, how React Native enables JavaScript developers to step into native app development, and how Expo lowers the barrier to entry. Understanding these three pillars—the mindset shift, the React Native bridge, and Expo’s role—sets the stage for exploring the Expo ecosystem in detail in the next chapter.

---
