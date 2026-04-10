# PR Description: UI Navigation & Search Experience Enhancements

## 🚀 Overview
This Pull Request focuses on streamlining the log investigation workflow by introducing a "Show in Context" feature and a more reactive, forgiving search experience.

---

## ✨ Features

### 📍 Show in Context
A new "Show in context" action has been added to the log drawer and cell context menus. This allows users to jump from a filtered/searched view directly into the full, unfiltered log history, centering and highlighting the original line. This is critical for investigating the events immediately preceding or following an interesting log entry.

### ⚡ Live Reactive Search
The search bar has been transitioned to a fully reactive model:
- **Instant Filtering**: Results update immediately as you type.
- **Lower Threshold**: Filtering now starts from the first character.
- **Smart Fallback**: If a query is invalid according to Breser syntax, the system automatically falls back to a standard case-insensitive text search instead of blocking the UI.

---

## 💅 Styling
- Added a high-contrast `.highlighted` row style to clearly distinguish selected log lines during context navigation.
