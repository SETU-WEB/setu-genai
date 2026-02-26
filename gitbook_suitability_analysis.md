# GitBook\_Suitability\_Analysis

## Managing and Communicating SETU's Approach to AI in Research

_Prepared following review of project files, January–February 2026_

***

## 1. Overview of Materials Reviewed

The following files (January 11, 2026 onwards) informed this analysis:

| File                                                          | Type                | Purpose                                                                                  |
| ------------------------------------------------------------- | ------------------- | ---------------------------------------------------------------------------------------- |
| `genai-research-guidance.html`                                | Single-page web app | Full guidance document — navigable, styled, interactive                                  |
| `genai-research-guidance.docx`                                | Word document       | Source document for the guidance                                                         |
| `AI_Research_Scale.html`                                      | Single-page web app | 5-level AI usage framework for PhD research, tabbed by phase                             |
| `AI_Use_Scale.html`                                           | Single-page web app | Workshop slide deck on the spectrum of AI use                                            |
| `Reseasrch_AI_CaseStudy.docx`                                 | Word document       | Case study analysis with the 5-level framework                                           |
| `Draft Guidance Gen AI in Research October 2025 KM.pdf/.docx` | Draft guidance      | Earlier draft (KM annotations), attributed to SETU's Working Group on Gen AI in Research |
| `AI_as_a_Symbiotic_Design_Partner.pdf`                        | PDF                 | Contextual resource on AI as a design partner                                            |

What the content represents: A mature, principles-based institutional framework for responsible AI use in research, grounded in the EU Living Guidelines and developed by SETU's AI Steering Committee subgroup. The guidance covers core principles (Reliability, Honesty, Respect, Accountability), a 5-level AI involvement spectrum, phase-by-phase PhD guidance, case studies, and data protection guidance. The three HTML files represent the forward edge of this work — attempting to make the guidance more interactive and accessible than a static document.

***

## 2. Your Requirements: A Summary

| Tier     | Audience                                                      | Access Level      |
| -------- | ------------------------------------------------------------- | ----------------- |
| Internal | SETU community of practice (staff, PGR students, supervisors) | Full edit         |
| Extended | Partner universities, cross-institutional CoP                 | Read + contribute |
| External | General public, other institutions                            | Read only         |

Plus: the ability to **host the HTML single-page applications** as living tools within the platform.

***

## 3. What GitBook Is (and How It Fits)

GitBook is a documentation and knowledge management platform built around structured, versioned content. It is increasingly used by universities and research organisations for exactly this kind of "living guidance" work. Its core strengths map well to your context:

* **Living documents** — content is versioned, with full change history, which is directly aligned with your "Living Document — Updated Regularly" framing.
* **Professional presentation** — clean, structured output resembling a well-organised website or knowledge base, appropriate for both internal and external audiences.
* **Git-backed** — optionally syncs with GitHub or GitLab, which may be valuable if SETU's technical staff want programmatic control over content.
* **Role-based access** — different users can be granted editor, reviewer, or read-only access at the space or organisation level.

***

## 4. Mapping Your Three-Tier Access Model to GitBook

### Tier 1: Internal SETU Community of Practice — Full Edit

GitBook supports **organisation members** with editor-level access. You would:

* Create a GitBook **Organisation** for SETU.
* Invite internal staff and research students as **Editors** or **Admins** within that organisation.
* Use GitBook's **Change Requests** workflow (analogous to pull requests) to manage contributions — contributors propose changes, which are reviewed before merging into the live space. This prevents accidental overwrites in a large internal community.
* SETU's institutional SSO (if SAML/OIDC is available) can be connected to GitBook's **Enterprise** plan, enabling seamless sign-in for staff without requiring separate accounts. This is strongly recommended for a large internal CoP.

Assessment: Well supported. The change request workflow is particularly valuable for a community of practice where many people want to contribute but quality control is important.

### Tier 2: Cross-University Community of Practice — Read + Contribute

This is the most nuanced requirement and GitBook handles it via two mechanisms:

* **Visitor Authentication (Pro/Enterprise):** External partners from other universities can be granted access to a non-public space via a shared token or SSO federation. They can read all content and use **comments** and **page reactions** to engage.
* **Change Requests from guests:** GitBook allows guest contributors to submit change requests for review without having full editor access. This is the "contribute without full edit" model you need — other universities can propose additions, case studies, or amendments, which your internal CoP reviews and approves.
* Alternatively, you could open a dedicated **"Contributions" space** within the same organisation, where external partners have editor rights to a sandboxed area only.

Assessment: Achievable, but requires a deliberate structure. You will need to decide whether the extended CoP operates in the same space as your internal one (with gated change requests) or in a dedicated collaborative space. The former is cleaner; the latter is safer.

### Tier 3: External / Public — Read Only

GitBook spaces can be published publicly with no authentication required. A public-facing space would present your finalised guidance, framework, and case studies to any external visitor.

* Public spaces are indexed by search engines, enhancing discoverability.
* You can set a **custom domain** (e.g., `ai-research.setu.ie`) for the public-facing space on the Pro or Enterprise plan.
* GitBook's public spaces render cleanly on mobile and desktop, with accessible navigation — appropriate for communicating to a broad audience.

Assessment: Excellently supported. This is GitBook's primary use case.

***

## 5. Content Structure: How Your Materials Map to GitBook

Your existing materials map very naturally onto a GitBook space structure. A suggested organisation:

```
SETU AI in Research Knowledge Base
│
├── 📌 About This Resource          (purpose, how to use, version history)
│
├── Part A: Institutional Guidance
│   ├── Introduction & Scope
│   ├── Core Principles             (Reliability, Honesty, Respect, Accountability)
│   ├── Risks & Limitations of GenAI
│   ├── Data Protection & GDPR
│   ├── Acknowledgment & Citation
│   └── Guidance for Supervisors
│
├── Part B: Decision Framework
│   ├── The Five-Level AI Usage Framework
│   ├── Task-Level Guidance by Research Phase
│   ├── Case Studies                (from Reseasrch_AI_CaseStudy.docx)
│   └── Discussion Questions
│
├── Part C: Resources & Training
│   ├── Training & Support
│   └── Related Policies & References
│
└── 🛠️ Tools                        (embedded or linked interactive tools)
    ├── Research AI Usage Scale
    ├── PhD Framework Navigator
    └── Workshop Slides
```

Your `genai-research-guidance.docx` already has this structure — GitBook can import Word documents directly, preserving headings, lists, and tables, which would give you a solid first draft with minimal rework.

***

## 6. The HTML Tools: The Key Challenge

This is the most important technical consideration, and it needs to be addressed directly.

GitBook does not natively host or execute custom HTML/JavaScript single-page applications. It is a documentation platform, not a web hosting service. This means the three tools you have built:

* `genai-research-guidance.html` — interactive guidance navigator
* `AI_Research_Scale.html` — PhD AI usage framework with tabbed phases
* `AI_Use_Scale.html` — workshop presentation slides

cannot simply be uploaded into GitBook and run from within it.

What GitBook can do with your tools:

Option A — Embed via iframe (recommended):\
GitBook supports embedding external URLs as iframes using its built-in "Embed" content block. If you host your HTML tools on a static hosting service (GitHub Pages, Netlify, or Vercel — all free for static files), you can embed them directly into GitBook pages. Visitors would interact with the tools without leaving GitBook. This is the most seamless option and preserves the full interactivity of your existing tools.

Option B — Link to externally hosted tools:\
A simpler but less integrated approach — host the tools externally and add prominent links/buttons from the relevant GitBook pages. This is faster to set up but creates a less unified experience.

Option C — Rebuild tool content as native GitBook pages:\
The _content_ of the AI usage framework could be reproduced as structured GitBook pages with tables, callout blocks, and toggles. This would lose the custom interactivity (e.g., the tabbed phase navigation in `AI_Research_Scale.html`) but would be fully native and maintenance-free. Appropriate for more static content.

Recommendation: Use **Option A** for `AI_Research_Scale.html` and `AI_Use_Scale.html` (which have meaningful interactivity worth preserving) and **Option C** for the guidance content (which is already being migrated into the docx/GitBook format anyway). GitHub Pages is free, trivially simple to set up, and SETU may already have a GitHub organisation that could host these files. This would also provide a stable, citable URL for each tool.

***

## 7. GitBook's Plan Requirements for Your Use Case

| Requirement                           | Free Plan | Pro Plan | Enterprise |
| ------------------------------------- | --------- | -------- | ---------- |
| Public space (read-only external)     | ✅         | ✅        | ✅          |
| Multiple spaces/collections           | Limited   | ✅        | ✅          |
| Custom domain                         | ❌         | ✅        | ✅          |
| Visitor authentication (extended CoP) | ❌         | ✅        | ✅          |
| SSO / SAML integration                | ❌         | ❌        | ✅          |
| Unlimited editors                     | ❌         | ✅        | ✅          |
| Change requests & review workflow     | ✅         | ✅        | ✅          |
| Word document import                  | ✅         | ✅        | ✅          |
| Iframe embeds                         | ✅         | ✅        | ✅          |

For your use case — multiple tiers, institutional SSO, custom domain, and cross-university access — the **Pro plan** covers most needs. **Enterprise** adds SSO integration, which would be valuable at scale but is not strictly required to begin.

Note: GitBook offers **education/non-profit pricing** that SETU should enquire about — this can significantly reduce costs for institutional deployments.

***

## 8. Strengths of GitBook for This Use Case

* **Living document alignment:** Version history, change requests, and "last updated" metadata directly support the "Living Document" framing already in your guidance.
* **EU research integrity framing:** GitBook's structured, citation-friendly format supports the transparency principles (Honesty, Accountability) that run through your framework.
* **Low barrier to contribution:** The change request model allows researchers and supervisors who are not technical to propose edits through a web interface — no Git knowledge required.
* **Discoverability:** Public spaces are search-indexed. Other institutions looking for AI-in-research guidance may find SETU's resource, supporting the external communication goal.
* **Import from Word:** Your existing docx files can be imported directly, giving you a running start.
* **Multilingual potential:** GitBook supports content in any language, relevant if the extended CoP spans institutions with different language needs.

***

## 9. Limitations and Considerations

* **No native tool hosting:** As discussed, the HTML SPAs require external hosting. This is manageable but adds a dependency.
* **Limited community/forum features:** GitBook is a documentation tool, not a community platform. Comments are page-level and relatively lightweight. If the CoP requires richer discussion (threaded conversations, polls, working groups), you would need a complementary tool (e.g., a Teams channel or Discourse forum) alongside GitBook.
* **Vendor dependency:** Content lives in GitBook's infrastructure. The GitHub sync option mitigates this — keeping a Git-backed copy of all content in your own repository is strongly recommended.
* **Change request volume:** In a large active CoP, managing many concurrent change requests requires editorial process. Consider appointing section owners within the internal CoP.
* **AI\_Use\_Scale.html as a presentation:** The workshop slides tool is somewhat specialised — it may be better distributed as a downloadable file or linked separately rather than embedded, given it's presentation-format rather than reference-format.

***

## 10. Summary Assessment

| Requirement                        | GitBook Suitability    | Notes                                            |
| ---------------------------------- | ---------------------- | ------------------------------------------------ |
| Internal CoP with full edit        | ✅ Strong               | Change requests + editor roles                   |
| Extended CoP read + contribute     | ✅ Good                 | Visitor auth + guest change requests             |
| External read-only                 | ✅ Excellent            | Core GitBook use case                            |
| Living document / versioning       | ✅ Excellent            | Built-in, central feature                        |
| Migration of existing docx content | ✅ Good                 | Word import available                            |
| Hosting HTML tools natively        | ⚠️ Not possible        | Requires external hosting + iframe embed         |
| Institutional SSO                  | ✅ With Enterprise plan | Or workable without on Pro                       |
| Custom domain                      | ✅ On Pro+              | e.g. ai-research.setu.ie                         |
| Community discussion/forum         | ⚠️ Limited             | Page comments only — may need supplementary tool |

Overall: GitBook is a well-suited platform for this project. It handles the documentation, access tiering, and living-document requirements very well. The one meaningful limitation — hosting the interactive HTML tools — is addressable with a simple external static hosting solution. The existing documents, particularly `genai-research-guidance.docx`, would migrate cleanly and form an excellent foundation for a GitBook space.

{% hint style="info" %}
Recommended next step: run a proof of concept using GitBook's free plan: import the guidance document, structure the space as outlined above, and test embedding one of the HTML tools hosted on GitHub Pages — this would validate the approach before committing to a paid plan.
{% endhint %}

{% stepper %}
{% step %}
### Proof-of-concept: Import guidance

* Import `genai-research-guidance.docx` into a new GitBook space.
* Verify headings, lists, and tables migrated correctly.
* Assign one or two internal editors to manage the space.
{% endstep %}

{% step %}
### Proof-of-concept: Host and embed a tool

* Host one HTML tool (e.g., `AI_Research_Scale.html`) on GitHub Pages, Netlify, or Vercel.
* Create a GitBook page and embed the hosted URL using GitBook's Embed block.
* Confirm interactivity and cross-origin embedding behaviour.
{% endstep %}

{% step %}
### Proof-of-concept: Access & contribution model

* Configure space visibility (private/public) and invite a small set of extended CoP members.
* Test contributor workflows: comments, page reactions, and submitting a change request as an external contributor.
* Evaluate whether Visitor Authentication or a dedicated Contributions space is preferable.
{% endstep %}
{% endstepper %}

***

_Analysis based on review of SETU project files, January–February 2026. GitBook feature details based on documentation available as of early 2026 — verify current pricing and plan features at gitbook.com._
