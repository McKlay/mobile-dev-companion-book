---
hide:
  - toc
---

## **Mobile Dev Builder’s Companion Book**
### From React Native to Expo & EAS — a guide to building and deploying mobile apps

---

### **Contents**

---

#### 📖 [Preface](Preface.md)

- [Why This Book Exists](Preface.md#why-this-book-exists)

- [Who Should Read This](Preface.md#who-should-read-this)

- [From Web Comfort to Mobile Reality](Preface.md#from-web-comfort-to-mobile-reality)

- [What You’ll Learn (and What You Won’t)](Preface.md#what-youll-learn-and-what-you-wont)

- [How to Read This Book](Preface.md#how-to-read-this-book)

---

#### Part I – [Foundations of Cross-Platform Mobile Development](PartI_overview.md)

     Chapter 1: [Why Mobile Feels Different from Web](chapter1.md)  
        1.1 Web vs. mobile mindset shift  
        1.2 React Native as the bridge between JavaScript and native UI  
        1.3 Understanding Expo’s role  

     Chapter 2: [The Expo Ecosystem](chapter2.md)  
        2.1 Expo SDK and its prebuilt modules  
        2.2 Metro bundler explained  
        2.3 Expo Go vs Dev Client vs Production  

---

#### Part II – [Getting Started with Your First Project](PartII_overview.md)

     Chapter 3: [Scaffolding a React Native App](chapter3.md)  
        3.1 Using `create-expo-app`  
        3.2 Project structure explained  
        3.3 Adding Tailwind with NativeWind  

     Chapter 4: [Running Your App on Web and Device](chapter4.md)  
        4.1 Fast Refresh & Live Reload basics  
        4.2 Running with Expo Go on physical devices  
        4.3 When and why to switch to Dev Client  

---

#### Part III – [Surviving Dependency Hell](PartIII_overview.md)

     Chapter 5: [Library Compatibility Issues](chapter5.md)  
        5.1 Common problem packages (`react-native-reanimated`, `gesture-handler`)  
        5.2 Using `expo-doctor` and `expo install`  
        5.3 How to interpret red Metro errors  

     Chapter 6: [Babel, Metro, and You](chapter6.md)  
        6.1 What Babel does in React Native projects  
        6.2 Metro bundler workflow (port 8081)  
        6.3 Hot reload vs full reload  

---

#### Part IV – [Building Natively with EAS](PartIV_overview.md)

     Chapter 7: [Introduction to EAS (Expo Application Services)](chapter7.md)  
        7.1 Why Expo Go is not enough  
        7.2 Installing and configuring EAS CLI  
        7.3 Understanding `eas.json` build profiles  

     Chapter 8: [Your First Native Build](chapter8.md)  
        8.1 Running `eas build -p android --profile development`  
        8.2 Installing and testing the Dev Client APK  
        8.3 Differences between dev, preview, and production builds  

     Chapter 9: [Connecting Dev Client to Metro](chapter9.md)  
        9.1 Running `expo start --dev-client`  
        9.2 Using tunnels, hotspots, and deep links  
        9.3 USB fallback with `adb reverse`  

---

#### Part V – [Practical Lessons and Next Steps](PartV_overview.md)

     Chapter 10: [Tips from the Trenches](chapter10.md)  
        10.1 Avoiding common Expo pitfalls  
        10.2 Best practices for project hygiene  
        10.3 Debugging strategies that actually work  

     Chapter 11: [Where to Go Next](chapter11.md)  
        11.1 Adding navigation and advanced UI (React Navigation, NativeWind)  
        11.2 Camera, file upload, and native APIs  
        11.3 Preparing for Play Store and App Store deployment  

---

#### [Technical Appendices (Cheat Sheets & Guides)](appendices.md)

A. CLI Commands Reference (Expo, EAS, adb)  
B. Comparison: Expo vs CRA/Vite (for web devs crossing into mobile)  
C. Troubleshooting Flowchart (Metro, builds, dependencies)  
D. Starter Project Template (Expo + NativeWind)  

---
