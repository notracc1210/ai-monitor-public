AI Monitor release web assets

Upload every file in this directory to the same public HTTPS directory.

Required files:
- index.html
- browser-extension-install.html
- browser-extension-privacy-policy.html
- WEB_ASSET_MANIFEST.json
- SHA256SUMS.txt

After uploading, verify from the public host:
- Browser install page: browser-extension-install.html
- Browser privacy policy: browser-extension-privacy-policy.html

Then write the public URLs into the release environment:

AI_MONITOR_PUBLIC_WEB_BASE_URL=<uploaded HTTPS directory> \
AI_MONITOR_BROWSER_EXTENSION_STORE_URL=<approved Chrome Web Store or managed-extension URL> \
  ./scripts/stage_release_web_assets.sh --write-env .env.release.local

Do not use browser-extension-install.html as the final public install URL until
AI_MONITOR_BROWSER_EXTENSION_STORE_URL points to an approved Chrome Web Store or
managed-extension install URL.

Support URL:
https://github.com/notracc1210/ai-monitor-public/issues
