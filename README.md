# free-ft

This chrome extension gives you free access to unlimited Financial Times (https://www.ft.com) articles. I built it as an exercise to learn Chrome's manifest v3 [declarativeNetRequest](https://developer.chrome.com/docs/extensions/reference/declarativeNetRequest/) - the new way to manage or block network requests which will eventually deprecate [webRequest](https://developer.chrome.com/docs/extensions/reference/webRequest/).

All the logic lives in [rules.json](https://github.com/arkadiyt/free-ft/blob/main/rules.json) and performs 3 things:

1) sets a `Referer: https://twitter.com` header on all ft.com requests, for which FT grants open access.

2) drops `Set-Cookie` response headers on ft.com - otherwise FT sets cookies to limit you to 1 article.

3) sends a `Cookie: FTCookieConsentGDPR=true` cookie on requests - this prevents FT from giving you a GDPR cookie popup.
