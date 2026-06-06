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

Built with a focus on privacy, strict rate-limiting, and non-blocking DOM integration, LeetForge ensures that every problem you solve is accurately tracked and securely backed up without ever slowing down your browser.

---

## ✨ Core Features

### 🔄 Dual-Destination Synchronization
* **Remote Sync:** Instantly push your accepted solutions to a designated GitHub repository (supports both **Public** and **Private** repositories).
* **Local Workspace Backup:** Save solutions directly to your local file system organized by problem name and iteration.
* **Bi-Directional Loading:** Easily load previously saved local files back into the LeetCode editor to review past approaches.

### 🛡️ Enterprise-Grade Reliability
* **Smart Deduplication:** LeetForge evaluates Base64 representations of your code on the server side. If a solution is identical to the latest commit, the push is intercepted, preventing your Git history from being cluttered with redundant commits.
* **Monaco Editor Native Integration:** LeetForge uses `pushEditOperations` to inject code directly into LeetCode's Monaco Editor engine. This preserves your native Undo/Redo history and ensures LeetCode's internal React states remain perfectly synchronized.
* **Optimized DOM Injection:** Uses heavily debounced `MutationObservers` to ensure the extension UI injects into the LeetCode DOM seamlessly without causing CPU spikes or typing lag.

---

## 🏗️ Technical Architecture

LeetForge operates on a highly optimized decoupled architecture to ensure maximum security and speed:

* **Client-Side (Chrome Extension):** Built with Manifest V3. Utilizes `chrome.storage.local` for blazing-fast state management and optimistic UI updates. Background service workers handle OAuth flows and persistent data syncs asynchronously.
* **Server-Side (Vercel Serverless):** A lightweight backend that manages GitHub API interactions.
* **Database (MongoDB Atlas):** Securely stores encrypted OAuth tokens and user preferences.
* **Protection Layer (Upstash Redis):** Implements strict Fixed-Window rate limiting. This dual-layered bouncer protects the backend from spam and ensures the extension never exceeds GitHub's strict 5,000 requests/hour API limits.

---

## 🛠️ Installation & Setup

### 1. Install the Extension
Download LeetForge directly from the [Chrome Web Store](https://chrome.google.com/webstore/detail/hekbammfjebokafjhhaaihnfophgnojj).

### 2. Authenticate with GitHub
1. Open the LeetForge extension popup.
2. Click **Continue with GitHub**.
3. Authorize the application. *(LeetForge requests the `repo` scope to enable syncing to Private repositories).*

### 3. Configure Your Workspaces
1. **Target Repository:** Select the GitHub repository where you want your solutions saved. (To prevent API abuse, this can be changed up to 3 times per 24-hour period).
2. **Local Workspace:** Click the folder icon to select a local directory for your backups.

> **💡 Seamless Experience Tip:** When Chrome prompts you for permission to edit your local folder, select **"Allow every time"**. This grants persistent access and prevents Chrome from repeatedly pausing your workflow with security popups.

---

## 🔒 Security & Privacy Statement

Developer tools require absolute transparency. LeetForge is built with a zero-trust security model:

* **No Telemetry:** We do not track your browsing history, LeetCode performance, or inject any analytics scripts (e.g., Google Analytics). 
* **Encryption at Rest:** Your GitHub OAuth token is AES-256 encrypted before being stored in our database. It is only decrypted in isolated server memory for the exact millisecond required to execute a Git commit.
* **Strict CORS Policies:** Our backend API is strictly locked to the Chrome Extension's unique ID, preventing Cross-Site Request Forgery (CSRF) or third-party endpoint hijacking.

---

## ❓ Frequently Asked Questions

**Can I sync to a Private GitHub repository?** Yes. LeetForge fully supports private repositories. If you want your private commits to display as "Green Squares" on your public GitHub profile graph, navigate to your GitHub Profile settings, click `Contribution Settings`, and enable *"Include private contributions on my profile"*.

**Why did my GitHub Sync fail with a rate limit error?** To protect both our infrastructure and your GitHub account from being flagged, LeetForge implements a strict rate limit of 10 pushes per minute. If you are rapidly testing code, please wait 60 seconds before syncing again.

**Why is Chrome asking for local file permissions again?** Chrome's security sandbox occasionally revokes local file handles if the browser updates or cache is cleared. Simply click the red refresh icon in the LeetForge popup to re-authenticate the folder.

---

## 🤝 Contributing & Issue Tracking

We welcome contributions to make LeetForge better! If you encounter a bug or have a feature request:

1. Check the [Issues tab](https://github.com/oms13/LeetForge/issues) to ensure it hasn't already been reported.
2. Click **New Issue**, provide a detailed description, steps to reproduce, and any relevant console logs.

---
<div align="center">
  <i>Engineered by Om Sahu.</i>
</div>
