# Tool Icons

Reusable local icon assets for supported agents, editors, terminals, and
multiplexers. These files are kept at the repository root so the website,
README, app UI, video generation, and VM/browser artifacts can share the same
source files.

Use `assets/icons/<name>` from repository-root contexts. The website references
them as `../assets/icons/<name>` because `site/index.html` is commonly opened
directly from disk during local review.

Product names and marks belong to their respective owners. Do not treat these
files as cctop-owned artwork.

`claude-code.svg` is the Claude Code wordmark used in larger agent cards;
`claude.svg` is the compact Claude mark for small chips.

Apple Terminal intentionally has no vendored icon here; use a text label unless
Apple publishes a suitable reusable asset for this context.

Ghostty's icon is included because it is used as a supported-tool identifier on
the website, but upstream licensing/trademark signals are more restrictive than
most of the other entries. Revisit this before using it in broader promotional
contexts.
