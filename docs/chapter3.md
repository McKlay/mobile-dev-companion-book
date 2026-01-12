---
hide:
  - toc
---

# Chapter 3: Scaffolding a React Native App

---


Every great app begins with a scaffold. In the web world, you may have used `create-react-app` or Vite to spin up a project quickly. In the mobile world, Expo provides a similar tool: `create-expo-app`. This chapter walks you through creating your first React Native project, understanding the structure it generates, and setting up styling with Tailwind via NativeWind. By the end, you’ll not only have a functioning project but also a clear sense of the moving parts and how to customize your workflow for rapid development.

## Using `create-expo-app`


### Why a Scaffolding Tool?

Scaffolding tools automate the tedious setup steps and ensure best practices from the start. Instead of manually configuring React Native, Metro, and platform-specific code, Expo’s scaffolding tool gives you a ready-to-run project in one command. This is especially helpful if you’re just starting—no need to wrestle with Xcode or Android Studio before writing your first component. You get a consistent structure, working scripts, and a development server out of the box.

**Benefits:**

- **Speed:** Go from zero to running app in minutes.
- **Reliability:** Avoid common misconfigurations and dependency issues.
- **Learning:** Focus on building features, not fixing build errors.


### The Command

Run this in your terminal:

```bash
npx create-expo-app my-first-app
cd my-first-app
npm start
```

This initializes a new Expo project named `my-first-app`. The `npm start` command launches Expo’s development server, which provides you with a QR code you can scan using Expo Go or your Dev Client. You can also use `npx expo start` for more advanced options, like running on simulators or enabling tunnel mode for remote devices.

**Tip:** If you want to use TypeScript, add the `--template` flag:

```bash
npx create-expo-app my-first-app --template
```


### First Impressions

If everything works, you’ll see a basic “Open up App.js to start working on your app!” screen. It might feel underwhelming at first, but this minimal starting point is intentional—it keeps you in control of shaping the app’s direction. The initial project is lightweight, with just enough code to verify your setup and let you start experimenting immediately.

**What’s Happening:**

- The app is running in development mode, with hot reloading enabled.
- You can edit `App.js` and see changes instantly on your device or simulator.
- The QR code lets you preview on any phone with Expo Go installed.


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

- **App.js** – The root of your React Native app; equivalent to `index.js` in web React projects. This is where your main component tree lives.
- **app.json** – Expo configuration file (name, slug, splash screen, icons, permissions, etc.). You can customize app metadata, deep linking, and more here.
- **babel.config.js** – Configures Babel for transforming modern JavaScript into code Metro can bundle. Supports JSX, TypeScript, and new JS features.
- **package.json** – Lists dependencies and scripts, just like in a Node project. You’ll find Expo, React Native, and other libraries here.
- **assets/** – Place for static files such as images, fonts, and sometimes custom icons or splash screens.
- **node_modules/** – All installed dependencies.

**Other files you may see:**

- **.gitignore** – Specifies files to exclude from version control.
- **README.md** – Project documentation.

Compared to web tooling, the structure is leaner. Most of the heavy lifting (like Webpack configs in web apps) is abstracted away by Expo. You can add more folders (like `components/` or `screens/`) as your app grows.


## Adding Tailwind with NativeWind

### Why Tailwind on Mobile?

Styling in React Native can feel verbose since there’s no CSS—styles are objects in JavaScript. Tailwind, adapted via **NativeWind**, gives you the utility-first styling approach you might already love from web projects. This means you can use familiar class names to style components, making your code more readable and maintainable.

**Benefits:**

- **Rapid prototyping:** Style components quickly with utility classes.
- **Consistency:** Use the same design language across web and mobile.
- **Less boilerplate:** No need to define a `StyleSheet` for every component.


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
import { Text } from "react-native";

export default function App() {
  return (
    <TailwindProvider>
      <Text className="text-lg font-bold text-blue-500">Hello Expo + Tailwind!</Text>
    </TailwindProvider>
  );
}
```

**Tip:** You can create a `components/` folder and use Tailwind classes in all your custom components for a scalable design system.


### The Payoff

With Tailwind in place, styling becomes concise and expressive. Instead of defining a `StyleSheet` for everything, you can rapidly prototype with classes like `p-4`, `bg-indigo-500`, or `rounded-xl`. You can also leverage Tailwind’s responsive utilities and color palette for consistent UI.

**Example:**

```tsx
<View className="flex-1 items-center justify-center bg-gray-100">
  <Text className="text-xl font-semibold text-green-600">Welcome to NativeWind!</Text>
</View>
```


## Conclusion: First Building Block Complete

By scaffolding with `create-expo-app`, you’ve taken the first real step into mobile development. You’ve learned how to interpret the project structure and even enhanced styling with NativeWind. This foundation prepares you for the next step: running your app on devices and understanding the development feedback loop, which we’ll explore in Chapter 4.

As you continue, experiment with adding new screens, components, and styles. The Expo and NativeWind ecosystem makes it easy to iterate and build beautiful, performant mobile apps. You’re now ready to explore device testing and debugging workflows in the next chapter.

---