<div align="center">
  <img src="https://raw.githubusercontent.com/oms13/LeetForge/main/assets/icon-128.png" alt="LeetForge Logo" width="90" />
  
  # LeetForge - LeetCode Helper
  **The Zero-Config LeetCode to GitHub Synchronization Engine**

  [![Chrome Web Store](https://img.shields.io/badge/Chrome_Web_Store-Available_Now-2cbb5d?style=for-the-badge&logo=google-chrome&logoColor=white)](https://chrome.google.com/webstore/detail/hekbammfjebokafjhhaaihnfophgnojj)
  [![GitHub Issues](https://img.shields.io/github/issues/oms13/LeetForge?style=for-the-badge&color=ffa116)](https://github.com/oms13/LeetForge/issues)
  [![License](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)
</div>

---

## 🚀 Overview

LeetForge is a lightweight, high-performance Chrome Extension designed to automate your technical interview preparation workflow. It seamlessly bridges the gap between your LeetCode coding environment, your local machine, and your GitHub portfolio.

Completely re-engineered for Manifest V3, LeetForge now operates on a highly resilient, "client-first" architecture. It ensures every problem you solve is accurately tracked, properly versioned, and securely backed up—without ever slowing down your browser or logging your personal data on a third-party database.

---

## ✨ Core Features

### 🔄 Dual-Destination Synchronization
* **Remote Sync:** Instantly push your accepted solutions to a designated GitHub repository (supports both **Public** and **Private** repositories).
* **Local Workspace Backup:** Save solutions directly to your local file system organized by problem name and iteration.
* **Bi-Directional Loading:** Easily load previously saved local files back into the LeetCode editor to review past approaches.

### 🧠 Smart Sync Engine & Self-Healing
* **Client-Side Deduplication:** LeetForge hashes your code locally before syncing. If a solution is identical to your latest commit, it safely skips the push, keeping your Git history pristine.
* **High-Score Overwrites:** If you submit a new solution that beats your old runtime or memory percentiles, LeetForge intelligently overwrites the existing file while logging the new stats in the commit message.
* **SPA-Proof Extraction:** Utilizing a dual-layer extraction system (Monaco API + DOM Fallback) and XHR network wiretapping, the extension perfectly tracks submissions across LeetCode's dynamic Single Page Application environment.

### 🛡️ Non-Intrusive Integration
* **Monaco Editor Native Integration:** LeetForge uses native browser APIs to inject code directly into LeetCode's Monaco Editor engine. This preserves your native Undo/Redo history and ensures LeetCode's internal React states remain perfectly synchronized.
* **Optimized DOM Injection:** Uses heavily debounced `MutationObservers` to ensure the extension UI injects into the LeetCode DOM seamlessly without causing CPU spikes or typing lag.

---

## 🏗️ Technical Architecture

LeetForge has evolved to a fully decentralized, serverless model to guarantee maximum speed, uptime, and user privacy:

* **Client-Side (Chrome Extension):** Built entirely on Manifest V3. Utilizes `chrome.storage.local` for blazing-fast Base64 hash tracking and `IndexedDB` for persistent local file system handles. Background service workers natively route all requests directly to the GitHub REST API.
* **Stateless Auth Gateway (Vercel Edge):** The Vercel backend exists *solely* to facilitate the secure GitHub OAuth token exchange. It operates as a stateless pass-through and contains zero databases.
* **In-Browser Rate Limiting:** Implements a strict rolling-window rate limit (10 submissions per minute) directly inside the extension memory bank to protect your GitHub API quota.

---

## 🛠️ Installation & Setup

### 1. Install the Extension
Download LeetForge directly from the [Chrome Web Store](https://chrome.google.com/webstore/detail/hekbammfjebokafjhhaaihnfophgnojj).

### 2. Authenticate with GitHub
1. Open the LeetForge extension popup.
2. Click **Continue with GitHub**.
3. Authorize the application. *(LeetForge requests the `repo` scope to enable syncing to Private repositories).*

### 3. Configure Your Workspaces
1. **Target Repository:** Select the GitHub repository where you want your solutions saved.
2. **Local Workspace:** Click the folder icon to select a local directory for your backups.

> **💡 Seamless Experience Tip:** When Chrome prompts you for permission to edit your local folder, select **"Allow on every visit"**. This grants persistent access and prevents Chrome from repeatedly pausing your workflow with security popups.

---

## 🔒 Security & Privacy Statement

Developer tools require absolute transparency. LeetForge is built with a zero-trust, client-first security model:

* **Zero Backend Storage:** Your GitHub OAuth token is never saved on our servers. It is stored exclusively on your local device using Chrome's secure, isolated storage APIs.
* **No Telemetry:** We do not track your browsing history, LeetCode performance, or inject any analytics scripts (e.g., Google Analytics). 
* **Direct API Communication:** Once authenticated, LeetForge communicates directly from your browser to GitHub's API. Your source code never passes through our servers.

---

## ❓ Frequently Asked Questions

**Can I sync to a Private GitHub repository?** Yes. LeetForge fully supports private repositories. If you want your private commits to display as "Green Squares" on your public GitHub profile graph, navigate to your GitHub Profile settings, click `Contribution Settings`, and enable *"Include private contributions on my profile"*.

**Why did my GitHub Sync fail with a rate limit error?** To protect your GitHub account from being flagged, LeetForge implements a strict client-side rate limit of 10 pushes per minute. If you are rapidly testing code, please wait 60 seconds before syncing again.

**Why is Chrome asking for local file permissions again?** Chrome's security sandbox occasionally revokes local file handles if the browser updates or cache is cleared. Simply open the extension popup and re-select your folder to refresh the connection.

---

## 🤝 Contributing & Issue Tracking

We welcome contributions to make LeetForge better! If you encounter a bug or have a feature request:

1. Check the [Issues tab](https://github.com/oms13/LeetForge/issues) to ensure it hasn't already been reported.
2. Click **New Issue**, provide a detailed description, steps to reproduce, and any relevant console logs.

---
<div align="center">
  <i>Engineered by Om Sahu.</i>
</div>
