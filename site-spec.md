# Indexio website: initial specification

## Product purpose

Indexio is a personal resource library for collecting links, references, and short cheat sheets in one place. The first release is intended for one person and may later be shared with a small number of other people.

## Navigation and content model

- **Directory**: top-level collection. Selecting it opens its folders.
- **Folder**: a named collection inside a directory. In list view it expands inline to show subfolders. In grid view it opens a page of subfolders.
- **Subfolder**: optional grouping inside a folder. Selecting it opens its resources.
- **Resource**: a title, URL, detailed description, bullet notes, and optional tags. Selecting it opens a detail page with a prominent link to the source.
- Each directory, folder, and subfolder may have an editable name and icon. Folders may also have a short description.

## Required interactions

- Browse directories, folders, subfolders, and resource detail pages.
- Switch between grid and list views where appropriate.
- Search resource titles, descriptions, notes, and folder names.
- Create, edit, and remove directories, folders, subfolders, and resources.
- Import and export directory data as JSON.
- Use the interface on phones and computers.
- Choose from ten dark pastel gradient backgrounds; remember the selected background in the current browser.
- Customize the profile display name, subtitle, and picture; keep profile settings in the current browser.

## Visual direction

- Near-black background with restrained pastel accents.
- Use the supplied Sakana typeface for display headings; use a clear system sans serif for interface text.
- Responsive layout with a compact phone navigation bar.
- Keep controls readable, keyboard accessible, and visibly focused.

## First mockup behavior

The mockup in `index.html` demonstrates the navigation, sample content, search, edit dialogs, resource details, JSON import/export, ten selectable gradients, and local profile customization. It stores changes, the selected background, and profile settings in the current browser with `localStorage`. This allows interaction testing on one browser, but data does not sync to another device and is not protected by a login or access code.

## Hosting and privacy constraints

GitHub Pages can host the static interface at a `*.github.io` address. It does not provide a database, identity checks, cross-device syncing, or server-side access-code verification. A published static site and its sample content should be treated as publicly reachable. A real multi-device version will need a backend for storage and code verification; a four-digit code should be rate limited by that backend. IP address alone is not a reliable identity across devices or networks.

The attached Sakana license allows embedding for personal use and disallows distributing the font file. Review that license before publishing the font asset with a publicly reachable site; if needed, replace it with a font that permits public web embedding.

## Suggested implementation plan

1. Review the clickable mockup and settle any changes to the hierarchy, editing flows, or visual treatment.
2. Build the static, responsive front end and publish it to GitHub Pages, keeping all user data local while the storage approach is being chosen.
3. If cross-device use is required, add a backend database and access-code flow, plus export/import validation and recovery behavior.
4. Add privacy and accessibility details appropriate to the chosen storage and hosting setup, then verify the site on desktop and mobile before launch.

## Success criteria

- A user can find a saved resource by navigating or searching.
- The hierarchy is understandable on both phone and desktop screens.
- A resource opens with its source link, detailed description, and scan-friendly notes.
- Directory exports can be imported again without losing their nested contents.
- The published version clearly reflects whether the data is local-only or synchronized.
