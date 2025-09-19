██████╗  ██████╗ ██████╗ ██╗███╗   ██╗ ██████╗  ██████╗ █████╗  ██████╗██╗  ██╗███████╗
██╔══██╗██╔═══██╗██╔══██╗██║████╗  ██║██╔════╝ ██╔════╝██╔══██╗██╔════╝██║  ██║██╔════╝
██████╔╝██║   ██║██████╔╝██║██╔██╗ ██║██║  ███╗██║     ███████║██║     ███████║█████╗  
██╔═══╝ ██║   ██║██╔═══╝ ██║██║╚██╗██║██║   ██║██║     ██╔══██║██║     ██╔══██║██╔══╝  
██║     ╚██████╔╝██║     ██║██║ ╚████║╚██████╔╝╚██████╗██║  ██║╚██████╗██║  ██║███████╗
╚═╝      ╚═════╝ ╚═╝     ╚═╝╚═╝  ╚═══╝ ╚═════╝  ╚═════╝╚═╝  ╚═╝ ╚═════╝╚═╝  ╚═╝╚══════╝

# Boringcache

**A universal, portable build cache.**  
Cache once, reuse anywhere — CI, deploy, or your laptop.  

boringcache is a distributed cache platform with:  
- A **Rust CLI** for saving/restoring cache  
- A **Rails backend** with workspaces (private or public)  
- **S3-compatible storage** powered by [Tigris Data](https://www.tigrisdata.com/)  

Think Docker layers, but for build artifacts.  

👉 [Website](https://boringcache.com) · [Docs](https://boringcache.com/docs)

---

## ✨ Features

- **Portable** — works in *any environment*: CI/CD, local dev, deployment pipelines  
- **Fast** — caches only compatible layers, restores instantly  
- **Reusable** — share cache across machines and workspaces  
- **Simple** — one CLI, one cache format, everywhere  
- **Transparent** — you control retention, visibility (private/public)  
