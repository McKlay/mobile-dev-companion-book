---
hide:
  - toc
---

# Chapter 11: Where to Go Next

---

Reaching this point means you’ve built, styled, debugged, and even deployed native builds of your app. But mobile development doesn’t end at “it runs.” The real growth comes from pushing your apps further—adding richer navigation, accessing device capabilities, and preparing them for the rigor of app store deployment. This chapter points you toward those next steps.

## Adding Navigation and Advanced UI

### React Navigation

Most real apps need more than a single screen. **React Navigation** is the go-to library for handling stacks, tabs, and drawer navigation in React Native.

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
````

With this, you can transition between screens just like native apps do, complete with smooth animations.

### Advanced Styling with NativeWind

If you’ve used Tailwind on the web, **NativeWind** lets you carry over that same utility-first styling into React Native. Combined with React Navigation, it enables building polished UIs quickly, without drowning in verbose style objects.

---

## Camera, File Upload, and Native APIs

### Accessing the Camera

Using Expo SDK modules, you can integrate device features like the camera:

```tsx
import { CameraView } from 'expo-camera';

<CameraView style={{ flex: 1 }} />
```

From barcode scanning to document capture, the camera is one of the most common native integrations.

### File Uploads

With libraries like `expo-document-picker` or `expo-image-picker`, you can let users upload files or images. This is often paired with backend APIs to store or process the uploaded data.

### Beyond Expo SDK

At some point, you’ll outgrow Expo’s built-in modules. That’s when Dev Clients and custom native modules become essential, giving you access to the full range of platform-specific APIs.

---

## Preparing for Play Store and App Store Deployment

### The Reality of Store Guidelines

Unlike web apps, mobile apps must pass through review processes before users can install them. Both Google Play and Apple’s App Store have strict requirements around app quality, privacy, and design.

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

3. Address any review feedback and resubmit as needed.

### Best Practices

* Prepare polished icons and splash screens.
* Test thoroughly on both iOS and Android devices.
* Follow platform-specific UI/UX conventions for better acceptance chances.

---

## Conclusion: The Path Forward

The journey from web developer comfort zones to deploying full-fledged mobile apps is challenging but deeply rewarding. With React Native, Expo, and EAS, you’ve learned how to build, test, debug, and ship apps that run on real devices.

From here, your growth depends on practice and exploration: build side projects, experiment with native APIs, and eventually push into areas like performance optimization, offline-first design, or even integrating AI models into your mobile apps.

This book has given you a foundation—now it’s up to you to expand it, one app at a time.

---
