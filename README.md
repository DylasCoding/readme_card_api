# GitHub Repository Card API

Generate beautiful SVG cards for GitHub repositories.

---

## Preview

### Default

![Default Card](https://github-card-api-rust.vercel.app/api/card?user=DylasCoding\&repo=Multiplayer2D)

### Dark Theme

![Dark Card](https://github-card-api-rust.vercel.app/api/card?user=DylasCoding\&repo=Multiplayer2D\&theme=dark)

### Unity Project

![Unity Card](https://github-card-api-rust.vercel.app/api/card?user=DylasCoding\&repo=Multiplayer2D\&theme=dark\&tags=Unity,Netcode,C%23,Firebase)

### Fully Customized

![Custom Card](https://github-card-api-rust.vercel.app/api/card?user=DylasCoding\&repo=Multiplayer2D\&theme=dark\&width=550\&tags=Unity,Netcode,C%23,Firebase\&border=%238b5cf6\&descColor=%2394a3b8)

---

## Usage

### Markdown

```md
![Repository Card](https://github-card-api-rust.vercel.app/api/card?user=USERNAME&repo=REPOSITORY)
```

### HTML

```html
<img src="https://github-card-api-rust.vercel.app/api/card?user=USERNAME&repo=REPOSITORY" />
```

---

## Parameters

| Parameter   | Description                  | Default                |
| ----------- | ---------------------------- | ---------------------- |
| `user`      | GitHub username              | `DylasCoding`          |
| `repo`      | Repository name              | `Multiplayer2D`        |
| `desc`      | Custom description           | Repository description |
| `tags`      | Comma-separated tags (max 4) | None                   |
| `theme`     | `light` or `dark`            | `light`                |
| `border`    | Border color (HEX)           | Auto                   |
| `descColor` | Description text color (HEX) | Auto                   |
| `width`     | Card width in pixels         | `420`                  |

---

## Theme

### Light Theme

```text
/api/card?theme=light
```

### Dark Theme

```text
/api/card?theme=dark
```

Example:

```text
/api/card?user=DylasCoding&repo=Multiplayer2D&theme=dark
```

---

## Custom Description

Override the repository description.

```text
/api/card?desc=2D%20Multiplayer%20RPG%20Game
```

Example:

```text
/api/card?user=DylasCoding&repo=Multiplayer2D&desc=2D%20Multiplayer%20RPG%20Game
```

---

## Custom Tags

Add technology badges below the description.

Maximum: **4 tags**

```text
/api/card?tags=Unity,Netcode,C#,Firebase
```

Example:

```text
/api/card?user=DylasCoding&repo=Multiplayer2D&tags=Unity,Netcode,C#,Firebase
```

### Supported Tag Colors

| Tag        | Style    |
| ---------- | -------- |
| Unity      | Green    |
| Netcode    | Blue     |
| C#         | Purple   |
| React      | Sky Blue |
| Firebase   | Orange   |
| JavaScript | Yellow   |
| TypeScript | Blue     |
| Kotlin     | Pink     |
| Java       | Red      |
| Python     | Indigo   |
| Rust       | Orange   |
| Go         | Cyan     |
| Vue        | Green    |
| Svelte     | Rose     |

Unknown tags automatically use the default style.

---

## Custom Border Color

Supports any HEX color.

```text
/api/card?border=%238b5cf6
```

Examples:

| Color  | HEX       |
| ------ | --------- |
| Purple | `#8b5cf6` |
| Blue   | `#3b82f6` |
| Green  | `#22c55e` |
| Red    | `#ef4444` |
| Orange | `#f97316` |

> Remember to encode `#` as `%23`.

---

## Custom Description Color

```text
/api/card?descColor=%2394a3b8
```

Examples:

| Color       | HEX       |
| ----------- | --------- |
| Slate       | `#64748b` |
| Light Slate | `#94a3b8` |
| Amber       | `#f59e0b` |
| White       | `#ffffff` |

---

## Custom Width

Default width is **420px**.

```text
/api/card?width=600
```

Examples:

```text
width=350
width=420
width=500
width=700
```

---

## Complete Example

```text
https://github-card-api-rust.vercel.app/api/card?user=DylasCoding&repo=Multiplayer2D&theme=dark&width=550&tags=Unity,Netcode,C#,Firebase&border=%238b5cf6&descColor=%2394a3b8
```

---

## Notes

* SVG is generated dynamically.
* Repository description is fetched automatically from GitHub.
* Repository language is fetched automatically from GitHub.
* Accent colors are automatically selected based on the repository language.
* Supports GitHub README, portfolio websites, and project showcases.
