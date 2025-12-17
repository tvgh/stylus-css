# stylus-css

newcomer from antigravity

Custom Stylus CSS snippets.

## GitHub README masonry userstyle

`github-readme-masonry.user.css` adds Pinterest-like masonry columns for image-heavy README content on GitHub. Paragraphs, list items, and helper `div` blocks that contain images are turned into cards while headings and regular prose stay full width.

### How to use

1. Install the [Stylus browser extension](https://add0n.com/stylus.html).
2. Create a new style scoped to `github.com` and paste the contents of `github-readme-masonry.user.css`, or import the file directly.
3. Tweak the CSS variables at the top of the file to adjust spacing, card radius, and theme tokens.

### Key variables

- `--masonry-min-column`: minimum column width used by the multi-column layout.
- `--masonry-gap`: gutter between masonry cards.
- `--masonry-image-gap`: vertical gap between stacked images inside a card.
- `--masonry-card-padding`: inner padding for each card.
- `--masonry-card-radius`: corner radius for cards and images.
- `--masonry-card-shadow`: drop shadow beneath each card.
- `--masonry-border`: border outline for cards.
- `--masonry-surface`, `--masonry-text`, `--masonry-muted`, `--masonry-accent`: theme colors (light and dark palettes provided).
- `--masonry-prompt-max-height`, `--masonry-prompt-label`: controls folding of long prompt/code blocks (collapsed by default, expands on hover or focus).

### Notes

- Text inside image-bearing paragraphs or list items is visually hidden so the masonry focuses on the imagery; captions added via elements like `figcaption` or `.caption` remain visible.
- Lists that contain images are converted into their own masonry zone while other README content remains full width.
- Long code-block prompts are collapsed by default with a hover/focus-to-expand affordance to avoid occupying excessive page space.
