# Nocturne

A modern, glossy dark theme for [Vencord](https://vencord.dev): deep slate surfaces, a soft violet accent, frosted floating panels, a drifting ambient glow and fluid animations everywhere.

![Version](https://img.shields.io/badge/version-1.2.0-8b7cf6) ![Vencord](https://img.shields.io/badge/client-Vencord-6aa8ff) ![Dark only](https://img.shields.io/badge/mode-dark-151821)

## Features

- **A fully themed palette.** Nocturne recolours Discord's base colour scales, not just a handful of surfaces. Buttons, toggles, radios, selected rows, highlights and hover states all follow the theme.
- **Glossy surfaces.** Panels, menus, tooltips, modals, embeds, reactions and the message box get a soft top sheen, a thin highlight edge and a frosted glass blur.
- **Motion everywhere:**
  - Messages glide in, the channel header drops in and the message box rises in.
  - Channels cascade in when you open a server, and server icons bounce in and wobble on hover.
  - Context menus pop open and their items cascade in one by one.
  - Reactions and mention badges bounce, and emoji wiggle on hover.
  - Links get a sweeping gradient underline, and blockquote bars flow with colour.
  - The typing dots and the message box glow softly, and an ambient glow drifts behind the app.
- **Glossy buttons.** Filled buttons have a light streak that sweeps across on hover, and brand buttons have a shifting gradient.
- **New typography.** The whole app uses [Plus Jakarta Sans](https://fonts.google.com/specimen/Plus+Jakarta+Sans), and code blocks use [JetBrains Mono](https://www.jetbrains.com/lp/mono/).
- **Respects reduce motion.** If *Reduce Motion* is on in Discord or in your OS, every animation and hover movement turns off.
- **Works with every dark variant.** Dark, Darker and Midnight all pick up the theme. Nitro profile themes keep their own colours.
- **No `:has()` selectors**, so Discord's UI stays snappy.

## Installation

### Option 1: Online theme (updates automatically)

1. Open Discord → **Settings** → **Vencord** → **Themes** → **Online Themes**.
2. Paste this link and save:

   ```
   https://raw.githubusercontent.com/MercenaryUSA/Nocturne/main/Nocturne.theme.css
   ```

### Option 2: Local file

1. Download [`Nocturne.theme.css`](Nocturne.theme.css).
2. Open Discord → **Settings** → **Vencord** → **Themes** → **Open Themes Folder**.
3. Drop the file in. On Windows the folder is `%APPDATA%\Vencord\themes`.
4. Enable **Nocturne** in the list.

Use Discord's **Dark** (or Darker / Midnight) appearance. Nocturne is dark-only.

## Customization

Every colour, size and timing is a variable in the `:root` block at the top of the file. Edit them in your local copy, or override them in Vencord's **QuickCSS**:

```css
:root {
    --nc-accent: #ff7ab6;        /* main accent */
    --nc-accent-strong: #f0559b; /* buttons, brand surfaces */
    --nc-accent-2: #ffb86b;      /* second gradient colour */
    --nc-font: "Inter", sans-serif;
    --nc-ambient-speed: 90s;     /* slower background drift */
}
```

| Variable | What it controls |
|---|---|
| `--nc-accent`, `--nc-accent-strong`, `--nc-accent-2` | Accent colour, button colour and the second gradient colour |
| `--nc-bg-0` / `--nc-bg-1` / `--nc-bg-2` | App frame, chat and channel sidebar backgrounds |
| `--nc-surface-1` / `-2` / `-3` | Cards, menus, tooltips and other raised surfaces |
| `--nc-text-strong` / `--nc-text` / `--nc-text-muted` / `--nc-text-subtle` | Text colours |
| `--nc-font`, `--nc-font-code` | UI font and code font |
| `--nc-radius-sm` / `-md` / `-lg` | Corner rounding |
| `--nc-fast` / `--nc-med` / `--nc-slow` | Animation speeds |
| `--nc-ease`, `--nc-ease-spring` | Animation easing curves |
| `--nc-ambient-speed` | Speed of the drifting background glow |
| `--nc-blur`, `--nc-sheen`, `--nc-edge`, `--nc-shadow` | Glass blur, gloss highlight, edge light and drop shadow |

To tone the motion down without turning it off, raise the three speed variables. To keep messages from animating as they load, delete the `.messageListItem_SY_P2T` rule in section 14 of the file.

## Compatibility

- Built for the Discord desktop client with Vencord, against Discord's November 2026 build.
- Discord's CSS class names include build hashes, e.g. `message_SY_P2T`, and these can change when Discord updates. Colours and fonts use Discord's design tokens, so they keep working across updates. If a few animations or gloss effects stop showing up, the class names behind them probably changed. Please open an issue.
- Fonts load from Google Fonts, with jsdelivr as a fallback. If neither is reachable, Discord's default font is used.

## License

Free to use, modify and share. Credit is appreciated.
