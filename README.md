# free-ft

### Table of contents

- [Overview](https://github.com/arkadiyt/free-ft#overview)
- [Installation](https://github.com/arkadiyt/free-ft#installation)

### Overview

This chrome extension gives you free access to unlimited Financial Times (https://www.ft.com) articles. I built it as an exercise to learn Chrome's manifest v3 [declarativeNetRequest](https://developer.chrome.com/docs/extensions/reference/declarativeNetRequest/) - the new way to manage or block network requests which will eventually deprecate [webRequest](https://developer.chrome.com/docs/extensions/reference/webRequest/).

All the logic lives in [rules.json](https://github.com/arkadiyt/free-ft/blob/main/rules.json) and performs 3 things:

1) sets a `Referer: https://twitter.com` header on all ft.com requests, for which FT grants open access.

2) drops `Set-Cookie` response headers on ft.com - otherwise FT sets cookies to limit you to 1 article.

3) sends a `Cookie: FTCookieConsentGDPR=true` cookie on requests - this prevents FT from giving you a GDPR cookie popup.

### Installation

I have no plans of publishing this on the Chrome web store. If you want to install this extension you may do so locally by:

1) Cloning this repo

2) Going into your chrome extension settings (`chrome://extensions/`) and checking the "Developer mode" slider in the upper right corner

3) Clicking the "Load unpacked" button that appeared in the upper left corner and selecting the folder you cloned this repo into.
