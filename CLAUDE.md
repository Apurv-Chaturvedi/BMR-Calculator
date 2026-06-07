# CLAUDE.md

## Project overview
- BMR (Basal Metabolic Rate) calculator using the Mifflin-St Jeor equation
- Also computes TDEE (Total Daily Energy Expenditure) and calorie targets by goal
- Pure HTML/CSS/JS — no build step, no dependencies, no framework
- Single file: `index.html` (the only file that matters)
- `bmr_calculator_with_toggles.html` is a legacy duplicate — ignore it

## How to run
- Open `index.html` directly in a browser — no server needed
- To preview locally: `open index.html` or drag into browser

## Deploy process
- Hosted on GitHub Pages: https://apurv-chaturvedi.github.io/BMR-Calculator/
- Push to `main` branch → auto-deploys (legacy Pages build, no Actions needed)
- Remote: https://github.com/Apurv-Chaturvedi/BMR-Calculator
- Auth: push via HTTPS using a GitHub Personal Access Token (repo scope)
  - Token goes in remote URL: `https://<token>@github.com/Apurv-Chaturvedi/BMR-Calculator.git`

## Gotchas
- `toggleWeightUnit()` in the old code recreated the input via `innerHTML`, wiping the entered value — avoid that pattern
- No `NaN` guard in original code; always validate inputs before computing
- Homebrew is not installed on this machine; `gh` CLI was not available — use curl + GitHub API or token-in-URL for pushes
- The `!` prefix in Claude Code chat runs shell commands in the session

## Code style / preferences
- Inline everything in `index.html` — `<style>` and `<script>` tags, no external files
- No frameworks, no CDN imports — keep it dependency-free
- Use CSS custom properties or utility classes sparingly; flat CSS is fine here
- Validate all user inputs; show inline error messages (red border + message below field)
- Round BMR/TDEE results to whole numbers with `.toLocaleString()` for display
