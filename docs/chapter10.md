---
hide:
  - toc
---

# Chapter 10: Tips from the Trenches

---

Every developer who spends enough time with React Native and Expo learns the same lesson: **the official docs are only half the story.** The other half comes from mistakes made at 2 AM, debugging cryptic Metro errors, or chasing version mismatches through GitHub issues. This chapter gathers those battle-tested lessons so you don’t have to stumble through every pitfall yourself.

## Avoiding Common Expo Pitfalls

### Pitfall 1: Ignoring SDK Versions

Expo is versioned tightly, and your project depends on the specific SDK release you’re using. Installing a random NPM package version is the fastest way to break your build.

**Tip:** Always use:

```bash
expo install <package-name>
````

This ensures Expo aligns the installed version with your SDK.

---

### Pitfall 2: Relying Too Long on Expo Go

Expo Go is fantastic for prototypes, but it can give you a false sense of security. Features may work in Expo Go but fail in a Dev Client or production build.

**Tip:** Transition to a Dev Client early once you add any native dependencies. Don’t wait until release week.

---

### Pitfall 3: Forgetting to Clear Caches

Metro’s cache can hold onto broken states. If you’re debugging an error that *shouldn’t exist*, the cache may be to blame.

**Tip:** Run:

```bash
npx expo start -c
```

to clear caches before spending hours chasing phantom issues.

---

## Best Practices for Project Hygiene

### Keep Your Dependencies Lean

Each library you add increases the chance of version conflicts. Resist the temptation to install “just one more” package for something you could implement with plain React Native.

### Organize Your Components

Split components into `/components` and group related features. This reduces clutter and keeps you from getting lost in a sea of `App.js` spaghetti.

### Version Control Discipline

Always commit a working state before experimenting. Expo projects can break suddenly, and having a safe checkpoint saves you from painful rollbacks.

---

## Debugging Strategies That Actually Work

### Strategy 1: Start Simple

When faced with a red error screen, your instinct may be to dive into Stack Overflow. Instead, strip the problem down: comment out code until the error disappears, then reintroduce parts systematically. Often, the culprit reveals itself faster than endless Googling.

### Strategy 2: Read the Logs Closely

Expo and Metro errors often contain hidden clues. Look for specific words like `babel`, `worklet`, or `UIManager`—these usually point you toward the real issue.

### Strategy 3: Know When to Rebuild

If your app behaves differently in Expo Go and Dev Client, the issue often lies in native bindings. Rebuild with:

```bash
eas build -p android --profile development
```

to confirm whether the bug is JavaScript-only or native-related.

---

## Conclusion: Wisdom from the Field

By avoiding common pitfalls, maintaining project hygiene, and applying systematic debugging, you’ll spend less time stuck and more time building features. The truth is, no developer completely avoids dependency hell or red error screens—but seasoned developers recover faster because they’ve built habits that minimize the damage.

In the next chapter, we’ll zoom out and talk about **what comes after the basics**: advanced UI, navigation, working with device APIs, and preparing your app for distribution on app stores.

---