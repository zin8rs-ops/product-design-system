# Foozi – Content Prioritization System

Version: 1.0
Status: Core System Logic
Owner: Product / UX / Data

---

# Objective

Define how Foozi dynamically prioritizes and displays content on:

* Homepage
* Match Pages

The system ensures:

* Maximum relevance
* Fast decision-making
* Clear hierarchy

---

# Core Principle

Content is NOT static.

Content is ranked by **decision relevance**.

---

# Content Categories

Every content item must belong to one category:

1. Decision Data
2. Explanatory Data
3. Engagement Data

---

# Ranking Inputs

Each match / content item receives a dynamic score based on:

1. Match Importance
2. Prediction Confidence (Tactra Edge)
3. Model vs Market Delta
4. User Interest Signals
5. Time Relevance
6. Volatility / Risk Level

---

# 1. Match Importance

Measures how relevant a match is globally.

Inputs:

* League priority
* Team popularity
* Competition stage

Score: 0–100

---

# 2. Prediction Confidence

Strength of model prediction.

Example:

Edge difference between teams.

Score: 0–100

---

# 3. Confidence Delta

Difference between model prediction and market odds.

Example:

Model: 48%
Market: 39%
Delta: +9%

Score increases with higher delta.

---

# 4. User Interest Signals

Measures real user behavior.

Inputs:

* Clicks
* Predictions made
* Page views

---

# 5. Time Relevance

Matches closer to kickoff are prioritized.

Example:

* <2h → very high
* 2–6h → high
* 6–24h → medium

---

# 6. Risk Level

Measures predictability.

* Low Risk → stable
* High Risk → volatile

High risk increases curiosity, but lowers confidence.

---

# Final Ranking Score

Each match receives a combined score:

Ranking Score =

(Importance * 0.25)

* (Confidence * 0.20)
* (Delta * 0.20)
* (User Interest * 0.15)
* (Time Relevance * 0.10)
* (Risk Factor * 0.10)

---

# Homepage Prioritization

## Goal

Show the most relevant matches TODAY.

## Rules

* Top 5–8 matches only
* Sorted by Ranking Score
* At least:

  * 1 high delta match
  * 1 high confidence match
  * 1 high interest match

---

# Match Card Priority

Each card shows:

1. Tactra Edge
2. Win Probability
3. Delta Indicator
4. Risk Level (optional)

---

# Match Page Prioritization

## Goal

Guide user to decision quickly.

## Order:

1. Prediction (Edge + Probability)
2. Key Drivers
3. Delta vs Market
4. Risk Level
5. Supporting Stats

---

# Dynamic Content Rules

## Rule 1

If Delta > threshold:

→ Highlight as "Value Pick"

## Rule 2

If Confidence > threshold:

→ Highlight as "Strong Pick"

## Rule 3

If Risk > threshold:

→ Show warning: "High Variance Match"

---

# UI Priority Layers

Layer 1 → Decision

* Prediction
* Edge
* Delta

Layer 2 → Explanation

* Key Drivers
* Form
* Trends

Layer 3 → Deep Data

* Stats
* Head-to-head

---

# Anti-Rules

Do NOT:

* Show unranked match lists
* Display data without context
* Prioritize based on chronology only

---

# Future Extensions

* Personalized ranking per user
* Favorite teams boosting score
* Learning from user predictions

---

# Success Metrics

* CTR on match cards
* Prediction participation rate
* Time to first interaction
* Scroll depth

---
