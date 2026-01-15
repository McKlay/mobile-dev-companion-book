---
hide:
  - toc
---

# Chapter 5: Library Compatibility Issues

---


If you spend enough time building with React Native and Expo, you’ll eventually encounter what developers lovingly call **“dependency hell.”** It’s that moment when you install a library, eager to test a new feature, only to be greeted by walls of cryptic red errors. Unlike the web, where most packages are pure JavaScript, mobile libraries often involve **native code bindings**, and this is where things get messy.

In this chapter, we’ll explore why some libraries cause more problems than others, how Expo’s tooling helps you keep versions aligned, and how to interpret errors so you don’t get lost in the chaos. You’ll also learn strategies for debugging, best practices for dependency management, and how to keep your project healthy as it grows.


## Common Problem Packages

Some libraries are more likely to cause trouble than others, especially those that bridge JavaScript and native code. Understanding which packages are "high risk" helps you plan upgrades and debug issues more effectively.

### The Case of `react-native-reanimated`

One of the most powerful libraries in the ecosystem, `react-native-reanimated`, allows for buttery-smooth animations by running code directly on the native thread. But because it sits so close to the native layer, it is often **sensitive to version mismatches** and build configuration issues.

**Symptoms of version issues:**

- Blank screens when running animations.
- Metro errors like *“Cannot find node in UIManager”* or *“Reanimated 3 failed to create a worklet”*.
- Build failures on iOS/Android when versions don’t align.
- Warnings about missing Babel plugins or incompatible API usage.

**Best Practices:**

- Always use `expo install` to add or update this package.
- Double-check that the Babel plugin is configured in `babel.config.js`.
- After changes, clear caches with `npx expo start -c`.

### `react-native-gesture-handler`

Another essential yet finicky package is `react-native-gesture-handler`. It underpins navigation and complex touch gestures in React Native apps. Like `reanimated`, it often breaks if you mix incompatible versions with React Native or Expo.

**Symptoms:**

- Crashes when navigating between screens.
- Errors such as *“Module not found: GestureHandler”* or *“undefined is not an object (evaluating 'RNGestureHandlerModule.Direction')”*.
- Gestures silently failing without logs.

**Best Practices:**

- Use `expo install` to ensure version alignment.
- Follow the official setup instructions for linking and configuration.

Together, these two libraries account for a large portion of developer headaches—but they’re also indispensable. Mastering them is part of the journey. Other common offenders include camera, maps, and Bluetooth libraries.


## Expo’s Safety Nets: `expo install`

A common pitfall for beginners is using `npm install` or `yarn add` directly when adding libraries. While this works fine on the web, it can backfire in React Native because not all versions of a package are compatible with your current Expo/React Native version.

**Why is this a problem?**

- The React Native ecosystem moves fast, and native APIs change frequently.
- Expo SDK versions are tightly coupled to specific versions of React Native and popular libraries.

**Solution:**

Instead, use:

```bash
expo install react-native-reanimated
```

Unlike `npm install`, this command automatically installs the **correct version** aligned with your current Expo SDK. Think of it as Expo’s built-in guardrail against version mismatches. It works for all Expo-compatible packages, not just the Expo SDK itself.

**Tip:** If you’re ever unsure, run `expo install` for any package you want to add or update.


## Checking Health with `expo-doctor`

When things still go wrong (and they will), `expo-doctor` is your friend:

```bash
npx expo-doctor
```

This command scans your project for dependency mismatches, incompatible native modules, and other red flags. It doesn’t fix everything automatically, but it gives you a roadmap of what’s broken and what needs attention.

**Example output:**

```
[WARN] react-native-reanimated@3.4.2 expected, found 3.3.0
[ERROR] expo-sqlite is missing native module bindings
```

From there, you’ll know whether to upgrade, downgrade, or reinstall a package. `expo-doctor` is especially useful after upgrading Expo SDK versions or adding new native dependencies.


## How to Interpret Metro’s Red Errors

### The Panic Moment

Metro errors often feel like they’re yelling at you: giant red screens with long stack traces. The key is to **slow down** and read them carefully. Most errors contain clues about what went wrong and how to fix it.

For example:

```
Error: Reanimated 3 failed to create a worklet, maybe you forgot to add Reanimated's babel plugin?
```

The fix is often hidden in the error itself—in this case, adding the plugin to `babel.config.js`.

**Other common error types:**

- "Invariant Violation": Usually a missing or misconfigured dependency.
- "Module not found": A package is missing or not linked correctly.
- "Native module cannot be null": The native code for a library isn’t installed or built.

### Debugging Mindset

* **Step 1:** Ask: Is this a JavaScript-only package or does it bridge into native code?
* **Step 2:** If native, check version alignment with `expo install`.
* **Step 3:** Run `expo-doctor` to confirm mismatches.
* **Step 4:** Clear caches (`npx expo start -c`) before retrying.
* **Step 5:** Search the error message online—chances are, someone else has hit it before.

Most issues can be resolved with patience, version discipline, and careful reading of error messages.


## Conclusion: Taming the Beast

Dependency hell isn’t a bug—it’s a feature of working with a diverse ecosystem that blends JavaScript with native code. By recognizing common offenders, relying on Expo’s `expo install` guardrails, and using `expo-doctor` for diagnosis, you’ll transform frustration into a manageable process.

**Best Practices Recap:**

- Use `expo install` for all dependencies.
- Run `expo-doctor` after major changes.
- Read Metro errors carefully and search for solutions.
- Keep your Expo SDK and libraries up to date, but upgrade cautiously.
- Document fixes and workarounds for your team.

In the next chapter, we’ll dive deeper into the tooling behind the scenes—Babel and Metro—so you understand why some errors appear and how the development pipeline really works.

---