# Project: Static Conference Site

## Build Commands

```bash
npm run build      # Build Tailwind CSS: src/input.css → docs/output.css
npm run watch      # Watch mode for development
```

**Important**: Always run `npm run build` after modifying `src/` files.

## Directory Structure

```
docs/              # Static site root (committed)
  ├── index.html   # Main page (plain HTML + inline CSS)
  ├── campus_map.png
  ├── access.png
  └── kdk_abstract_template.docx
```

**Key**: No build process needed. Direct HTML editing with inline CSS.

## Git Ignore Rules

Never commit: `node_modules`, `package-lock.json`, `src/`, `tailwind.config.js`, `.opencode/`, `output.css`, `fonts/`

## Design Conventions

- **Typography**: System fonts (sans-serif for body, serif for headings)
- **Responsive**: Font size larger on desktop (768px+), default on mobile
- **No external deps**: Pure HTML/CSS/JS, self-contained

## HTML Conventions

- Use `eventListener` instead of inline `onclick`
- Include skip link for accessibility
- Tab panels need `role="tablist"`, `role="tab"`, `role="tabpanel"`, `aria-selected`, `aria-controls`
- All images need `alt` attributes

---

# Annual Conference Site Setup Workflow

## Overview

Create/update conference website in 3 phases as materials arrive.

## Phase 1: Initial Setup (Conference Overview)

**Input**: Word document containing:
- Conference name and number (e.g., 第38回)
- Dates (会期)
- Venue (会場)
- Committee chair (大会実行委員長)
- Registration method and fees (申込方法・参加費)
- Application deadline (申込締切)
- Bank account info (振込先)

**Actions**:
1. Update hero section with conference number and name
2. Update `#overview` section: dates, venue, committee chair
3. Update `#registration` section:
   - Application deadline (申込締切)
   - Fee table (参加費)
   - Bank transfer info (振込先)
   - Registration form link (申込みフォーム)
4. Update `#schedule` section with draft schedule
5. Leave `#program` sections as "工事中" (Under Construction)
6. Update footer year

## Phase 2: Public Symposium Program

**Input**: Word document containing public symposium program

**Actions**:
1. In `#program` section, replace "市民公開シンポジウム" card "工事中" with actual program
2. Format program content using consistent styling
3. Ensure proper accessibility and semantic HTML

## Phase 3: General Presentations Program

**Input**: Excel file containing:
- Oral presentations (口頭発表)
- Poster presentations (ポスター発表)
- Organized by day (1日目, 2日目)

**Actions**:
1. Extract data from Excel
2. Update `#program` section "一般講演" tabs:
   - Tab 1: 口頭発表 1日目
   - Tab 2: 口頭発表 2日目
   - Tab 3: ポスター発表
3. Replace each tab's "工事中" with actual presentation list
4. Format presentation info with consistent styling:
   - Time slot
   - Presentation title
   - Presenter name
   - Affiliation

## Template Reference

Use current `docs/index.html` as base template. Key sections:

- **Hero**: Conference number (金色文字), title, dates, venue badge
- **Navigation**: Links to all sections, mobile-responsive
- **Overview**: 3-column grid for dates/venue/chair
- **Schedule**: Daily schedule boxes with time slots
- **Program**: Tabs for different presentation types
- **Registration**: Fee table, bank info, application form button
- **Presentation**: Instructions for oral/poster presentations
- **Access**: Location info, maps, accordion-style notices
- **Footer**: Contact info, copyright

## Common Updates

When updating yearly:

1. **Conference Number**: Update hero section (金色文字) and page title
2. **Dates**: Throughout the page
3. **Venue**: Contact section
4. **Fee Table**: Check for price changes
5. **Bank Info**: Verify account details
6. **Links**: Registration form, abstract template
7. **Copyright Year**: Update footer
8. **Images**: Update campus_map.png and access.png if needed
