---
hide:
  - toc
---

### Why This Book Exists

Three weeks before writing this, I had never built a mobile app.  
But while working on **ScanlyAI**, I went from zero knowledge to deploying a working React Native + Expo app on my Android phone.  

That journey taught me a hard truth:  
**Vibe coding is not enough.**

Here’s what I realized (from a LinkedIn post I wrote during the process):  

* ✅ Vibe coding works great for static sites or small demo projects.  
* ✅ It’s fine if you only need simple auth and a few backend endpoints.  
* ❌ But once your app has 3+ backend services, real integrations, or complex flows—it breaks.  
* ❌ AI can’t keep up, and you’re left debugging on your own.  

I had to pause, spend a week learning React Native, Expo, and NativeWind properly, and grind through forums, docs, and debugging. Painful? Yes. But necessary.  

This book exists because **mobile is different from web**. The tools look familiar (React, CLI commands, bundlers), but the complexity multiplies once you bring in native dependencies, device testing, and build systems like EAS.  

The goal of this handbook is to capture those lessons and distill them into a structured, beginner-to-intermediate guide for anyone stepping into cross-platform mobile development.  

### Who Should Read This

This book is for:

* **Web developers** (React, Vite, CRA, Tailwind) curious about mobile development.  
* **Indie builders and startup founders** who want to ship cross-platform apps without drowning in native setup.  
* **Students and career switchers** looking for a structured path into mobile engineering.  
* **AI/ML engineers** (like myself) who want to wrap models in mobile apps for real-world use cases.  

You don’t need prior mobile experience. Basic React knowledge helps. We’ll cover Expo, EAS, Metro, and the ecosystem step by step.

### From Web Comfort to Mobile Reality

I started with **Bolt.new**, leaning heavily on Copilot and other AI tools. At first, it felt like coding on autopilot. But once dependency mismatches appeared, everything collapsed.  

That’s when I realized: vibe coding is a rocket booster for prototyping, but not a parachute when things get complex.  

This book captures that turning point: moving from “AI will fix it for me” to **understanding the stack deeply enough to fix it myself**.  

### What You’ll Learn (and What You Won’t)

You will learn:

* How Expo scaffolds and bundles apps across Android, iOS, and Web.  
* The difference between Expo Go, Dev Client, and production builds.  
* How to configure and run EAS cloud builds for real device testing.  
* How to resolve common dependency/version issues.  
* How to think like a mobile engineer (not just a web dev).  

You will *not* find:

* Advanced Android/iOS native development tutorials.  
* In-depth Swift or Kotlin coverage (we’ll stay Expo-first).  
* Blind “copy-paste and pray” code snippets with no explanation.  

This is a handbook for **builders** — engineers who want to actually ship.  

### How to Read This Book

Each chapter includes:

* **Foundational Concepts**: What makes mobile unique compared to web.  
* **Command Cheat Sheets**: Key CLI workflows with explanations.  
* **Troubleshooting Tips**: Real fixes from real errors I hit.  
* **Code Walkthroughs**: Practical examples using Expo + React Native.  
* **Builder’s Notes**: Lessons and reflections from the trenches.  

Whether you’re coming from frontend React, backend APIs, or AI/ML, this book will guide you from zero to running your own Dev Client on a real device.  