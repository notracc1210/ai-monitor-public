AI Monitor release web assets

Upload every file in this directory to the same public HTTPS directory.

Required files:
- index.html
- browser-extension-install.html
- browser-extension-privacy-policy.html
- WEB_ASSET_MANIFEST.json
- SHA256SUMS.txt

After uploading, verify from the public host:
- Browser install page: https://notracc1210.github.io/ai-monitor-public/ai-monitor/browser-extension-install.html
- Browser privacy policy: https://notracc1210.github.io/ai-monitor-public/ai-monitor/browser-extension-privacy-policy.html

Then write the public URLs into the release environment:

AI_MONITOR_PUBLIC_WEB_BASE_URL=<uploaded HTTPS directory> \
AI_MONITOR_BROWSER_EXTENSION_STORE_URL=<approved Chrome Web Store or managed-extension URL> \
  ./scripts/stage_release_web_assets.sh --write-env .env.release.local

browser-extension-install.html is a stable public install page. Before the
Chrome Web Store or managed-extension URL is ready, it explains that browser
adapter installation is pending while the desktop app remains usable. After
AI_MONITOR_BROWSER_EXTENSION_STORE_URL points to an approved install URL, rerun
this script and upload the refreshed page to add the install button.

Support URL:
https://github.com/notracc1210/ai-monitor-public/issues
