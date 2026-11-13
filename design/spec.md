# MDigital design spec (logo kit, 2026-11)

Source: `mdigital-logo-kit.zip`. Brand: peak + sun mark, Sora wordmark, cyan to blue gradient on Midnight. Keep the site dark by default; add light via `data-theme="light"`.

## Decisions
| Was | Now | Why |
|---|---|---|
| Indigo `#6366F1` / `#818CF8` | Cyan `#2BF5E3` + Blue `#3B82F6` | kit colours |
| Bg `#0A0A0F` (near black) | `#071428` page, `#0A1D3B` cards | kit Midnight |
| Logo = lucide `code-2` in indigo chip | `brand/svg/logo-horizontal-for-dark-bg.svg` | real logo |
| Inter everywhere | Sora 600/700 headings, Inter body | kit typeface |
| White text on gradient button | Midnight text `#0A1D3B` | white on `#2F7BF5` = 3.98:1 fails AA; Midnight on Cyan = 12.2:1 |
| Rainbow icon colours (yellow, purple, orange, green) | one family: cyan chip on dark, blue on light | one accent system |

## Contrast (WCAG AA: 4.5 text, 3 large/UI)
| Pair | Ratio |
|---|---|
| Mist `#E8EFFA` on `#071428` | 15.93 |
| Mist on `#0A1D3B` | 14.51 |
| Muted `#9FB3D1` on `#071428` / `#0A1D3B` | 8.64 / 7.86 |
| Cyan `#2BF5E3` on `#071428` / `#0A1D3B` | 13.40 / 12.20 |
| Blue-400 `#6AA2FA` on `#071428` / `#0A1D3B` | 7.16 / 6.52 |
| Midnight on Cyan (button) | 12.20 |
| Midnight on Blue `#3B82F6` (gradient end) | 4.56 |
| Midnight `#0A1D3B` on white / Mist | 16.78 / 14.51 |
| Blue-700 `#1D5FD1` on white / Mist (light accent) | 5.82 / 5.03 |
| Slate `#4A5F82` on white / Mist (light muted) | 6.46 / 5.59 |
| FAIL: Cyan on white | <2 (never use) |
| FAIL: Blue `#3B82F6` text on Mist | below 4.5 (never use) |

## Components
**Logo (nav)** horizontal, dark-bg file on dark, light-bg file on light. Height 32px mobile, 40px at lg. Min width 120px. Clear space = sun diameter. Footer: same logo at 32px.
**Favicon** `<link rel="icon" href="design/brand/favicon/favicon.svg" type="image/svg+xml">`, plus `favicon.ico`, `apple-touch-icon-180.png`, `android-chrome-192/512.png`. Move to site root on deploy.
**Button primary** bg gradient-brand, text Midnight, 600 weight, 0.875rem, padding 0.625rem 1.25rem, radius 0.75rem. Hover: lift 2px + glow `0 10px 30px var(--glow)`. Focus: 2px ring cyan, offset 2px. Disabled: 50% opacity.
**Button secondary** transparent bg tint, 1px `--border-strong`, text `--text`. Hover: border `--accent`.
**Card** bg `--surface`, 1px `--border`, radius 1.25rem, padding 1.5rem (2rem lg). Hover: border `--card-border-hover`, lift 4px (was 8). Do: one accent per card. Don't: stack glow and gradient.
**Icon chip** 2.5rem square, radius 0.75rem, bg `--icon-chip-bg`, icon `--icon-chip-fg`, Lucide 1.25rem stroke 1.75. Same icon style everywhere.
**Headings** Sora 700, h1 clamp(2.5rem, 6vw, 4.5rem)/1.05, h2 clamp(2rem, 4vw, 3rem)/1.15, h3 1.25rem/1.3. Gradient text: `--gradient-brand`, headline keyword only, once per section max.
**Body** Inter 400, 1rem/1.65, colour `--text-muted` for secondary.
**Section** padding 6rem lg, 4rem mobile. Container max 72rem.
**Background orbs** replace indigo with cyan 12% and blue 12% opacity, blur 100px. Max two.
**Scrollbar** track `--bg`, thumb `--mid-700`, hover `--cyan-400`.
**Status dots** (code mockup window): keep red/yellow/green only inside the mockup chrome.

## Tailwind CDN config (paste over the existing `tailwind.config`)
```js
colors: {
  bg: '#071428', surface: '#0A1D3B', raised: '#102A52',
  accent: '#2BF5E3', 'accent-glow': '#6AA2FA', brand: '#3B82F6',
  mist: '#E8EFFA', muted: '#9FB3D1', midnight: '#0A1D3B',
},
fontFamily: { sans: ['Inter','system-ui','sans-serif'], display: ['Sora','Inter','sans-serif'], mono: ['JetBrains Mono','monospace'] },
```
Add Sora to the Google Fonts link: `family=Sora:wght@600;700`.

## Mapping for the developer
- `text-accent`, `bg-accent/10`, `border-accent` keep working (now cyan).
- Replace `text-yellow-400`, `text-purple-400`, `text-orange-*`, `text-green-*` on icons with `text-accent`; keep yellow only for star ratings if present.
- Replace hex/rgba `99,102,241` with `43,245,227`; `#818CF8` with `#6AA2FA`; `#6366F1`/`#4F46E5` gradient with `#2BF5E3`/`#3B82F6`.
- `.btn-primary` text must change from white to `#0A1D3B`.
- Add `og:image` from `brand/png/social-avatar-1080.png` until a 1200x630 share image exists.
