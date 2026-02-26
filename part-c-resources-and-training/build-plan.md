---
description: The Plan
---

# Build Plan

## GitBook Demo Site — Setup Guide

### Quick Reference: Structure to Build

In GitBook, create the following pages in this order. Each page's content is in the companion file `GitBook_Page_Content.md`.

```
📄 About This Resource                  ← Start here (edit the default home page)
│
📁 Part A: Institutional Guidance       ← Create as a "Group" heading
   📄 1. Introduction & Scope
   📄 2. Core Principles
   📄 3. Risks & Limitations of GenAI
   📄 4. Data Protection & Privacy
   📄 5. Acknowledgment & Citation
   📄 6. Guidance for Supervisors
│
📁 Part B: Decision Framework           ← Create as a "Group" heading
   📄 7. The Five-Level Framework
   📄 8. Task-Level Guidance by Phase
   📄 9. Case Studies
   📄 10. Discussion Questions
│
📁 Part C: Resources & Training         ← Create as a "Group" heading
   📄 11. Training & Support
   📄 12. Related Policies & References
│
📁 Tools                                ← Create as a "Group" heading
   📄 Research AI Usage Scale
   📄 PhD Framework Navigator
   📄 Workshop: AI in Academia
```

***

### Step-by-Step Instructions

#### Step 1 — Rename / configure your space

1. In your GitBook organisation, open the space you want to use (or create a new one).
2. Click the space title at the top left and rename it: **`SETU AI in Research — Knowledge Base`**
3. In Space Settings → Visibility, set to **Unlisted** for now (you can make it public later when ready).

#### Step 2 — Edit the home page

1. Click on the default first page (usually called "Welcome" or "Introduction").
2. Rename it to: **`About This Resource`**
3. Paste in the content from Section 1 of `GitBook_Page_Content.md`.

#### Step 3 — Create Group headings

GitBook lets you add "Groups" — these are non-clickable section headings that organise your pages.

1. Click `+` beside any page → choose **"New Group"**
2. Create three groups: `Part A: Institutional Guidance`, `Part B: Decision Framework`, `Part C: Resources & Training`, and `Tools`

#### Step 4 — Add pages under each group

Under each group, click `+` → **"New Page"**. Name each page as listed above and paste in the content.

#### Step 5 — Embed the HTML tools

For each Tools page:

1. In the page body, type `/` and select **"Embed"**
2. Paste the URL of the externally-hosted tool (GitHub Pages, etc.)
3. GitBook will render it as an interactive iframe within the page

#### Step 6 — Add a page description

On each page, click just below the title to add a **page description** (shown in search results and navigation). Short one-liners work well — suggestions are included at the top of each page's content below.

#### Step 7 — Publish

When ready: Space Settings → Visibility → **Public** (or configure Visitor Authentication for the extended CoP tier).

***

{% hint style="success" %}
### Tips

* Use **callout blocks** (type `/callout` or `/hint`) for warnings and important notes — these render beautifully in GitBook.
* The `>` blockquote markdown becomes a callout in GitBook's editor.
* GitBook supports **tables** natively — paste from the content below and they'll render correctly.
* You can import the Word document directly: Space menu → `Import content` → Upload `.docx`. Use this as an alternative to manual copy-paste, then tidy up the formatting.
{% endhint %}
