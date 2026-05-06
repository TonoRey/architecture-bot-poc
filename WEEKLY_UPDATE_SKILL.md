# Architecture Intelligence PoC — Weekly Update Skill

You are updating Antonio's Architecture Intelligence PoC learning path reference website AND pushing the changes to GitHub automatically. This is a weekly Sunday update task.

## Objective
Review the past week's Cowork sessions to identify what Antonio and his team built, learned, and unblocked in the Architecture Intelligence PoC project, update the HTML file locally, then push it to GitHub so it publishes automatically.

## Steps

### 1. Read the current site
Read the file at `/Users/reycas/Documents/CloudeCowork/ArchitectureBot/index.html` to understand the current state (which sprint we're on, what's already logged, current progress percentages).

### 2. Review recent sessions
Use the `list_sessions` and `read_transcript` tools to review sessions from the past 7 days. Look for any sessions related to:
- The Architecture Intelligence Chatbot PoC
- draw.io diagram parsing, NetworkX graph building
- Gemini API, LangChain, FAISS, sentence-transformers
- Code written, errors debugged, concepts explained
- Sprint progress: what was completed, what's blocked
- Questions asked about GCP, MuleSoft, Apigee, LLMs, RAG, embeddings

### 3. Update the HTML file
Update `/Users/reycas/Documents/CloudeCowork/ArchitectureBot/index.html` with:

**Progress bars**: Update percentages based on sprint activity this week.
- PoC Overall: (sprints completed / 4) * 100
- Each sprint bar: estimate based on tasks completed in session logs

**Sprint cards**: Update status classes:
- `active` (amber border) = currently in progress
- `done` (green border) = completed this week
- `locked` (red dim, opacity 0.5) = not started yet

**Weekly Log section**: Add a new `<div class="week-entry current">` for the current week at the TOP of the log section. Move previous "current" to completed (badge-done class).

Format for new week entry:
```html
<div class="week-entry current">
  <div class="week-header">
    <span class="week-title">Week N — [Date Range] · [Sprint Name]</span>
    <span class="week-badge badge-active">ACTIVE</span>
  </div>
  <ul class="week-items">
    <li>What was built this week (specific function/file/feature)</li>
    <li>Concept learned by doing (with brief explanation)</li>
    <li>Error encountered and how it was fixed</li>
    <li>What the LLM can now answer that it couldn't before</li>
    <li>Next: What we tackle next session</li>
  </ul>
</div>
```

**Code Snippets section**: Add any new functions built this week using:
```html
<div class="cmd-card">
  <div class="cmd-line">
    <span class="cmd-prompt">colab $</span>
    <span class="cmd-code">function_name(params) → return_type</span>
  </div>
  <div class="cmd-objective"><strong>Sprint N</strong> — What this function does</div>
  <div class="cmd-example"># Built: YYYY-MM-DD · Lines: ~N · Status: working</div>
</div>
```

Update snippet status from `# Status: pending` to `# Built: DATE · Status: working` when completed.

**Footer**: Update `last_updated` date to today.

### 4. Save and push to GitHub
Save the updated HTML to `/Users/reycas/Documents/CloudeCowork/ArchitectureBot/index.html`.

Then run this bash command to commit and push:
```bash
cd /sessions/[current-session]/mnt/CloudeCowork/ArchitectureBot
git config user.email "antonioreyesnava@gmail.com"
git config user.name "TonoRey"
git add index.html
git commit -m "Weekly PoC update - $(date '+%Y-%m-%d')"
git pull --rebase origin main
git push origin main
```

Note: The bash environment may not have network access to GitHub. If the push fails, the local file is still saved and Antonio's crontab will push it at 8:30 PM from his Mac.

## Style constraints
- Keep dark blue cyberpunk aesthetic (--bg: #080810, --blue-hi: #a8c8f0)
- All content in English
- Same HTML structure and CSS classes as established
- Do not remove existing content — only add/update
- Password to unlock the site: `archbot2025`

## Context about this project
- Project: Architecture Intelligence Chatbot PoC
- Stack: Google Colab + Gemini 1.5 Flash + NetworkX + FAISS + LangChain + sentence-transformers
- Cost target: ~$0 (free tiers only)
- Timeline: 4 sprints, May 5 – June 2, 2025
- Goal: Demo to Antonio's boss showing a chatbot that answers questions about a draw.io architecture diagram
- Team: Antonio (architect) + JR engineers (Python + REST API basics)
- Learning approach: Claude as pair programmer, learn by building

## Sprint reference
- Sprint 1 (Week 1): Parse draw.io XML → build NetworkX graph → visualize in Colab
- Sprint 2 (Week 2): Connect Gemini → LangChain tools → basic Q&A on architecture
- Sprint 3 (Week 3): FAISS + sentence-transformers → semantic search → impact analysis ("what breaks if I remove X?")
- Sprint 4 (Week 4): ipywidgets chat UI → conversation memory → demo script → boss presentation

## GitHub / Netlify info
- GitHub repo: https://github.com/TonoRey/architecture-bot-poc (create if not exists)
- Live site: to be configured on Netlify after first push
- User: Antonio Reyes Nava (antonioreyesnava@gmail.com)
- GitHub handle: TonoRey
- Timezone: CST (Mexico City)
