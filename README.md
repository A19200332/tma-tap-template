# Tap Empire — Telegram Mini App Game Template

A production-ready **tap-to-earn** game UI you can rebrand in about 15 minutes.
Single `index.html`. No build step, no framework, no backend.

**Live demo:** https://a19200332.github.io/tma-tap-template/

---

## What you get

| Feature | Included |
|---|---|
| Tap-to-earn loop with coin animation, floating numbers, particle sparks | Yes |
| Energy system with regeneration | Yes |
| Three upgrade tracks (tap power, energy cap, passive bot) with scaling costs | Yes |
| Referral link generation + copy button | Yes |
| Leaderboard with live rank | Yes |
| Wallet connect UI (TON Connect placeholder) | Yes |
| Telegram WebApp SDK integration (user name, haptics, expand, header color) | Yes |
| LocalStorage save/load | Yes |
| Mobile-first layout, safe-area aware, works inside Telegram WebView | Yes |
| Optional game assets (CC0 packs) | Bundle option |

---

## Quick start

```bash
# 1. download / unzip
# 2. open index.html in a browser — it just runs
# 3. or serve locally
python -m http.server 8080
```

No npm install. Nothing to compile.

---

## Deploy in 3 minutes

**Option A — GitHub Pages**

1. Create a repo, push this folder.
2. Settings → Pages → Source: `main` / root.
3. Your game is live at `https://<user>.github.io/<repo>/`.

**Option B — Netlify / Vercel**

Drag the folder into Netlify Drop, or import the repo in Vercel. Static output, zero config.

**Option C — Your own hosting**

Upload `index.html` anywhere that serves static files.

---

## Turn it into a Telegram Mini App

1. Open [@BotFather](https://t.me/BotFather) → `/newbot` → get a token.
2. `/newapp` → pick your bot → set the URL to your deployed page.
3. Open the bot, tap the menu button — the game runs full-screen inside Telegram.

The template already calls `Telegram.WebApp.ready()`, `expand()`, `setHeaderColor()` and reads the user's name when it is opened inside Telegram.

---

## Rebrand checklist

| What | Where |
|---|---|
| Accent colors (gold + violet) | `:root` at the top of `index.html` |
| Coin / logo | the `<svg class="coin">` block — replace the `<path>` with your logo |
| Game name, copy, nav labels | plain text in the HTML |
| Passive income rates and upgrade prices | the `UPGRADES` array in the script |
| Leaderboard seed data | the `BOTS` array |
| Referral base URL | `refLink()` → `https://t.me/YourBot/app` |

---

## Connecting a real wallet

The wallet tab is a UI placeholder. To make it real:

1. Create a TON Connect manifest (`tonconnect-manifest.json`) and host it.
2. Add the TON Connect SDK:

```html
<script src="https://unpkg.com/@tonconnect/ui@latest/dist/tonconnect-ui.min.js"></script>
```

3. Replace `connectWallet()` with:

```js
const tonConnectUI = new TON_CONNECT_UI.TonConnectUI({
  manifestUrl: 'https://yourdomain.com/tonconnect-manifest.json'
});
const wallet = await tonConnectUI.connectWallet();
// wallet.account.address -> use it as the player id
```

---

## License

- **Template code:** single commercial use per purchase. You may modify it and deploy it for your own projects. You may **not** resell, redistribute or publish the template itself (modified or not) as a template, boilerplate or source code product.
- **Optional asset packs:** CC0 (public domain), commercial use allowed, attribution not required.
- **No warranty.** Test on your own devices before launch.

---

## Support

Open an issue or email the seller. Include your order id.
