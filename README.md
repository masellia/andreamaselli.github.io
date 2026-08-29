# Andrea Maselli Jekyll Website Prototype

A clean GitHub Pages / Jekyll rebuild of the Wix personal website.

## Local preview

```bash
bundle install
bundle exec jekyll serve
```

Then open `http://localhost:4000`.

## GitHub Pages deployment

1. Create a repository, e.g. `andreamaselli.github.io` or `personal-website`.
2. Upload these files.
3. In GitHub, enable Pages from the repository settings.
4. Replace placeholder links in `_config.yml`.
5. Add real images in `assets/img/`, especially `hero.jpg`.

## Main editable files

- `_config.yml`: site metadata and external profiles
- `_data/navigation.yml`: navigation menu
- `index.md`: homepage text
- `pages/*.md`: internal pages
- `assets/css/main.css`: visual design

## Maintenance conventions

- Treat the root-level `cv.pdf` as the authoritative source for talks, meetings, and publications. When updating those sections, extract the latest information from that file and update the corresponding structured website data.
- Preserve Andrea's manual typography, title and subtitle sizing, vertical-bar lengths, and spacing adjustments. Do not normalize or overwrite those visual choices unless explicitly requested.

## The QB Room

NFL analyses are collection documents stored by season under `_nfl/`. A new article automatically appears on the deployed archive at `/andreamaselli.github.io/me/qb-room/` and in the same-season previous/next navigation.

Use filenames such as `_nfl/2026/week-01-opponent.md` and this front matter:

```yaml
---
title: "Article headline"
description: "Short archive and search description."
date: 2026-09-13
game_date: 2026-09-13
season: 2026
week_label: "Week 1"
week_order: 1
phase: regular
opponent: Opponent Name
opponent_abbr: OPP
home_away: home
team_score: 27
opponent_score: 20
status: Final
thesis: "The main interpretation of the game in one sentence."
stats_game_label: Game
stats_season_label: Season
stats_note: Explanation and source for the statistics.
stats:
  - metric: Offensive EPA/play
    game: "+0.17"
    season: "+0.08"
---
```

Insert the statistics table where it belongs in the article with:

```liquid
{% include nfl-stats.html stats=page.stats %}
```

Store new article-specific images under `assets/img/nfl/<season>/<week>/` and render them with:

```liquid
{% include nfl-figure.html src="/assets/img/nfl/2026/week-01/example.jpg" alt="Meaningful description" caption="Caption" credit="Source" %}
```

Use the NFL season year for `season`, including for playoff games played in January of the following calendar year. Use `week_order` to place regular-season and postseason articles in the intended sequence. Set `date` to the publication date and avoid future dates, because Jekyll does not publish future-dated documents by default. Restart the local Jekyll server after changing collection configuration.
