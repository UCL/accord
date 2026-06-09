# How to Update the Roadmap Data

This guide explains how to edit the roadmap content — adding new pillars, updating recommendations, and marking progress — without needing any technical background.

---

## What is this file?

The file `roadmap-data.json` is what powers the roadmap page on the ACCoRD website. It contains all eight recommendation pillars, their recommendations, and their status. When you edit this file and push it to the `main` branch of the repository, the website updates automatically.

JSON is just a structured text format. It uses curly braces `{}` to group things together, square brackets `[]` for lists, and `"quotes"` around text. As long as you're careful to keep the structure intact, editing it is straightforward.

---

## Before you start

You'll need a GitHub account with access to this repository. If you don't have one yet:

1. Go to [github.com](https://github.com) and sign up for a free account.
2. The repository is public so anyone can make a pull request, but it will need to be reviewed and approved by one of the collaborators.

---

## How to edit the file on GitHub (no coding required)

1. Go to the repository on GitHub.
2. Navigate to `docs/assets/data/roadmap-data.json`.
3. Click the **pencil icon** (Edit this file) in the top-right corner of the file view.
4. Make your changes (see sections below for what to change and how).
5. When you're done, scroll to the bottom of the page.
6. Under **Commit changes**, write a short note describing what you changed (e.g. `"Add recommendation to Triage pillar"`).
7. Select **"Create a new branch for this commit and start a pull request"** — give the branch a short name (e.g. `update-triage`).
8. Click **Propose changes**.
9. On the next page, click **Create pull request**.
10. A collaborator will review and approve your changes. Once approved, they (or you) can click **Merge pull request** to publish them to the website.

> **Why this step?** The `main` branch is protected — changes cannot go live without a collaborator's approval. This prevents accidental edits from breaking the website.

---

## Understanding the structure

The file is a list of **recommendation pillars**. There are currently eight:

- Triage
- Templates
- Technical Audits and Compliance
- Advisory Service
- Policy
- Professional Development and Guidance
- Provisioning and Funding
- People – Community and Resourcing

Each pillar looks like this:

```json
{
  "id": "triage",
  "title": "Triage",
  "icon": "filter",
  "color": "#E8522A",
  "gradient": "linear-gradient(135deg, #E8522A 0%, #F07848 100%)",
  "summary": "A short summary shown on the roadmap overview.",
  "details": "A longer description shown when someone clicks into the pillar.",
  "status": "In Progress",
  "lead": "Lead person/team/organisation",
  "recommendations": [
    ...
  ]
}
```

Each pillar contains a list of **recommendations**, which look like this:

```json
{
  "label": "The recommendation title",
  "done": false,
  "subRecommendations": [
    "Sub-recommendation.",
    "Another bullet point."
  ],
  "rawData": [
    "A raw evidence or data point.",
    "Another data point."
  ]
}
```

The hierarchy is: **Pillar to Recommendations to Raw Data Points**.

---

## Common tasks

### Mark a recommendation as complete

Find the recommendation and change `"done": false` to `"done": true`.

```json
"done": true
```

### Update the pillar status

Find the pillar and change the `"status"` value. The options used in this project are:

- `"Planning"`
- `"In Progress"`
- `"Complete"`

```json
"status": "Complete"
```

### Update the summary or details text

Find the pillar and replace the text inside the quotes for `"summary"` or `"details"`:

```json
"summary": "Your updated summary text here.",
"details": "Your updated longer description here."
```

### Add a new sub-recommendation to a recommendation

Find the `"subRecommendations"` list for that recommendation and add a new line inside the square brackets. Each point must be in quotes and separated by a comma:

```json
"subRecommendations": [
  "Existing point.",
  "Another existing point.",
  "Your new point goes here."
]
```

> Make sure there is a comma after every point **except the last one**.

### Add a new raw data point

Same as above, but for the `"rawData"` list:

```json
"rawData": [
  "Existing data point.",
  "Your new data point."
]
```

### Add a new recommendation to a pillar

Find the `"recommendations"` list for the pillar you want to update. Add a new recommendation block inside the square brackets, separated by a comma from the previous one:

```json
"recommendations": [
  {
    "label": "Existing recommendation",
    "done": false,
    "subRecommendations": [],
    "rawData": []
  },
  {
    "label": "Your new recommendation title",
    "done": false,
    "subRecommendations": [
      "First summary point.",
      "Second summary point."
    ],
    "rawData": [
      "First data point.",
      "Second data point."
    ]
  }
]
```

### Add a brand new pillar

Copy an existing pillar block (everything from `{` to the matching `}`) and paste it at the end of the list, just before the final `]`. Make sure there is a comma after the previous pillar's closing `}`.

Then update all the fields:

| Field | What to put |
|---|---|
| `id` | A short unique identifier with hyphens, no spaces (e.g. `"data-sharing"`) |
| `title` | The display name shown on the tile and panel (e.g. `"Data Sharing"`) |
| `icon` | Leave as-is or ask a developer to update — this controls the icon on the tile |
| `color` | A hex colour code for the tile (e.g. `"#4A90D9"`) |
| `gradient` | Leave as-is or ask a developer to update |
| `summary` | One sentence shown on the roadmap overview |
| `details` | Longer description shown when a user opens the pillar panel |
| `status` | `"Planning"`, `"In Progress"`, or `"Complete"` |
| `lead` | The person, team, or organisation leading this pillar |
| `recommendations` | Start with an empty list `[]` and add recommendations as needed (see above) |

---

## Avoiding common mistakes

JSON is strict about formatting. Here are the most common errors and how to avoid them:

**Missing comma between items**
Every item in a list needs a comma after it — except the very last one.

```json
"subRecommendations": [
  "First point.",   ← comma here because it's not last
  "Second point."   ← no comma here because it's last
]
```

**Extra comma after the last item**
A trailing comma will break things. Make sure the last item in any list has no comma after it.

**Unmatched quotes or brackets**
Every opening `"`, `[`, or `{` needs a matching closing one. If something looks wrong, count your brackets.

**Tip:** GitHub's editor will highlight errors in red. If you see red, something is wrong with the structure. You can also paste the whole file into [jsonlint.com](https://jsonlint.com) to check for errors before committing.

---

## Getting help

If you're unsure about anything, don't worry, you can't accidentally break the live website. Because your changes go through a pull request on a separate branch, nothing goes live until a collaborator reviews and approves it. If something looks wrong, you can simply close the pull request without merging. Feel free to reach out to the ACCoRD team if you'd like a hand.
