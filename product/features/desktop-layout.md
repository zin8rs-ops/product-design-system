# Desktop Layout — Foozi Product Spec

**Version:** 0.1 — Placeholder
**Status:** Future Milestone — NOT in current sprint
**Phase:** Post-MVP — after mobile launch

---

## Status

> ⏳ Dieser Milestone wird erst gestartet nachdem Mobile Launch abgeschlossen ist.
> Claude Code soll diese Datei NICHT anfassen bis `/gsd:new-milestone desktop-layout` aufgerufen wird.

---

## Vision

"Modern-Neu" — kein Standard-Portal-Layout. Foozi Desktop soll sich von Kicker, Transfermarkt und Bundesliga.de visuell und strukturell abheben. Editorial, datenreich, gaming-engaged — aber auf großem Screen.

---

## Offene Entscheidungen (zu klären beim Milestone-Start)

- [ ] Primäres Layout-Muster — Two-Column / Magazine / Dashboard?
- [ ] Navigation — Sidebar oder Top Nav?
- [ ] Breakpoints — md (768px) · lg (1024px) · xl (1280px) · 2xl (1536px)
- [ ] Squad Galaxy auf Desktop — größere Pitch, Hover-States statt Tap
- [ ] Tactra Verdict — Side-Panel oder eigene Spalte?
- [ ] Player Page Desktop — Hero full-width mit Spielerbild?

---

## Bekannte Anforderungen

- Alle Mobile-Komponenten müssen responsive erweiterbar sein — keine Desktop-only Rewrites
- Tailwind Breakpoint-System — md: prefix durchgängig
- Squad Galaxy: Touch → Hover, Tap → Click
- Navigation: Mobile Bottom Nav → Desktop Top Nav oder Sidebar

---

## Inspirations-Richtung

- Modern-Neu — nicht klassisches Sport-Portal
- Datenreich ohne überladen zu wirken
- Tactra als visuelles Zentrum auf großen Screens
- Editorial-Qualität — denk NYT Sports meets FIFA Ultimate Team

---

## GSD Checklist (noch nicht aktiv)

- [ ] Desktop-Layout Konzept — Wireframes / Prototype
- [ ] Breakpoint-System definieren
- [ ] Navigation Desktop-Variante
- [ ] Player Page Desktop
- [ ] Club Page Desktop
- [ ] My Squad Desktop
- [ ] Competition Page Desktop
- [ ] Homepage Desktop

---

## Related Files

- product/features/player-page.md — Mobile spec
- product/features/club-page.md — Mobile spec
- product/features/my-squad.md — Mobile spec

---

> **Trigger:** Erst starten wenn Mobile Polish + My Squad Share + Auth abgeschlossen.
> **Command:** /gsd:new-milestone desktop-layout

---

*Foozi · fussballdaten.de · Desktop Layout Spec v0.1 — Placeholder*
