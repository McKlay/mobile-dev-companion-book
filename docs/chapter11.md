---
hide:
  - toc
---

# Chapter 11: Where to Go Next

---


Reaching this point means you’ve built, styled, debugged, and even deployed native builds of your app. But mobile development doesn’t end at “it runs.” The real growth comes from pushing your apps further—adding richer navigation, accessing device capabilities, and preparing them for the rigor of app store deployment. This chapter points you toward those next steps and offers guidance for leveling up your skills, building production-ready features, and exploring the broader React Native ecosystem.


## Adding Navigation and Advanced UI

### React Navigation

Most real apps need more than a single screen. **React Navigation** is the go-to library for handling stacks, tabs, and drawer navigation in React Native. It supports deep linking, custom transitions, and integration with device navigation gestures.

Example setup for a stack navigator:

```tsx
import { createNativeStackNavigator } from '@react-navigation/native-stack';
import { NavigationContainer } from '@react-navigation/native';

const Stack = createNativeStackNavigator();

export default function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator>
        <Stack.Screen name="Home" component={HomeScreen} />
        <Stack.Screen name="Details" component={DetailScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}
```

With this, you can transition between screens just like native apps do, complete with smooth animations, header customization, and back navigation. Explore tab and drawer navigators for more complex flows.

**Tip:** Use the React Navigation docs for recipes on authentication flows, nested navigation, and custom headers.

### Advanced Styling with NativeWind

If you’ve used Tailwind on the web, **NativeWind** lets you carry over that same utility-first styling into React Native. Combined with React Navigation, it enables building polished UIs quickly, without drowning in verbose style objects. You can create reusable components, theme your app, and keep your styles consistent across platforms.

---


## Camera, File Upload, and Native APIs

### Accessing the Camera

Using Expo SDK modules, you can integrate device features like the camera:

```tsx
import { CameraView } from 'expo-camera';

<CameraView style={{ flex: 1 }} />
```

From barcode scanning to document capture, the camera is one of the most common native integrations. You can also use the camera for profile photos, AR features, or real-time video processing.

**Tip:** Always request permissions before accessing sensitive device features.

### File Uploads

With libraries like `expo-document-picker` or `expo-image-picker`, you can let users upload files or images. This is often paired with backend APIs to store or process the uploaded data. Consider using `expo-media-library` for gallery access and `expo-file-system` for advanced file handling.

### Beyond Expo SDK

At some point, you’ll outgrow Expo’s built-in modules. That’s when Dev Clients and custom native modules become essential, giving you access to the full range of platform-specific APIs. You can integrate third-party SDKs, custom Bluetooth, push notifications, or even native UI components.

**Best Practice:** Start with Expo SDK for rapid prototyping, then migrate to custom modules as your needs grow.

---


## Preparing for Play Store and App Store Deployment

### The Reality of Store Guidelines

Unlike web apps, mobile apps must pass through review processes before users can install them. Both Google Play and Apple’s App Store have strict requirements around app quality, privacy, and design. Expect to address privacy policies, permissions, and content guidelines.

**Common reasons for rejection:**

- Missing or low-quality icons and splash screens
- Incomplete privacy disclosures
- Crashes or unresponsive UI
- Use of unsupported APIs or permissions

### Deployment Workflow

1. Build production-ready binaries with EAS:

  ```bash
  eas build -p android --profile production
  eas build -p ios --profile production
  ```

2. Submit builds directly using EAS Submit:

  ```bash
  eas submit -p android
  eas submit -p ios
  ```

3. Address any review feedback and resubmit as needed. Keep an eye on review timelines and communicate with your team or stakeholders.

### Best Practices

- Prepare polished icons and splash screens (in all required sizes).
- Test thoroughly on both iOS and Android devices, including edge cases and offline scenarios.
- Follow platform-specific UI/UX conventions for better acceptance chances.
- Read the latest App Store and Play Store guidelines before submitting.
- Automate builds and submissions with EAS for consistency and speed.

---


## Conclusion: The Path Forward

The journey from web developer comfort zones to deploying full-fledged mobile apps is challenging but deeply rewarding. With React Native, Expo, and EAS, you’ve learned how to build, test, debug, and ship apps that run on real devices.

**Where to go next:**

- Build side projects to solidify your skills and explore new patterns.
- Experiment with native APIs, animations, and device integrations.
- Dive into performance optimization, offline-first design, and accessibility.
- Explore advanced topics like push notifications, background tasks, and integrating AI models.
- Join the React Native and Expo communities for support, updates, and inspiration.

This book has given you a foundation—now it’s up to you to expand it, one app at a time. Keep building, keep learning, and enjoy the journey!

---
