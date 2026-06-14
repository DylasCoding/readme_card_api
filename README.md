# github-card-api

> Dynamic SVG card generator for GitHub repositories — auto-fetches description & language from the GitHub API, renders a styled card with language-based accent colors.

## Preview

### Forest Theme

[![Multiplayer2D](https://github-card-api-rust.vercel.app/api/card?user=DylasCoding&repo=Multiplayer2D&theme=forest&tags=Unity%2CC%23&accentFrom=ef4444&accentTo=b91c1c)](https://github.com/DylasCoding/Multiplayer2D)

### Neon Theme

[![Multiplayer2D](https://github-card-api-rust.vercel.app/api/card?user=DylasCoding&repo=Multiplayer2D&theme=neon&tags=Unity%2CC%23&accentFrom=10b981&accentTo=047857)](https://github.com/DylasCoding/Multiplayer2D)

### Light Theme

[![Multiplayer2D](https://github-card-api-rust.vercel.app/api/card?user=DylasCoding&repo=Multiplayer2D&tags=Unity%2CC%23&accentFrom=ef4444&accentTo=b91c1c)](https://github.com/DylasCoding/Multiplayer2D)

### Side-by-side Example

| Dark | Light                                                                                                                                                                                                                 |
|-------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [![](https://github-card-api-rust.vercel.app/api/card?user=DylasCoding&repo=Multiplayer2D&tags=Unity,Netcode,C%23&theme=dark)](https://github.com/DylasCoding/Multiplayer2D) | [![Multiplayer2D](https://github-card-api-rust.vercel.app/api/card?user=DylasCoding&repo=Multiplayer2D&tags=Unity%2CC%23&accentFrom=ef4444&accentTo=b91c1c)](https://github.com/DylasCoding/Multiplayer2D)
|

---

**🔗 Live endpoint:** `https://github-card-api-rust.vercel.app/api/card`

---

## Quick Start

Paste this into any GitHub `README.md` to display a card for your repo:

```markdown
![My Repo](https://github-card-api-rust.vercel.app/api/card?user=YOUR_USERNAME&repo=YOUR_REPO)
```

Make it clickable:

```markdown
[![My Repo](https://github-card-api-rust.vercel.app/api/card?user=YOUR_USERNAME&repo=YOUR_REPO)](https://github.com/YOUR_USERNAME/YOUR_REPO)
```

---

## Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `user` | string | — | **Required.** Your GitHub username |
| `repo` | string | — | **Required.** Repository name (case-sensitive) |
| `theme` | string | `light` | Card color theme — see [Themes](#themes) below |
| `tags` | string | _(none)_ | Comma-separated tech tags, max 4. e.g. `react,typescript,node` |
| `desc` | string | _(auto)_ | Override description text. If omitted, fetched from GitHub API |
| `width` | number | `420` | Card width in pixels |
| `border` | hex | _(theme)_ | Override border color — without `#`, e.g. `border=30363d` |
| `descColor` | hex | _(theme)_ | Override description text color — without `#` |
| `accentFrom` | hex | _(auto)_ | Override accent start color (sidebar + title). Without `#`, e.g. `06b6d4` |
| `accentTo` | hex | _(accentFrom)_ | Override accent end color for gradient. Omit for solid accent |

---

## Themes

Use `theme=<name>` to change the card appearance.

### Dark themes

| Name | Preview |
|------|---------|
| `dark` | Classic GitHub dark |
| `neon` | Deep purple with violet glow |
| `midnight` | Navy blue with steel accents |
| `forest` | Dark green with emerald tones |
| `volcano` | Deep brown-red with orange accents |
| `ocean` | Near-black with cyan highlights |

### Light themes

| Name | Preview |
|------|---------|
| `light` | Clean white (default) |
| `rose` | Soft pink background |
| `mint` | Fresh green-white |
| `sky` | Light blue wash |
| `sand` | Warm amber-yellow |
| `lavender` | Soft purple tint |

**Example:**

```markdown
![My Repo](https://github-card-api-rust.vercel.app/api/card?user=octocat&repo=Hello-World&theme=neon)
```

---

## Adding Tags

Tags appear as colored pills on the card. Well-known tech tags have predefined colors; any other tag will fall back to a default gray style.

```markdown
![My Repo](https://github-card-api-rust.vercel.app/api/card?user=octocat&repo=Hello-World&tags=react,typescript,node,docker)
```

> **Note:** Some characters must be URL-encoded in query strings:
> - `c#` → `c%23`
> - `c++` → `c%2B%2B`
> - Spaces → `+` or `%20`

### Supported tags with colors

`unity` · `netcode` · `c#` · `react` · `firebase` · `javascript` · `typescript` · `kotlin` · `java` · `python` · `rust` · `go` · `vue` · `svelte` · `dart` · `flutter` · `next` · `node` · `tailwind` · `docker` · `graphql`

Any other tag is valid and will render with a default neutral style.

---

## Examples

### Minimal — just user + repo

```markdown
![Hello-World](https://github-card-api-rust.vercel.app/api/card?user=octocat&repo=Hello-World)
```

### With tags and dark theme

```markdown
![Hello-World](https://github-card-api-rust.vercel.app/api/card?user=octocat&repo=Hello-World&tags=node,javascript&theme=dark)
```

### With neon theme and custom description

```markdown
![My Game](https://github-card-api-rust.vercel.app/api/card?user=octocat&repo=my-game&tags=unity,c%23&theme=neon&desc=A+top-down+shooter+built+in+Unity)
```

### Wider card with ocean theme

```markdown
![My API](https://github-card-api-rust.vercel.app/api/card?user=octocat&repo=my-api&tags=go,docker&theme=ocean&width=500)
```

### Side-by-side cards in a table

```markdown
| Game Project | Web Project |
|---|---|
| [![](https://github-card-api-rust.vercel.app/api/card?user=octocat&repo=game&tags=unity,c%23&theme=neon)](https://github.com/octocat/game) | [![](https://github-card-api-rust.vercel.app/api/card?user=octocat&repo=web&tags=react,typescript&theme=sky)](https://github.com/octocat/web) |
```

---

## Accent Color by Language

The sidebar gradient and repo name color are automatically determined by the primary language GitHub reports for your repo — no configuration needed.

| Language | Accent |
|----------|--------|
| C# | Purple |
| JavaScript | Amber |
| TypeScript | Blue |
| Python | Indigo |
| Kotlin | Pink |
| Java | Red |
| Rust | Orange |
| Go | Cyan |
| Vue | Green |
| Swift | Orange |
| Dart | Sky blue |
| Ruby | Rose |
| PHP | Violet |
| C++ | Blue |
| _(other)_ | Indigo (default) |

---

## Notes

- Description and language are **automatically fetched** from the GitHub API. The `desc` parameter overrides this.
- Cards are **cached for 1 hour** (`Cache-Control: public, max-age=3600`) to stay within GitHub API rate limits.
- Description longer than 2 lines is automatically truncated with `…`
- Tags beyond the 4th are silently ignored.
- `border` and `descColor` values are raw hex — **do not include `#`**.
- `user` and `repo` are **case-sensitive** and must match exactly as they appear on GitHub.

### Custom accent color

Override the sidebar and title color with any hex value:

```markdown
![My Repo](https://github-card-api-rust.vercel.app/api/card?user=octocat&repo=Hello-World&theme=dark&accentFrom=06b6d4&accentTo=0891b2)
```

Solid accent (no gradient):

```markdown
![My Repo](https://github-card-api-rust.vercel.app/api/card?user=octocat&repo=Hello-World&theme=dark&accentFrom=f43f5e)
```
