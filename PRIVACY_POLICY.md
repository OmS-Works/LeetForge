# Privacy Policy for LeetForge

**Last Updated:** [Insert Today's Date]

LeetForge ("we", "our", or "us") is committed to protecting your privacy. This Privacy Policy explains how your data is collected, used, and protected when you use the LeetForge Chrome Extension.

## 1. Data We Collect and How We Use It
LeetForge is designed to be privacy-first. We collect the absolute minimum data required to synchronize your LeetCode solutions with your GitHub account.

* **GitHub Authentication:** We use Chrome's native `identity` API to authenticate you via GitHub OAuth. We securely store your encrypted OAuth access token and your selected GitHub username/avatar strictly to facilitate the syncing of your code.
* **Website Content:** The extension reads the code you write strictly within the LeetCode code editor (`leetcode.com`) solely for the purpose of pushing it to your chosen GitHub repository or local hard drive. 
* **Local Storage:** We use your browser's local storage to cache your settings, target repository, and daily sync counts. This data remains on your local machine.

## 2. What We DO NOT Do
* **We DO NOT sell your data.**
* **We DO NOT track your browsing history.** * **We DO NOT inject telemetry or analytics trackers** (e.g., Google Analytics). 
* **We DO NOT read your private GitHub repositories** beyond the exact repository you explicitly authorize us to push code to.

## 3. Third-Party Services
To facilitate our core functionality, LeetForge interacts with the following third-party services:
* **GitHub API:** Used to authenticate your account and push code commits.
* **Upstash (Redis):** Used strictly for anonymous, IP-based rate limiting to protect the GitHub API from spam.

## 4. Data Security
Your GitHub OAuth token is encrypted using AES-256 encryption before being stored on our backend. It is only decrypted in isolated server memory for the exact millisecond required to execute a Git commit. 

## 5. Your Rights & Data Deletion
You have total control over your data. You can disconnect LeetForge at any time by:
1. Clicking "Sign Out" within the LeetForge extension popup.
2. Revoking LeetForge's OAuth access directly from your GitHub account settings (Settings > Applications > Authorized OAuth Apps).

## 6. Contact Us
If you have any questions about this Privacy Policy, please open an issue on our [GitHub Repository](https://github.com/[YOUR_GITHUB_USERNAME]/[YOUR_PUBLIC_REPO_NAME]/issues).
