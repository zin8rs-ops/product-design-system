# Foozi – Competition Page UX Specification

Version: 1.0  
Status: Draft  
Owner: Product / UX  

---

# Objective

Competition pages are the **core hub for league exploration**.

Users come here to:

1. See current standings
2. Check upcoming matches
3. Explore teams and statistics
4. Discover insights and trends

Competition pages should feel like a **data-rich football dashboard**, not a static table page.

---

# Page Structure

Order of sections:

1. Competition Hero
2. Standings
3. Upcoming Matches
4. Top Players
5. AI Competition Insights
6. Trending Teams
7. Competition Statistics
8. Related Media

---

# 1 Competition Hero

Purpose:

Immediately communicate the competition context.

Content:

- competition name
- season
- league logo
- navigation tabs

Tabs:

Overview  
Matches  
Standings  
Teams  
Stats  

Example:

Bundesliga – Season 2025/26

Navigation tabs allow fast switching between views.

---

# 2 Standings (League Table)

Purpose:

Most important data for competition pages.

Content:

- position
- team
- matches played
- goal difference
- points

Displayed Teams:

Top 10 visible by default.

Full table expandable.

UX Rule:

Avoid overwhelming the page with a full table immediately.

---

# 3 Upcoming Matches

Purpose:

Allow users to quickly see the next games.

Content:

Match cards including:

- home team
- away team
- time
- matchday
- tactra prediction score

Example:

Bayern vs Dortmund  
Saturday 18:30

UX Rule:

Display **5–8 matches only**.

CTA:

View Full Match Schedule

---

# 4 Top Players

Purpose:

Highlight key performers.

Possible leaderboards:

Top Scorers  
Most Assists  
Highest Rated Players

Each row includes:

- player
- team
- stat value

Example:

Harry Kane — 21 goals  
Florian Wirtz — 14 assists

CTA:

View Full Rankings

---

# 5 AI Competition Insights

Purpose:

Surface interesting patterns from data.

Example insights:

Bayern have the highest xG in the league.

Dortmund scored in 9 consecutive matches.

Leverkusen has the best defensive record.

UX Rule:

Maximum **3–4 insights**.

---

# 6 Trending Teams

Purpose:

Encourage exploration.

Display:

Teams with high engagement based on:

- match interest
- recent performance
- user predictions

Example:

🔥 Bayern  
🔥 Dortmund  
🔥 Stuttgart

Each links to team pages.

---

# 7 Competition Statistics

Purpose:

Show key league metrics.

Examples:

Average goals per match  
Clean sheet percentage  
Home vs away win rate

Visualization options:

- stat cards
- mini charts

---

# 8 Related Media

Purpose:

Provide content related to the competition.

Examples:

Highlights  
News  
Analysis

Cards link to:

/highlights  
/news

---

# UX Design Principles

Competition pages should follow these rules:

Clarity  
Standings must be immediately visible.

Hierarchy  
League table first, insights second.

Scanability  
Data should be easy to scan quickly.

Exploration  
Encourage users to navigate to teams, players and matches.

---

# Anti-Patterns

Avoid:

- overly dense statistical tables
- hidden standings
- long match lists above the fold

---

# Success Metrics

Competition page performance is measured via:

- match page CTR
- team page navigation
- scroll depth
- return visits
