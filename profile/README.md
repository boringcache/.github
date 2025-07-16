██████╗  ██████╗ ██████╗ ██╗███╗   ██╗ ██████╗  ██████╗ █████╗  ██████╗██╗  ██╗███████╗
██╔══██╗██╔═══██╗██╔══██╗██║████╗  ██║██╔════╝ ██╔════╝██╔══██╗██╔════╝██║  ██║██╔════╝
██████╔╝██║   ██║██████╔╝██║██╔██╗ ██║██║  ███╗██║     ███████║██║     ███████║█████╗  
██╔═══╝ ██║   ██║██╔═══╝ ██║██║╚██╗██║██║   ██║██║     ██╔══██║██║     ██╔══██║██╔══╝  
██║     ╚██████╔╝██║     ██║██║ ╚████║╚██████╔╝╚██████╗██║  ██║╚██████╗██║  ██║███████╗
╚═╝      ╚═════╝ ╚═╝     ╚═╝╚═╝  ╚═══╝ ╚═════╝  ╚═════╝╚═╝  ╚═╝ ╚═════╝╚═╝  ╚═╝╚══════╝

💤 BoringCache – Cache like it’s nobody’s business. Fast. Predictable. Unimpressed.

---

## 💡 What Is BoringCache?

**BoringCache** is a minimal, transparent caching system for slow CI toolchains (like Ruby and Node.js).  
It doesn’t try to be smart — it **pulls** and **pushes** only what you tell it to, with compression, reproducibility, and platform awareness.

- Works with [mise](https://mise.jdx.dev) for version installs
- Uses `.tar.zst` archives for fast, compact transfers
- Targets **global cache** and **user/project-level push**
- No black-box magic or fragile detection — just solid, boring cache mechanics

---

## ✨ Key Features

- ✅ Manual `cache pull/push` CLI
- 🧠 Global platform-aware namespace:
