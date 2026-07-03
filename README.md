&lt;p align="center"&gt;
  &lt;img src="https://img.shields.io/badge/version-2.0.0-58a6ff?style=flat-square" alt="Version"&gt;
  &lt;img src="https://img.shields.io/badge/license-MIT-3fb950?style=flat-square" alt="License"&gt;
  &lt;img src="https://img.shields.io/badge/platform-Web-8b949e?style=flat-square" alt="Platform"&gt;
  &lt;img src="https://img.shields.io/badge/pure-vanilla_js-f0db4f?style=flat-square" alt="Pure JS"&gt;
&lt;/p&gt;

&lt;h1 align="center"&gt;BundleCraft&lt;/h1&gt;
&lt;p align="center"&gt;&lt;em&gt;A terminal-inspired, zero-dependency web tool for bundling and unbundling HTML projects.&lt;/em&gt;&lt;/p&gt;

&lt;p align="center"&gt;
  &lt;a href="#features"&gt;Features&lt;/a&gt; •
  &lt;a href="#quick-start"&gt;Quick Start&lt;/a&gt; •
  &lt;a href="#usage"&gt;Usage&lt;/a&gt; •
  &lt;a href="#keyboard-shortcuts"&gt;Shortcuts&lt;/a&gt; •
  &lt;a href="#architecture"&gt;Architecture&lt;/a&gt;
&lt;/p&gt;

---

## ✨ Features

| Capability | Description |
|------------|-------------|
| **📦 Bundle to Single HTML** | Merge `.html`, `.css`, and `.js` files into one self-contained, portable HTML file |
| **🗂️ Unbundle to Files** | Extract inline `&lt;style&gt;` and `&lt;script&gt;` blocks into separate, well-organized source files |
| **🖱️ Drag & Drop** | Intuitive drag-and-drop interface with visual hover states and file type detection |
| **⚡ Minification** | Optional CSS / JS / HTML minification to squeeze every byte out of your output |
| **🎨 Prettification** | Reverse mode: auto-format extracted code with clean indentation and structure |
| **👁️ Live Preview** | Real-time, sandboxed iframe preview of your bundled output |
| **🕐 History** | Persistent session history stored in `localStorage` — never lose track of past conversions |
| **🌗 Light & Dark Mode** | Full terminal-inspired dark theme + clean light mode, with instant toggle |
| **⌨️ Keyboard Driven** | Power-user shortcuts for every major action |
| **📱 Responsive** | Collapsible sidebar and adaptive layout for mobile, tablet, and desktop |

---

## 🚀 Quick Start

No build step. No dependencies. No server required.

```bash
# 1. Save the application
curl -o bundlecraft.html &lt;url&gt;

# 2. Open in your browser
open bundlecraft.html        # macOS
xdg-open bundlecraft.html    # Linux
start bundlecraft.html       # Windows

📖 Usage
Bundling (Multi-File → Single HTML)
Navigate to Bundle to HTML in the sidebar
Drag & drop or browse for your project files:
One .html entry point (required)
Any linked .css files
Any linked .js files
Toggle your preferred options:
☑️ Minify Output — strips whitespace and comments
☑️ Base64 Assets — (placeholder for future image/font inlining)
☑️ Defer Scripts — adds defer to extracted inline scripts
☐ Source Map — includes inline source map for debugging
Click 🔨 Bundle Files (or press Ctrl + Enter)
Copy to clipboard or Download the resulting single HTML file
Smart Path Resolution: BundleCraft automatically resolves relative paths (./styles.css, ../js/app.js) by matching basenames across your uploaded files.
Unbundling (Single HTML → Multi-File)
Navigate to Unbundle to Files in the sidebar
Drop a bundled/single-file HTML onto the zone
Configure extraction options:
☑️ Prettify Output — formats all extracted code
☑️ Separate Modules — splits each <style> / <script> block into its own file
☑️ Add Comments — inserts source-location headers for traceability
Click 🔧 Extract Files
Download individual files or grab the entire set as sequential downloads
Live Preview
Switch to the Live Preview tab to see your bundled HTML rendered in a sandboxed <iframe>. The preview updates automatically after every successful bundle operation (if Auto Preview is enabled in Settings).
⌨️ Keyboard Shortcuts
Table
Shortcut	Action
Ctrl + L	Toggle Light / Dark theme
Ctrl + Enter	Execute current operation (Bundle or Extract)
Ctrl + Shift + X	Clear all data and reset workspace
Ctrl + B	Toggle sidebar (mobile & desktop)
Esc	Close any open modal
🏗️ Architecture
BundleCraft is engineered as a single-file, zero-dependency application. Every feature — from parsing to minification to ZIP-like download sequencing — is implemented with native Web APIs.
plain
┌─────────────────────────────────────────┐
│  UI Layer (Vanilla CSS + DOM)           │
│  ├── Sidebar Navigation                 │
│  ├── Drag-and-Drop Zones                │
│  ├── Terminal Console                   │
│  └── Toast Notifications                │
├─────────────────────────────────────────┤
│  Engine Layer (Native APIs)             │
│  ├── DOMParser (HTML parsing)           │
│  ├── XMLSerializer (HTML serialization) │
│  ├── FileReader (File ingestion)        │
│  ├── Blob / URL.createObjectURL (DL)    │
│  └── localStorage (History persistence)  │
├─────────────────────────────────────────┤
│  Transform Layer (Pure JS)              │
│  ├── CSS Minifier / Prettifier          │
│  ├── JS Minifier / Prettifier           │
│  ├── HTML Minifier / Prettifier         │
│  └── Smart Path Resolver                │
└─────────────────────────────────────────┘
Why No Build Tools?
Portability: One file. Email it, USB it, host it on a static CDN.
Privacy: Everything happens client-side. Your source code never leaves your machine.
Longevity: No npm rot. No broken dependencies in 2029.
🛠️ Advanced Configuration
All preferences are persisted to localStorage and survive page refreshes:
Table
Setting	Key	Default
Dark Mode	bundlecraft_theme	dark
Auto Preview	settingAutoPreview	true
Line Numbers	settingLineNumbers	true
Word Wrap	settingWordWrap	true
Conversion History	bundlecraft_history	[]
🧪 Supported File Types
Table
Extension	Role in Bundle	Role in Unbundle
.html, .htm	Entry point (required)	Source to extract from
.css	Linked stylesheet (inlined)	Extracted output
.js	Linked script (inlined)	Extracted output
.txt	Auxiliary (ignored by parser)	—
🐛 Troubleshooting
Table
Symptom	Likely Cause	Fix
"No HTML entry point detected"	You uploaded only CSS/JS	Include at least one .html file
CSS/JS not inlined	Path mismatch	Ensure filenames match href / src attributes exactly
Preview shows blank	Missing <body> content	Check that your HTML is valid
History empty	First visit / cleared	Perform a conversion to populate
📝 Changelog
v2.0.0
Full terminal-inspired UI redesign
Added unbundle (extraction) mode
Added live preview with sandboxed iframe
Added persistent history & settings
Added keyboard shortcuts
Added light/dark theme toggle
Added mobile-responsive sidebar
📄 License
MIT License — free for personal and commercial use. No attribution required.
<p align="center">
  <sub>Crafted with precision. No frameworks. No dependencies. Just the platform.</sub>
</p>
```