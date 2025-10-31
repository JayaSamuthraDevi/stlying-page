✅ 1. If you use a system font (already installed on the user’s device)

You don’t need any CDN or import link — just define it globally in your CSS or SCSS.

For example, open your global style file:

📄 src/styles.scss

* {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}


This will apply the font to every element across your entire Angular app because styles.scss is included globally.

✅ No CDN or font import needed (these fonts are built into the OS/browser).

✅ — **Nunito** is *not* a system font, so you **must import it** before applying it globally.

Here’s exactly how to do it in your **Angular project** (works in Angular v20 and earlier).

---

## 🧩 Step 1: Import the Nunito font

### Option 1 — Add via `index.html`

Simplest and fastest.

In your file:
📄 `src/index.html`
inside the `<head>` tag:

```html
<link href="https://fonts.googleapis.com/css2?family=Nunito:wght@300;400;600;700&display=swap" rel="stylesheet">
```

This loads the font from **Google Fonts** at runtime.

---

### Option 2 — Add via global stylesheet (`styles.scss`)

Alternatively, you can import it directly in your styles:

```scss
@import url('https://fonts.googleapis.com/css2?family=Nunito:wght@300;400;600;700&display=swap');
```

---

## 🧩 Step 2: Apply it globally

In the same global stylesheet (`src/styles.scss`):

```scss
html, body {
  font-family: 'Nunito', sans-serif;
  font-weight: 400;
  color: #222; // optional
}

* {
  font-family: inherit;
}
```

This ensures **every component** inherits Nunito automatically — no need to redefine it anywhere else.

---

## 🧩 Step 3 (Optional): Self-host Nunito

If your environment doesn’t allow CDN access (like corporate firewalls or offline apps), you can **download and self-host** it.

1. Download from [Google Fonts → Nunito](https://fonts.google.com/specimen/Nunito)
2. Copy `.woff2` files to `src/assets/fonts/nunito/`
3. Add a `@font-face` rule in `styles.scss`:

   ```scss
   @font-face {
     font-family: 'Nunito';
     src: url('assets/fonts/nunito/Nunito-Regular.woff2') format('woff2');
     font-weight: 400;
     font-style: normal;
   }
   @font-face {
     font-family: 'Nunito';
     src: url('assets/fonts/nunito/Nunito-Bold.woff2') format('woff2');
     font-weight: 700;
     font-style: normal;
   }

   body {
     font-family: 'Nunito', sans-serif;
   }
   ```

✅ Works completely offline
✅ No external dependencies

---

### ✅ TL;DR

| Setup Type         | Needs Internet? | Where to Add                  | Example                                          |
| ------------------ | --------------- | ----------------------------- | ------------------------------------------------ |
| Google Fonts (CDN) | ✅ Yes           | `index.html` or `styles.scss` | `<link href="https://fonts.googleapis.com/...">` |
| Self-hosted        | ❌ No            | `@font-face` in `styles.scss` | `src: url('assets/fonts/...')`                   |
| Apply Globally     | —               | `styles.scss`                 | `font-family: 'Nunito', sans-serif;`             |

---

Would you like me to give you a ready-to-use **Nunito font SCSS snippet** that includes light, regular, semibold, and bold weights (400–700) for global typography setup?
