# X Writing Skill

Transform your notes into engaging X (Twitter) content using AI-powered content analysis and drafting.

## Features

- **Analyze your notes** to identify the most shareable insights
- **Draft authentic posts** that match your voice and drive engagement
- **macOS Notes integration** to automatically fetch ideas from your Notes app
- **Follow proven patterns** from x-strategy.md and style-guide.md
- **Avoid AI patterns** using anti-patterns.md to sound human, not AI-generated

## Setup

### 1. Configure macOS Notes (Optional)

If you want to fetch ideas from your macOS Notes app:

1. Copy the environment example file:
   ```bash
   cp .env.example .env.local
   ```

2. Edit `.env.local` and configure your preferences:
   ```bash
   export NOTES_SOURCE="Tweets"
   export CASING_STYLE="lowercase"
   ```

   - `NOTES_SOURCE`: Name of your Notes app note containing X post ideas
   - `CASING_STYLE`:
     - `"lowercase"` - Prefer lowercase (default). Capitalizes personal names and WordPress only
     - `"standard"` - Use standard capitalization rules

### 2. Using the Skill

#### From pasted content:

```bash
claude "Transform these notes into X posts: [paste your notes]"
```

#### From macOS Notes:

```bash
claude "Look in my Notes for good tweet ideas"
```

This will automatically fetch content from your configured Notes app note and analyze it.

#### List available notes:

```bash
./scripts/fetch-notes.sh list
```

#### Fetch from a specific note:

```bash
./scripts/fetch-notes.sh get "Note Name"
```

## How It Works

The skill follows a three-phase process:

### Phase 1: Analysis
1. Loads reference guides (x-strategy.md, style-guide.md, anti-patterns.md)
2. Fetches or reads your source notes
3. Applies content selection criteria to identify high-value insights
4. Evaluates what's worth sharing vs. what to skip

### Phase 2: Drafting
1. Selects the best angle from your notes
2. Chooses appropriate format (single tweet vs. thread)
3. Applies voice and style guidelines
4. Optimizes for natural engagement
5. Avoids AI writing patterns

### Phase 3: Output
1. Presents ready-to-post content with character counts
2. Shows which pattern was used (e.g., "Shipped X, learned Y")
3. Explains what was prioritized and why
4. Offers alternative angles if appropriate
5. Saves approved posts to `.social/X.md`

## Content Principles

The skill follows these core principles from your reference guides:

**Value First**
- Fresh insights from real experience
- Immediately actionable content
- Natural engagement triggers

**Specificity Builds Credibility**
- Name tools, projects, numbers
- Concrete examples over vague claims
- Show your work and process

**Authentic Voice**
- Direct, zero fluff
- Confident without hedging
- Personal but focused on work
- Avoid banned AI phrases
- Lowercase preference (configurable via CASING_STYLE)
  - Always capitalize: personal names, WordPress, product names
  - Lowercase everything else (including sentence starts)

## Reference Files

- **`references/x-strategy.md`** - What to post, content selection, engagement patterns
- **`references/style-guide.md`** - How to write, voice, tone, structure
- **`references/anti-patterns.md`** - AI writing patterns to avoid

## Examples

**User:** "Look in my notes for good tweet ideas"

**Skill:**
1. Fetches content from your "Tweets" note
2. Analyzes all ideas against x-strategy.md criteria
3. Identifies 3-5 high-value insights
4. Drafts posts using appropriate patterns
5. Presents options with character counts and explanations

**User:** "Make this more specific and add a question"

**Skill:**
1. Adds concrete details (tools, numbers, projects)
2. Includes specific engagement question
3. Shows updated version with changes highlighted

## Tips for Best Results

1. **Provide context**: "Notes from building X feature" vs just pasting notes
2. **Be specific**: "Focus on the learning about context matching"
3. **Request variations**: "Show me a few angles" gives options
4. **Iterate**: "Make it more specific" or "Add a question ending"
5. **Work incrementally**: Process one idea at a time for better results

## Troubleshooting

**Script permission denied:**
```bash
chmod +x scripts/fetch-notes.sh
```

**Can't find note in Notes app:**
- Check the exact note name (case-sensitive)
- Verify the note is in the default "Notes" account (iCloud or On My Mac)
- Try listing all notes: `./scripts/fetch-notes.sh list`

**HTML formatting in output:**
The script strips HTML tags from Notes app content automatically.
