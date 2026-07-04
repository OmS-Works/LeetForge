# Privacy Policy for LeetForge

**Effective Date:** July 4, 2026

LeetForge ("we", "our", or "us") is committed to protecting your privacy. This Privacy Policy explains how your data is collected, used, and protected when you use the LeetForge Chrome Extension.

We are committed to protecting your privacy and ensuring transparency. LeetForge is designed to operate primarily on your local machine, minimizing off-device data transmission.

## 1. Information We Collect

LeetForge strictly limits data collection to what is necessary for the Extension to function. We collect and process the following information:

*   **GitHub Authentication Data:** When you authorize LeetForge via GitHub OAuth, we receive an OAuth access token. We also retrieve basic profile information (such as your GitHub username and avatar) to display within the Extension interface.
*   **LeetCode Session Data:** The Extension reads problem details (title, difficulty, topic tags, descriptions), runtime/memory statistics, and your written code snippets directly from the active LeetCode DOM and network requests.
*   **Local File System Data:** If you utilize the local save feature, LeetForge requests permission to access a specific local directory via the File System Access API. We store a persistent reference handle to this directory.

## 2. How We Use Your Information

The data we collect is used exclusively to provide and improve the core functionality of LeetForge. We use your data to:

*   **Synchronize to GitHub:** Your LeetCode code snippets, problem descriptions, and performance statistics are formatted and pushed directly to your selected GitHub repository using the GitHub REST API.
*   **Save Locally:** Your code is written to your local machine using the directory handle you explicitly authorized.
*   **Prevent Duplicate Work:** We use local caching to track problem hashes and submission SHAs to avoid pushing duplicate files to your repository or local drive.

## 3. Data Storage and Security

LeetForge is built with a "client-first" architecture to maximize data security:

*   **Client-Side Storage:** Your GitHub OAuth token, GitHub repository selections, local directory handles, and problem caches are stored exclusively on your local device using Chrome's secure `chrome.storage.local` API and IndexedDB. 
*   **Stateless Backend Authentication:** LeetForge utilizes a custom backend (`leet-forge-backend.vercel.app`) solely for completing the secure GitHub OAuth token exchange. This backend acts as a stateless pass-through; it **does not** log, store, or database your OAuth token, your GitHub identity, or your LeetCode code snippets.
*   **No Telemetry:** We do not track your browsing history outside of the active `leetcode.com/problems/*` tabs required for the Extension to function.

## 4. Third-Party Data Sharing

**We do not sell, rent, or share your personal data with third parties.** 

Your data is only transmitted to the specific third-party APIs required for the Extension to function:
*   **GitHub API:** To authenticate your account and push your code commits.
*   **LeetCode API:** To fetch problem context and submission success states.

LeetForge's use and transfer of information received from Google APIs will adhere to the [Chrome Web Store User Data Policy](https://developer.chrome.com/docs/webstore/user_data/), including the Limited Use requirements.

## 5. User Control and Data Deletion

You have full control over your data and how LeetForge interacts with it:

*   **Revoke GitHub Access:** You can instantly revoke LeetForge's access to your GitHub account at any time by navigating to your GitHub settings: *Settings > Applications > Authorized OAuth Apps*, and revoking the "LeetForge" application.
*   **Clear Local Data:** Uninstalling the LeetForge extension from your Chrome browser will immediately delete all locally stored OAuth tokens, caches, and file system handles.
*   **Local Files:** Files saved to your local machine by LeetForge remain under your control and must be deleted manually from your operating system if desired.

## 6. Changes to This Privacy Policy

We may update our Privacy Policy from time to time. Any changes will be reflected by updating the "Effective Date" at the top of this document. We advise you to review this Privacy Policy periodically for any changes.

## 7. Contact Information

If you have any questions, concerns, or suggestions regarding this Privacy Policy, please contact us at:

*   **GitHub:** https://github.com/OmS-Works/LeetForge/issues
