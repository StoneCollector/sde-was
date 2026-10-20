# SecLab — Applied Security Workbench

A lightweight, zero-dependency client-side web security workbench demonstrating core cryptographic primitives and lexical phishing heuristics.

---

## 🛠 Modules

1. **[01 / CIA Primitives & WebCrypto (`crypto.html`)](crypto.html)**
   - **Integrity**: Continuous SHA-256 digest computation demonstrating avalanche and bit-flip effects.
   - **Confidentiality**: Client-side AES-256-GCM authenticated symmetric encryption and decryption with random IV generation.
   - **Entropy & Defense**: Real-time password entropy ($H = L \times \log_2(N)$) and exhaustive key search / offline cluster cracking estimations.

2. **[02 / Phishing Heuristics (`phishing.html`)](phishing.html)**
   - Lexical threat inspection of URLs.
   - Unencrypted transport protocol alerts (`http://`).
   - Direct IP address host detection.
   - Deep subdomain layering detection.
   - Homoglyph & non-ASCII Cyrillic character spoofing (Punycode translation).
   - High-risk TLD filtering (`.xyz`, `.top`, `.tk`, etc.).
   - Credential harvesting target pattern analysis.

---

## 🚀 GitHub Pages Deployment

This repository is pre-configured and 100% ready for **GitHub Pages**.

### Option A: Automatic via GitHub Actions (Recommended)
This repository includes [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml).
1. Go to your GitHub repository: **Settings** &rarr; **Pages**.
2. Under **Build and deployment** &rarr; **Source**, select **GitHub Actions**.
3. Every commit pushed to the `main` branch will automatically build and deploy your site to:
   ```
   https://<your-username>.github.io/<your-repo-name>/
   ```

### Option B: Deploy from Branch
1. Go to your GitHub repository: **Settings** &rarr; **Pages**.
2. Under **Build and deployment** &rarr; **Source**, select **Deploy from a branch**.
3. Choose branch: **`main`**, folder: **`/ (root)`**, and click **Save**.
4. The `.nojekyll` file ensures that GitHub Pages serves all static assets directly.

---

## 💻 Local Preview

Because all assets use relative paths and CDN imports, you can preview the workbench locally without a build step:

- **Directly**: Double-click `index.html` in your file explorer to open it in any modern browser.
- **Local HTTP server** (optional):
  ```bash
  # Python 3
  python -m http.server 8000

  # or Node (npx)
  npx serve .
  ```
  Then navigate to `http://localhost:8000`.

---

## 📂 Project Structure

```
├── .github/
│   └── workflows/
│       └── deploy.yml      # Automated GitHub Pages CI/CD workflow
├── .gitignore              # Standard git ignore rules
├── .nojekyll               # Bypasses Jekyll on GitHub Pages
├── 404.html                # Custom styled 404 error page
├── crypto.html             # CIA primitives & Web Crypto engine
├── index.html              # Workbench portal & navigation
├── phishing.html           # Lexical threat analyzer
└── README.md               # Documentation & setup guide
```
