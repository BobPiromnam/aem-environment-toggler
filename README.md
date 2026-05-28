# AEM Environment Toggler Bookmarklet

A lightweight, single-click browser shortcut designed for web developers and content authors working on Canada.ca. It intelligently cycles your current browser tab between the Live site, the AEM Authoring Editor, and the AEM Preview environment depending on where you currently are.

## How It Works (The Cycle)

*   **From Live (`www.canada.ca`)** $\rightarrow$ Redirects the current tab straight into the **AEM Authoring Editor** for that exact page.
*   **From Authoring (`author-canada-prod.adobecqms.net`)** $\rightarrow$ Opens the page on the **AEM Preview site** in a **new tab** (preserving your authoring session).
*   **From Preview (`canada-preview.adobecqms.net`)** $\rightarrow$ Redirects the current tab back to the public **Live site**.
*   **Anywhere else** $\rightarrow$ Triggers a safe warning popup letting you know the domain isn't supported.

Query strings (like `?wbdisable=true`) and URL hashes are completely preserved throughout the entire loop.

---

## Installation & Setup

### Method 1: Manual Link Creation (Recommended)
1. Ensure your browser's **Bookmarks Bar** is visible (`Ctrl + Shift + B` or `Cmd + Shift + B`).
2. Right-click an empty space on your Bookmarks Bar and select **Add Page** (or **Add Bookmark**).
3. Set the **Name** to something recognizable, like `➡️ AEM Toggle`.
4. Copy the entire raw JavaScript block below and paste it into the **URL** field:

```text
javascript:(function(){var h=window.location.hostname,p=window.location.pathname,s=window.location.search+window.location.hash;if(h.includes("canada.ca")){window.location.href="[https://author-canada-prod.adobecqms.net/editor.html/content/canadasite](https://author-canada-prod.adobecqms.net/editor.html/content/canadasite)"+p+s;}else if(h==="author-canada-prod.adobecqms.net"){var c=p.replace(/^\/editor\.html\/content\/canadasite/,"");window.open("[https://canada-preview.adobecqms.net](https://canada-preview.adobecqms.net)"+c+s,"_blank");}else if(h==="canada-preview.adobecqms.net"){window.location.href="[https://www.canada.ca](https://www.canada.ca)"+p+s;}else{alert("Warning: This shortcut only works on Canada.ca or official AEM domains.");}})();
