
# 🌐 HESS/ DFH — Why You Still Need a “Main Site” (Even though the 5 or 10 anchor Stack Is Separate)
### A human-friendly repo explaining how the main website + the 10 anchors explains how all links together

SFH (Semantic First-Hop) / DFH (Deterministic First-Hop) is **a machine-readable grounding layer**, not a human website.

But here’s the part that confuses people:

✅ **The HESS/DFH layer is separate from your website**  
✅ **…and you STILL need a real website to point back to**  
Because humans (and businesses, and buyers, and press, and regulators, and partners) need a **human-readable home** that matches the claims the machine layer is making.

Think of it like this:

- **Main website** = the *city* people live in (human navigation + trust)
- **HESS/DFH stack** = the *street signs + address registry* (machine navigation + deterministic first-hop)

---

## ✅ What this repo explains

This repo explains:

- Why the **main site must exist**
- Why the **stack is separate**
- How the **stack points back to the main site**
- How the **10 anchors connect together**
- Why the **sitemap anchor is the “map of everything”** machines can follow

---

# 1) Why you still need a main site

HESS/DFH is *not* meant to replace your website.

A domain needs a human-facing site because:

### ✅ 1) Humans need a place to verify reality
People need:
- “About”
- “Contact”
- “Legal”
- “Products”
- “Policies”
- “Press / announcements”
- “Documentation”

Without a main site, the stack is just claims floating in space.

### ✅ 2) The stack must point to canonical pages
Your stack needs real URLs to reference:
- official entity pages
- official definitions
- official policies
- official source pages
- official product pages

Those pages live on the main site (or the official systems it controls).

### ✅ 3) Search engines & AI need a trust loop
The stack says:
> “These are my official meanings and canonical sources.”

The main site says:
> “Yes — this is the real org, these are the real pages, and here is the public proof.”

That circular reinforcement is **how authority forms**.

---

# 2) Why the HESS/DFH layer is separate from the main site

Because websites are messy.

Websites change constantly:
- redesigns
- CMS migrations
- URL changes
- content edits
- marketing pages
- A/B tests

AI can’t rely on that chaos as a stable starting point.

So the HESS/DFH stack lives separately at:

https://yourdomain.com/.well-known/stack
That file is meant to be:

stable

minimal

deterministic

machine-readable

consistent across redesigns

It’s the first hop machines can always trust exists.

3) The “link-back” rule (how the stack connects to the website)
The stack must point to your main site in multiple ways:

✅ Canonical root (the official domain)
✅ Official entity page (About / Organization page)
✅ Canonical URL rules (preferred host, https, trailing slashes, etc.)
✅ Sitemap index (the machine map of all canonical pages)
✅ Sources (where the truth/claims originate)

So even though SFH/DFH is separate, it is tied to the main site through canonical references.

4) The 10 Anchors (5 meaning + 5 provenance) and how they link together
Meaning Anchors (what things are)
These tell machines “what you mean.”

1) /type
Defines the “classes” you publish.
Examples:

Organization

Product

Article

Person

Dataset

2) /entity
Defines the entities you claim exist on the domain.
Examples:

your company entity

your products as entities

your brands

your authors

3) /url
Defines canonical URL rules + key canonical pages.
Examples:

canonical host

canonical paths

official pages that represent each entity

4) /canonical
Defines the “preferred identifiers” and what is considered authoritative.
Examples:

primary IDs

external IDs (Wikidata, ORCID, etc.)

canonical naming rules

5) /sitemap
Defines where the full map of your canonical pages lives.
Examples:

sitemap index

segmented sitemaps (products, posts, docs)

update frequencies (optional metadata)

Provenance Anchors (where claims come from)
These tell machines “why you should trust the trail.”

6) /authority
Who is allowed to claim meaning for this domain?
Examples:

org identity

ownership proof references

official controlling entity

7) /source
Where does the domain’s info come from?
Examples:

official APIs

official CMS feeds

official databases

official documents

8) /timestamp
When were these claims last updated?
Examples:

lastModified per anchor

version dates

update cadence

9) /license
What are the usage rights?
Examples:

copyright

open licenses

content reuse rules

10) /integrity
How can a machine verify the file wasn’t tampered with?
Examples:

hashes of anchors

signing strategy (optional)

integrity checks

5) The sitemap is the bridge between “meaning” and “everything on the site”
This is the key mental model:

The anchors define rules + meaning

The sitemap lists every canonical page

Together they let machines go from:
“What is this domain?” → “What exists here?” → “Where are all the official pages?”

So the sitemap is how the stack stops being “just a dictionary” and becomes a navigable map.

The sitemap connects to the pillars like this:
/type says “what kinds of pages/entities exist”

/entity lists the actual things

/url says “here are the official pages for those entities”

/canonical says “here are the preferred identifiers”

/sitemap says “here is the full list of canonical URLs, at scale”

In other words:

The pillars define the rules.
The sitemap proves the inventory.

6) Minimal example layout (repo structure)
txt
Copy code
sfh-dfh-main-site-linkback/
├─ README.md
├─ examples/
│  ├─ well-known-stack.jsonld
│  ├─ sitemap-index.xml
│  ├─ sitemap-products.xml
│  ├─ sitemap-pages.xml
│  └─ anchor-map.md
└─ diagrams/
   └─ linkback-flow.md
7) Example: the .well-known/stack file (human-readable comments included)
This is a simplified example to show the linkback concept.
In practice you’ll expand each anchor into its own file.

json
Copy code
{
  "@context": "https://schema.org",
  "@type": "DefinedTermSet",
  "name": "SFH/DFH Stack — example.com",
  "url": "https://example.com/.well-known/stack",

  "mainSite": "https://example.com/",
  "aboutPage": "https://example.com/about",
  "contactPage": "https://example.com/contact",

  "anchors": {
    "type": "https://example.com/.well-known/type",
    "entity": "https://example.com/.well-known/entity",
    "url": "https://example.com/.well-known/url",
    "canonical": "https://example.com/.well-known/canonical",
    "sitemap": "https://example.com/.well-known/sitemap",

    "authority": "https://example.com/.well-known/authority",
    "source": "https://example.com/.well-known/source",
    "timestamp": "https://example.com/.well-known/timestamp",
    "license": "https://example.com/.well-known/license",
    "integrity": "https://example.com/.well-known/integrity"
  }
}
8) Example: the sitemap index (shows how “everything” becomes discoverable)
xml

<?xml version="1.0" encoding="UTF-8"?>
<sitemapindex xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <sitemap>
    <loc>https://example.com/sitemap-pages.xml</loc>
    <lastmod>2025-12-14</lastmod>
  </sitemap>
  <sitemap>
    <loc>https://example.com/sitemap-products.xml</loc>
    <lastmod>2025-12-14</lastmod>
  </sitemap>
</sitemapindex>
9) The full “link-up” flow (plain English)
A machine hits:
/.well-known/stack

The stack tells it:

what anchors exist (10 pillars)

where the sitemap index is

what the canonical rules are

The machine goes to /sitemap and pulls the sitemap index.

The sitemap index points to every canonical URL at scale.

The machine resolves pages:

using /url rules

matching entities from /entity

applying canonical identity rules from /canonical

filtering/validating provenance via /authority /source /timestamp /license /integrity

That’s how the stack and the main site become one system:

stack = deterministic entry + rules

main site = canonical content + public verification

sitemap = complete inventory bridge

10) What needs to be on the main site (minimum)
You don’t need a huge site. You need a trustable human layer that matches the claims:

Minimum recommended pages:

/about (who you are)

/contact (how to reach you)

/legal or /terms + /privacy

canonical pages for anything you list as an /entity

That’s enough for the stack to point to something real.
