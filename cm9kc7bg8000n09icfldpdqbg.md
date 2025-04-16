---
title: "🛠 Fixing `URL.canParse()` Error in Next.js 15"
datePublished: Wed Apr 16 2025 19:41:11 GMT+0000 (Coordinated Universal Time)
cuid: cm9kc7bg8000n09icfldpdqbg
slug: fixing-urlcanparse-error-in-nextjs-15
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/imgCpfIMoRw/upload/3debae043410b1a1a00e1bcd1cae9e46.jpeg
tags: nextjs, i18next, polyfills, nextjs15, urlcanparse

---

# **❓ The Problem**

While developing with Next.js 15, you might encounter this error:

```javascript
TypeError: URL.canPare is not a function
```

This happens because the `URL.canParse()` method is still experimental and not fully supported in most environments, including many versions of Node.js or browser runtimes.

If you are using libraries like `i18next` or `resourcesToBackend`, this function might be called internally, leading to unexpected crashes.

---

# **💡 The Solution: Add a Polyfill**

Fortunately, you can fix this with a simple polyfill — a piece of code that “fills in” missing functionality.

Add the following code to the top of your app entry file (e.g., `app/layout.tsx` or `app/page.tsx`:

```typescript
if (typeof URL.canParse !== "function") {
   URL.canParse = function (url: string) {
    try {
        new URL(url));
        return true;
    } catch {
        return false;
    }
  };
}
```

This checks whether `URL.canParse` is already defined and, if not, defines a safe fallback version.

---

# **✅ Tips**

* This polyfill works safely with Node.js 18, 20 and beyond.
    
* Even if your app doesn’t use `URL.canParse()` directly, it’s safer to patch it since third-part packages might.
    
* This is especially common when using `18next-resources-to-backend` in server-side translation loading.