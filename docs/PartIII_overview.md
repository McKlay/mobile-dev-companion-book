---
hide:
    - toc
---

## 🟢 Part III: Surviving Dependency Hell

Every mobile developer eventually encounters the infamous "dependency hell." While React Native and Expo smooth many rough edges, the moment you introduce third-party libraries, mismatched versions, or native code, things can quickly spiral into frustration. This part of the book equips you with strategies, tools, and mental models to not just survive but navigate dependency issues with confidence.

### Chapter 5: Library Compatibility Issues

This chapter examines the most common troublemakers in the React Native ecosystem—packages like `react-native-reanimated` and `react-native-gesture-handler`. You’ll learn why these packages are often problematic, how to resolve version mismatches, and how to use Expo’s recommended tools like `expo install` and `expo-doctor` to stay aligned with compatible versions.

**Key points covered:**

* Identifying common problem libraries (`react-native-reanimated`, `gesture-handler`).  
* Using `expo install` to ensure version alignment.  
* Running `expo-doctor` to catch mismatches early.  

### Chapter 6: Babel, Metro, and You

When errors appear in blazing red screens, it’s often unclear whether the issue comes from your code, Metro, or Babel. This chapter breaks down how Babel transforms your JavaScript, how Metro bundles your project, and how to interpret errors. You’ll also explore the nuances of hot reload vs. full reload, so you know when to restart and when to debug incrementally.

**Key points covered:**

* What Babel does in React Native projects.  
* Metro bundler workflow (and why it defaults to port 8081).  
* Hot reload vs full reload explained.  

---

By the end of Part III, you’ll be prepared to handle the ecosystem’s rough edges with practical debugging strategies. Instead of dreading the red error screen, you’ll know how to interpret, resolve, and even prevent common dependency pitfalls. This resilience sets you up for the next stage: building natively with Expo Application Services (EAS).  

---
