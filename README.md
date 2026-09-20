# 🌐 V-Train Community Rules (雲端規則庫)

Welcome to the official community-driven rule database for the **V-Train Extension**. 
This repository hosts the auto-syncing configuration rules that allow V-Train to adapt to various video platforms worldwide seamlessly.

## 🚀 How it Works (運作方式)

Starting from V-Train v1.0.8, the extension automatically syncs with this repository in the background. 
If a site is supported in `rules.json`, you **do not need to train it manually**. Just click **"Authorize & Enable"** on the site, and V-Train will automatically start tracking!

*(Note: Sensitive domains are stored as Base64 encoded strings to protect user privacy and comply with store policies.)*

## 🤝 How to Contribute (如何貢獻規則)

If you've encountered a site that V-Train doesn't support natively, you can train it yourself using the Visual Capture Tool. Once successful, you can share it with the world!

1. Open your V-Train Dashboard and go to **Rule Management (規則管理)**.
2. Find the rule you just trained, and click the orange **📋 Share (序號複製)** button.
3. Go to the [Issues](../../issues) tab of this repository.
4. Click **New Issue**, select the Rule Submission template, and paste your `SYNC-Z...` code.

Our maintainers will review your code, convert the domain to Base64 (if necessary), and merge it into `rules.json`. Within 24 hours, all V-Train users globally will receive your update!

---

### For Maintainers (維護者指南)

When adding a new rule to `rules.json`, follow this format:

```json
{
  "BASE64_ENCODED_DOMAIN": [
    {
      "hosts": ["BASE64_ENCODED_DOMAIN"],
      "pRule": { ... },
      "s": "div.video-wrapper",
      "tRule": { ... },
      "imgSelector": "video" 
    },
    null, null, null
  ]
}
```

* **Base64 Encoding**: All adult or sensitive domains MUST be Base64 encoded (both the object key and inside the `hosts` array) to bypass automated text scanners.
* **imgSelector**: Optional. Used to specify the CSS selector for extracting high-quality thumbnails when bookmarking (e.g., `"video"` grabs the video tag's `poster` attribute).
