---
hide:
  - toc
---

# Chapter 1: Why Mobile Feels Different from Web

---


Before diving into code and project scaffolding, it’s worth pausing to reflect on why building for mobile feels fundamentally different from building for the web. Many developers enter React Native with strong React or JavaScript backgrounds, expecting a smooth continuation of familiar workflows. Yet, the mobile world comes with its own constraints, philosophies, and technical nuances that can surprise even seasoned web developers.

This chapter explores the mindset shift required for mobile development, explains how React Native bridges the gap between JavaScript and native UI, and clarifies Expo’s role in making the developer journey smoother and more productive. By the end, you’ll have a solid foundation for understanding the unique challenges and opportunities of mobile app development.

## The Web vs. Mobile Mindset Shift

### The Web Developer’s Comfort Zone


On the web, developers are accustomed to a fast feedback loop: save your file, refresh the browser, and see immediate results. Browsers handle a remarkable amount of complexity for you—cross-platform rendering, network requests, caching, and even responsive design through CSS. You rarely need to worry about what’s happening under the hood of the operating system. The browser acts as a universal runtime, abstracting away most hardware and OS differences. If your site works in Chrome, it probably works in Firefox and Safari with only minor tweaks.

**Example:**

- You update a CSS file, hit refresh, and instantly see the new color scheme. If something breaks, browser dev tools help you debug in real time.

### Mobile Reality


Mobile apps, however, operate under a very different set of constraints and expectations:

- **Performance budgets** are much tighter—phones have limited memory, battery, and CPU. Every animation, image, and network request can impact battery life and responsiveness. Unlike desktops, mobile devices can’t rely on abundant resources.
- **Platform guidelines** (iOS Human Interface Guidelines, Android Material Design) shape how apps should look and behave. Users expect apps to feel “at home” on their device, following conventions for navigation, gestures, and visual design. Deviating from these can make your app feel awkward or untrustworthy.
- **Native APIs**—from the camera to GPS to push notifications—require bridging between JavaScript and the host OS. Accessing these features means understanding permissions, privacy, and sometimes writing native code.
- **Distribution** happens through app stores, with review processes and update cycles that don’t exist on the open web. Updates can take days to reach users, and every release must pass automated and human review for security, privacy, and content.
- **Offline and network variability** are the norm. Mobile users may have spotty connections, so apps must gracefully handle offline states and slow networks.

These differences demand a shift in mindset: you’re not just rendering UI anymore—you’re building for an ecosystem with strict rules, real-world limitations, and user expectations shaped by years of polished native apps.

**Example:**

- A simple image carousel that works smoothly on the web might stutter or drain battery on a low-end phone if not optimized. A button that’s too small or placed in the wrong spot could be rejected by Apple’s App Store for violating usability guidelines.

## React Native: Bridging JavaScript and Native UI

### The Bridge Concept


React Native enables developers to write JavaScript (and often TypeScript) while rendering native UI components under the hood. Unlike hybrid frameworks that simply embed a web browser in a native shell, React Native uses a “bridge” to connect your JavaScript logic to native modules. This means your app’s UI is composed of real native widgets, not HTML elements.

**How the Bridge Works:**

- Your JavaScript code runs in a separate thread (the JS thread), while the UI is rendered by the native platform (the main thread).
- When you update state or props in React, React Native sends messages across the bridge to update the native UI components.
- The bridge is asynchronous, which helps performance but can introduce bottlenecks if too much data is sent at once.

**Component Mapping Examples:**

- A `<Text>` component maps to a **UILabel** on iOS or a **TextView** on Android.
- A `<View>` translates to **UIView** (iOS) or **ViewGroup** (Android).
- A `<ScrollView>` becomes a native scrollable container, with platform-specific behaviors like bounce on iOS.

This approach ensures apps feel *native* in performance and look, while letting you leverage the reactivity of React. You get the best of both worlds: fast iteration with JavaScript and the polish of native UI.

### Benefits and Trade-offs


**Pros:**

- **Shared codebase:** Write once, deploy to both iOS and Android, reducing duplication and maintenance.
- **Strong React ecosystem:** Leverage React patterns, libraries, and community knowledge.
- **Faster iteration:** Hot reloading and fast refresh make UI tweaks and bug fixes quick.
- **Native performance:** UI components are rendered natively, not in a web view.

**Cons:**

- **Bridge bottlenecks:** Heavy or frequent communication between JS and native can cause performance issues, especially for animations or large data transfers.
- **Native module compatibility:** Some device features or third-party SDKs may require custom native code or may not be fully supported.
- **Ecosystem health:** React Native is actively maintained, but breaking changes or deprecated libraries can cause upgrade headaches.

Understanding this bridge model is crucial—it helps developers appreciate both the power and limitations of React Native. For most apps, the benefits far outweigh the trade-offs, but it’s important to know where the boundaries are.

## Understanding Expo’s Role

### Why Expo Exists


Expo sits on top of React Native, smoothing out many of the pain points new developers encounter. Instead of wrestling with Xcode or Android Studio configurations just to run a “Hello World” app, Expo provides a managed workflow that abstracts away much of the native complexity.

**Expo’s Key Features:**

- **Expo SDK:** Prebuilt modules for camera, notifications, sensors, authentication, and more. These modules are maintained and updated by the Expo team, reducing the need to write or maintain native code yourself.
- **Expo Go app:** A lightweight app you can install from the App Store or Google Play. It lets you preview your project instantly on a real device by scanning a QR code—no compiling or device provisioning required.
- **Unified tooling:** Commands like `npx create-expo-app` and `npx expo start` simplify project setup, development, and deployment. Expo CLI handles bundling, asset management, and even over-the-air updates.
- **EAS (Expo Application Services):** When you’re ready for advanced features—like custom native code, app store builds, or push notifications—EAS provides cloud-based build and deployment services.

**Example:**

- With Expo, you can build and share a prototype with a client in minutes, without ever opening Xcode or Android Studio.

### Developer Experience Gains


For beginners, Expo provides a sandboxed environment that just works—no need to install heavy IDEs or configure emulators. You can focus on learning React Native and building features, not fighting build errors.

For professionals, Expo streamlines prototyping and accelerates iteration. Teams can share QR codes to preview work, push updates over the air, and collaborate without worrying about local environment mismatches.

Eventually, when advanced customization is needed (such as integrating a custom native module or SDK), you can “eject” from the managed workflow to a bare React Native project, or use EAS to handle custom builds in the cloud.

## Conclusion: The Foundation Laid


This opening chapter laid out why building for mobile differs from the web, how React Native enables JavaScript developers to step into native app development, and how Expo lowers the barrier to entry. Understanding these three pillars—the mindset shift, the React Native bridge, and Expo’s role—sets the stage for exploring the Expo ecosystem in detail in the next chapter.

As you move forward, keep these differences in mind. Mobile development is a rewarding journey, but it requires new habits, attention to detail, and a willingness to learn platform conventions. With React Native and Expo, you have powerful tools to bridge the gap between web and mobile, making it easier than ever to build high-quality apps for millions of users.

---
