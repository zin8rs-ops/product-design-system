# Club Page — Foozi Product Spec

**Version:** 1.0  
**Status:** Design-Ready  
**URL Pattern:** `/team/{slug}`  
**Phase:** MVP Phase 2 — Teams & Players

---

## Purpose

The Club Page is a comprehensive club profile combining season overview, squad visualization, Tactra team intelligence and next match prediction. It is designed as the most visually distinctive club profile in German-language football media — mobile-first, data-driven, gaming-engaged.

---

## Design Principles (applied)

- **Club identity first** — accent color derived from club colors throughout
- **Squad Galaxy over grid** — players on pitch positions, not a boring table
- **Tactra as differentiator** — Team-Score and Team-DNA unique to Foozi
- **Season Pulse** — animated points curve replaces static result lists
- **Mobile-first** — max-width 480px, all layouts single-column on mobile
- **Token-driven** — no hardcoded colors, all via Foozi design tokens

---

## Page Structure

```
/team/{slug}
│
├── HERO (always visible)
├── TAB NAV
│   ├── Überblick
│   ├── Kader
│   ├── Tactra
│   └── Saison
```

---

## Hero

Always visible. Never scrolls away. Accent color = club primary color.

| Element | Description | Status |
|---|---|---|
| Club badge | Circle avatar with club short name, colored border | Designed |
| Club name | Large bold, letterSpacing -0.5px | Designed |
| League · Season | Small label above name | Designed |
| Position · Points · Goal diff | Meta strip below name | Designed |
| Tactra Team-Score Orb | Animated SVG ring, counts 0→score, club color | Designed |
| Form strip | Last 10 results as S/U/N chips, scrollable | Designed |
| Key Stats Bar | 4 animated counters: Siege · Tore · Ballbesitz % · Clean Sheets | Designed |
| Background number | Club position as large faded typographic element | Designed |
| Bottom border | 3px solid club accent color | Designed |

**Key Stats animate on page load** (count up from 0, 800ms, ease-out cubic).

---

## Tab: Überblick

Landing tab. Three modules stacked vertically.

### Next Match + Tactra Prognose
| Element | Description | Status |
|---|---|---|
| Opponent name | Large bold | Designed |
| Date · Time · Venue | Meta info | Designed |
| H/D/A cards | Three cards with % probabilities | Designed |
| Probability bar | Tri-color animated bar (red/amber/gray) | Designed |
| Tactra quote | AI-generated match note in italics | Designed |
| Card background | Gradient from club color light to white | Designed |

### Season Pulse
| Element | Description | Status |
|---|---|---|
| Cumulative points curve | SVG line chart, animates on load | Designed |
| Result dots | Green/amber/red dot per matchday | Designed |
| Current points label | Displayed at end of curve | Designed |
| Matchday axis | Spieltag 1 → Spieltag N | Designed |
| Legend | Sieg / Unentsch. / Niederlage color key | Designed |

### Marktwert Breakdown
| Element | Description | Status |
|---|---|---|
| Total squad value | Large number, club accent color | Designed |
| Position breakdown | Angriff · Mittelfeld · Abwehr · Tor | Designed |
| Animated bars | Per-position bars fill on load, show % | Designed |
| Value per position | Mio. € display per row | Designed |

---

## Tab: Kader

Squad Galaxy — the key innovation of the Club Page.

### Squad Galaxy
| Element | Description | Status |
|---|---|---|
| Pitch background | SVG pitch lines (penalty areas, center circle) | Designed |
| Player nodes | Positioned by formation slot | Designed |
| Node size | Proportional to market value | Designed |
| Ring color | Green ≥7.5 · Amber 6.5–7.5 · Red <6.5 (current form) | Designed |
| Jersey number | Displayed inside node | Designed |
| Player name | Short label below node | Designed |
| Float animation | Subtle continuous float per player, staggered | Designed |
| Tap interaction | Tap player → navigate to player profile | Planned |
| Formation switcher | Switch between 4-3-3 / 4-2-3-1 / 3-5-2 | Planned |
| Legend | Form ring color explanation | Designed |

**Node size formula:** `base(10px) + (playerMV / maxSquadMV) * 14px`

---

## Tab: Tactra

AI-powered team evaluation. Two sections.

### Team-Score Hero
| Element | Description | Status |
|---|---|---|
| Score Orb | Animated SVG ring, club color | Designed |
| Tier label | DOMINANT / STARK / SOLIDE / WANKEND | Designed |
| League rank note | "Top 3 der Bundesliga" | Designed |
| Background | Club color light gradient | Designed |

**Tier thresholds:** DOMINANT ≥85 · STARK 70–84 · SOLIDE 55–69 · WANKEND <55

### Team-DNA Cards (Sorare-Style)
| Element | Description | Status |
|---|---|---|
| 3×2 card grid | Aspect-ratio 3:4.2 cards | Designed |
| Flip interaction | Tap flips to solid color + description | Designed |
| Score ring | Animated SVG ring per card | Designed |
| Rank badge | Score value top-left | Designed |
| Shimmer lines | Top + bottom accent lines | Designed |

**Default Team-DNA attributes:**
- High Press · Ballbesitz · Direktspiel · Set Pieces · Gegenpressing · Konter

---

## Tab: Saison

Detailed season statistics and history.

### Stats Grid
| Element | Description | Status |
|---|---|---|
| 8-cell grid | 2-col layout, fade-up staggered animation | Designed |
| Cells | Tore · Gegentore · xG · xGA · Ballbesitz · Clean Sheets · Siege · Niederlagen | Designed |
| Highlight color | Club accent color on positive metrics | Designed |

### Season Pulse (repeated)
| Element | Description | Status |
|---|---|---|
| Full curve | Same as Überblick tab | Designed |

### Form Strip
| Element | Description | Status |
|---|---|---|
| Last 10 chips | S/U/N colored chips, full size | Designed |
| Scrollable | Horizontal scroll on mobile | Designed |

---

## Data Requirements

| Entity | Fields |
|---|---|
| Club | id, name, slug, shortName, league, season, position, points, goalDifference, accentColor |
| Season Stats | wins, draws, losses, scored, conceded, cleanSheets, possession, xG, xGA |
| Form | Last N results: result (S/U/N) |
| Next Match | opponent, date, time, venue, tactraH, tactraD, tactraA, tachtraNote |
| Squad | Per player: name, position, number, marketValue, currentFormRating |
| Market Value | total, breakdown per position group (label, value, percentage) |
| Season Timeline | Per matchday: result, goalsFor, goalsAgainst |
| Tactra | teamScore, tier, leagueRank, dna (label, score, icon, color, description) |

---

## Tech Notes

- **Framework:** React + TypeScript + Vite + Tailwind CSS
- **Animations:** motion.dev for pitch/pulse reveals, CSS keyframes for bars
- **Club theming:** accent color passed as prop to all Hero + Tactra components
- **Config-driven:** One config file per club — zero page rebuilds for new clubs
- **Error boundaries:** Per module — no white-screen crashes
- **Mobile-first:** max-width 480px base, scales up

---

## Innovation vs. Competitors

| Feature | Kicker | Transfermarkt | Bundesliga.de | Foozi |
|---|---|---|---|---|
| Squad on pitch | — | — | Basic | Squad Galaxy with MV + Form |
| Season curve | — | — | — | Animated points pulse |
| Team-DNA | — | — | — | Sorare-style flip cards |
| Next match AI | — | — | — | Tactra H/D/A + quote |
| MV by position | — | Gesamt only | — | Animated breakdown |

---

## Status Summary

| Tab | Modules | Designed | Planned | Open |
|---|---|---|---|---|
| Hero | 9 | 9 | 0 | 0 |
| Überblick | 3 | 3 | 0 | 0 |
| Kader | 1 | 1 | 2 | 0 |
| Tactra | 2 | 2 | 0 | 0 |
| Saison | 3 | 3 | 0 | 0 |
| **Total** | **18** | **18** | **2** | **0** |

---

## GSD Checklist

- [ ] Hero — Club badge, name, stats bar, form strip, Tactra orb
- [ ] Tab: Überblick — Next match prognose, Season pulse, MV breakdown
- [ ] Tab: Kader — Squad Galaxy with pitch layout
- [ ] Tab: Tactra — Team-score hero + Team-DNA cards
- [ ] Tab: Saison — Stats grid, pulse, form strip
- [ ] Routing — `/team/{slug}` wired
- [ ] Club theming — accent color prop system
- [ ] Mobile polish — touch targets, scroll behavior
- [ ] Link squad nodes → player profiles

---

## Related Files

- `product/features/player-page.md` — player page spec (companion page)
- `.product-design-system/platform-pages.md` — page type registry
- `.product-design-system/mvp-roadmap.md` — Phase 2 context
- `CLAUDE.md` — platform overview and design tokens

---

*Foozi · fussballdaten.de · Club Page Spec v1.0*
