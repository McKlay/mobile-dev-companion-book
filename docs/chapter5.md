---
hide:
  - toc
---

# Chapter 5: Library Compatibility Issues

---

If you spend enough time building with React Native and Expo, you’ll eventually encounter what developers lovingly call **“dependency hell.”** It’s that moment when you install a library, eager to test a new feature, only to be greeted by walls of cryptic red errors. Unlike the web, where most packages are pure JavaScript, mobile libraries often involve **native code bindings**, and this is where things get messy.

In this chapter, we’ll explore why some libraries cause more problems than others, how Expo’s tooling helps you keep versions aligned, and how to interpret errors so you don’t get lost in the chaos.

## Common Problem Packages

### The Case of `react-native-reanimated`

One of the most powerful libraries in the ecosystem, `react-native-reanimated`, allows for buttery-smooth animations by running code directly on the native thread. But because it sits so close to the native layer, it is often **sensitive to version mismatches**.

Symptoms of version issues:  

* Blank screens when running animations.  
* Metro errors like *“Cannot find node in UIManager”*.  
* Build failures on iOS/Android when versions don’t align.  

### `react-native-gesture-handler`

Another essential yet finicky package is `react-native-gesture-handler`. It underpins navigation and complex touch gestures in React Native apps. Like `reanimated`, it often breaks if you mix incompatible versions with React Native or Expo.

Symptoms:  

* Crashes when navigating between screens.  
* Errors such as *“Module not found: GestureHandler”*.  
* Gestures silently failing without logs.  

Together, these two libraries account for a large portion of developer headaches—but they’re also indispensable. Mastering them is part of the journey.

## Expo’s Safety Nets: `expo install`

A common pitfall for beginners is using `npm install` or `yarn add` directly when adding libraries. While this works fine on the web, it can backfire in React Native because not all versions of a package are compatible with your current Expo/React Native version.

Instead, use:

```bash
expo install react-native-reanimated
````

Unlike `npm install`, this command automatically installs the **correct version** aligned with your current Expo SDK. Think of it as Expo’s built-in guardrail against version mismatches.

## Checking Health with `expo-doctor`

When things still go wrong (and they will), `expo-doctor` is your friend:

```bash
npx expo-doctor
```

This command scans your project for dependency mismatches, incompatible native modules, and other red flags. It doesn’t fix everything automatically, but it gives you a roadmap of what’s broken.

Example output might look like:

```
[WARN] react-native-reanimated@3.4.2 expected, found 3.3.0
[ERROR] expo-sqlite is missing native module bindings
```

From there, you’ll know whether to upgrade, downgrade, or reinstall a package.

## How to Interpret Metro’s Red Errors

### The Panic Moment

Metro errors often feel like they’re yelling at you: giant red screens with long stack traces. The key is to **slow down** and read them carefully.

For example:

```
Error: Reanimated 3 failed to create a worklet, maybe you forgot to add Reanimated's babel plugin?
```

The fix is often hidden in the error itself—in this case, adding the plugin to `babel.config.js`.

### Debugging Mindset

* **Step 1:** Ask: Is this a JavaScript-only package or does it bridge into native code?
* **Step 2:** If native, check version alignment with `expo install`.
* **Step 3:** Run `expo-doctor` to confirm mismatches.
* **Step 4:** Clear caches (`npx expo start -c`) before retrying.

Most issues can be resolved with patience and version discipline.

## Conclusion: Taming the Beast

Dependency hell isn’t a bug—it’s a feature of working with a diverse ecosystem that blends JavaScript with native code. By recognizing common offenders, relying on Expo’s `expo install` guardrails, and using `expo-doctor` for diagnosis, you’ll transform frustration into a manageable process.

In the next chapter, we’ll dive deeper into the tooling behind the scenes—Babel and Metro—so you understand why some errors appear and how the development pipeline really works.

---