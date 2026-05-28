## Installation & Setup

### Method 1: Download & Drag (Recommended)
The easiest way to install the bookmarklet is to download the pre-configured shortcut file directly from this repository and add it to your browser.

1. Ensure your browser's **Bookmarks Bar** is visible (`Ctrl + Shift + B` or `Cmd + Shift + B`).
2. Download the `AEM Environment Toggle.url` file from the file list at the top of this repository.
3. Drag the downloaded file from your computer's **Downloads** folder and drop it directly onto your browser's Bookmarks bar.

---

### Method 2: Manual Link Creation (Fallback)
If you prefer not to download a file, you can create the bookmark manually in your browser:

1. Right-click an empty space on your Bookmarks Bar and select **Add Page** (or **Add Bookmark**).
2. Set the **Name** to something recognizable, like `➡️ AEM Toggle`.
3. Copy the entire raw JavaScript block below and paste it into the **URL** field:

```text
javascript:(function(){var h=window.location.hostname,p=window.location.pathname,s=window.location.search+window.location.hash;if(h.includes("canada.ca")){window.location.href="[https://author-canada-prod.adobecqms.net/editor.html/content/canadasite](https://author-canada-prod.adobecqms.net/editor.html/content/canadasite)"+p+s;}else if(h==="author-canada-prod.adobecqms.net"){var c=p.replace(/^\/editor\.html\/content\/canadasite/,"");window.open("[https://canada-preview.adobecqms.net](https://canada-preview.adobecqms.net)"+c+s,"_blank");}else if(h==="canada-preview.adobecqms.net"){window.location.href="[https://www.canada.ca](https://www.canada.ca)"+p+s;}else{alert("Warning: This shortcut only works on Canada.ca or official AEM domains.");}})();
