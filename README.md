## Installation & Setup

### Method 1: Interactive Web Setup (Recommended)
To prevent your browser or Windows security from blocking the shortcut file, install it via the project's web page:

1. Ensure your browser's **Bookmarks Bar** is visible (`Ctrl + Shift + B` or `Cmd + Shift + B`).
2. Go to the deployment page: **https://github.com/BobPiromnam/aem-environment-toggler**
3. Simply **click, drag, and drop** the green button onto your browser's Bookmarks bar.

---

### Method 2: Manual Link Creation (Fallback)
If you prefer to configure it yourself, you can build the bookmark manually:

1. Right-click an empty space on your Bookmarks Bar and select **Add Page** (or **Add Bookmark**).
2. Set the **Name** to: `➡️ AEM Toggle`.
3. Copy the entire raw JavaScript block below and paste it into the **URL** field:

```text
javascript:(function(){var h=window.location.hostname,p=window.location.pathname,s=window.location.search+window.location.hash;if(h.includes("canada.ca")){window.location.href="[https://author-canada-prod.adobecqms.net/editor.html/content/canadasite](https://author-canada-prod.adobecqms.net/editor.html/content/canadasite)"+p+s;}else if(h==="author-canada-prod.adobecqms.net"){var c=p.replace(/^\/editor\.html\/content\/canadasite/,"");window.open("[https://canada-preview.adobecqms.net](https://canada-preview.adobecqms.net)"+c+s,"_blank");}else if(h==="canada-preview.adobecqms.net"){window.location.href="[https://www.canada.ca](https://www.canada.ca)"+p+s;}else{alert("Warning: This shortcut only works on Canada.ca or official AEM domains.");}})();
