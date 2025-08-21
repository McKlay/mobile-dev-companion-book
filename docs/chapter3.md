---
hide:
  - toc
---

# Chapter 3: Scaffolding a React Native App

---

Every great app begins with a scaffold. In the web world, you may have used `create-react-app` or Vite to spin up a project quickly. In the mobile world, Expo provides a similar tool: `create-expo-app`. This chapter walks you through creating your first React Native project, understanding the structure it generates, and setting up styling with Tailwind via NativeWind. By the end, you’ll not only have a functioning project but also a clear sense of the moving parts.

## Using `create-expo-app`

### Why a Scaffolding Tool?

Instead of manually configuring React Native, Metro, and platform-specific code, Expo’s scaffolding tool gives you a ready-to-run project in one command. This is especially helpful if you’re just starting—no need to wrestle with Xcode or Android Studio before writing your first component.

### The Command

Run this in your terminal:

```bash
npx create-expo-app my-first-app
cd my-first-app
npm start
````

This initializes a new Expo project named `my-first-app`. The `npm start` command launches Expo’s development server, which provides you with a QR code you can scan using Expo Go or your Dev Client.

### First Impressions

If everything works, you’ll see a basic “Open up App.js to start working on your app!” screen. It might feel underwhelming at first, but this minimal starting point is intentional—it keeps you in control of shaping the app’s direction.

## Project Structure Explained

After scaffolding, your folder might look like this:

```
my-first-app/
├── App.js
├── app.json
├── babel.config.js
├── package.json
├── node_modules/
└── assets/
```

Let’s break this down:

* **App.js** – The root of your React Native app; equivalent to `index.js` in web React projects.
* **app.json** – Expo configuration file (name, slug, splash screen, icons, etc.).
* **babel.config.js** – Configures Babel for transforming modern JavaScript into code Metro can bundle.
* **package.json** – Lists dependencies and scripts, just like in a Node project.
* **assets/** – Place for static files such as images and fonts.

Compared to web tooling, the structure is leaner. Most of the heavy lifting (like Webpack configs in web apps) is abstracted away by Expo.

## Adding Tailwind with NativeWind

### Why Tailwind on Mobile?

Styling in React Native can feel verbose since there’s no CSS—styles are objects in JavaScript. Tailwind, adapted via **NativeWind**, gives you the utility-first styling approach you might already love from web projects.

### Installation

From your project root, run:

```bash
npm install nativewind tailwindcss
npx tailwindcss init
```

Update your **tailwind.config.js**:

```js
module.exports = {
  content: ["./App.{js,jsx,ts,tsx}", "./components/**/*.{js,jsx,ts,tsx}"],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

Then wrap your app in the NativeWind provider:

```tsx
import { TailwindProvider } from "nativewind";

export default function App() {
  return (
    <TailwindProvider>
      <Text className="text-lg font-bold text-blue-500">Hello Expo + Tailwind!</Text>
    </TailwindProvider>
  );
}
```

### The Payoff

With Tailwind in place, styling becomes concise and expressive. Instead of defining a `StyleSheet` for everything, you can rapidly prototype with classes like `p-4`, `bg-indigo-500`, or `rounded-xl`.

## Conclusion: First Building Block Complete

By scaffolding with `create-expo-app`, you’ve taken the first real step into mobile development. You’ve learned how to interpret the project structure and even enhanced styling with NativeWind. This foundation prepares you for the next step: running your app on devices and understanding the development feedback loop, which we’ll explore in Chapter 4.

---