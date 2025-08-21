---
hide:
  - toc
---

# Chapter 9: Connecting Dev Client to Metro

---

Now that you’ve built and installed a Dev Client, the next step is connecting it to your development server so you can iterate quickly. This is where **Metro**, Expo’s JavaScript bundler, comes back into play. Unlike Expo Go, which automatically links to Metro behind the scenes, a Dev Client requires a bit more setup. In this chapter, we’ll cover how to start Metro in Dev Client mode, handle different network setups, and use USB fallback when Wi-Fi fails.

## Running `expo start --dev-client`

### Why a Special Command?

When using Expo Go, the app already knows how to connect to Metro. But with a Dev Client, you’re running a **custom binary**—so Metro must be started in a mode tailored for it.

From your project root, run:

```bash
expo start --dev-client
````

This command launches Metro with the right configuration so your Dev Client app can connect. A QR code will appear in the terminal (or in the browser UI), which you can scan with your device.

### The Experience

Once connected, changes to your code are streamed directly to your Dev Client app. Fast Refresh works just like before—but now you can test native modules not available in Expo Go.

## Using Tunnels, Hotspots, and Deep Links

### The Network Challenge

Your phone and laptop must be on the **same network** for Metro to communicate. This isn’t always straightforward—especially with corporate firewalls, hotel Wi-Fi, or spotty connections.

Expo provides multiple solutions:

* **LAN (Local Network)** – Fastest and most stable when both devices share the same Wi-Fi.
* **Tunnel** – Creates a secure tunnel through Expo’s servers, allowing connection even when LAN fails. Slower but more reliable in restrictive networks.
* **Hotspot** – Share your laptop’s or phone’s hotspot to force both devices onto the same connection.

### Deep Linking

Sometimes scanning a QR code doesn’t work. In that case, Expo provides a **deep link URL** (e.g., `exp://192.168.x.x:8081`) you can open directly on your device. This bypasses QR scanning issues and connects your Dev Client directly.

## USB Fallback with `adb reverse`

When all else fails on Android, there’s still one trusty option: USB debugging with `adb`.

1. Connect your Android device via USB.

2. Run:

   ```bash
   adb reverse tcp:8081 tcp:8081
   ```

3. Start Metro with:

   ```bash
   expo start --dev-client
   ```

This forwards Metro’s traffic over USB, ensuring a stable connection even when Wi-Fi isn’t cooperating. (For iOS, USB debugging is trickier and usually requires Xcode.)

## Conclusion: Reliable Iteration

By now, you’ve learned how to connect your Dev Client to Metro across different scenarios: standard LAN, fallback tunnels, personal hotspots, and even USB with `adb reverse`. Mastering these options ensures you can always iterate on your app, regardless of network conditions.

With Part IV complete, you now know how to move beyond Expo Go, create native builds with EAS, and connect them back to Metro for development. In the next part, we’ll step away from tooling and explore **practical lessons and next steps**—battle-tested advice for keeping your projects healthy and preparing for real-world deployment.

---