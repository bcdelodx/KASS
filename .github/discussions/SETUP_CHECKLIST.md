# GitHub Discussions Setup Checklist

**Estimated time:** 30-45 minutes
**Status:** Ready to implement

---

## Phase 1: Enable Discussions (5 minutes)

### Step 1: Enable GitHub Discussions

- [ ] Go to https://github.com/bcdelodx/KASS
- [ ] Click **Settings** tab
- [ ] Scroll to **Features** section
- [ ] Check **✓ Discussions**
- [ ] Click **Set up discussions** button
- [ ] GitHub will create a default welcome post - you can delete this after setup

---

## Phase 2: Configure Categories (10 minutes)

### Step 2: Create Category Structure

Navigate to **Discussions** tab → Click **pencil icon** next to "Categories"

**Create these 7 categories in this order:**

| # | Category Name | Emoji | Description | Format |
|---|--------------|-------|-------------|---------|
| 1 | Methodological Questions | 📚 | Questions about causal inference methods and identification strategies | Q&A |
| 2 | Implementation Help | 💻 | Technical questions about running notebooks or code issues | Q&A |
| 3 | Show & Tell | 🔬 | Share analyses you've built using KASS methods | Announcement |
| 4 | Feature Requests & Ideas | 💡 | Suggestions for new notebooks, methods, or improvements | Discussion |
| 5 | Research & Policy Applications | 📖 | Applying causal inference to specific policy domains | Discussion |
| 6 | Announcements | 📢 | Official updates about new notebooks and features | Announcement |
| 7 | General Discussion | 🤝 | Broader conversations about policy analysis and research | Discussion |

**Format settings:**
- **Q&A format**: Allows marking best answer, useful for support
- **Discussion format**: Open-ended conversation
- **Announcement format**: Only maintainers can create posts; community can comment

**After creating categories:**
- [ ] Verify all 7 categories appear
- [ ] Check format types are correct
- [ ] Reorder if needed (drag to rearrange)

---

## Phase 3: Post Pinned Discussions (15 minutes)

### Step 3: Create and Pin Starter Threads

**For each pinned discussion:**

1. Click **New discussion** button
2. Select the appropriate category from dropdown
3. Copy content from the corresponding markdown file (see table below)
4. Paste content into discussion body
5. Add title from the markdown file
6. Click **Start discussion**
7. After posting, click **📌 Pin** button in top right corner

**Post these 4 pinned discussions:**

| Order | File | Category | Title |
|-------|------|----------|-------|
| 1 | `discussion_pin_01_welcome.md` | General Discussion | 👋 Welcome to KASS Discussions! Start Here |
| 2 | `discussion_pin_02_faq.md` | Methodological Questions | 📚 Common Causal Inference Questions – Start Here Before Posting |
| 3 | `discussion_pin_03_showcase.md` | Show & Tell | 🎯 Show & Tell: Share Your KASS-Powered Analyses |
| 4 | `discussion_pin_04_roadmap.md` | Feature Requests & Ideas | 🗺️ KASS Roadmap & How to Contribute |

**After pinning all 4:**
- [ ] Verify pins appear at top of their categories
- [ ] Check formatting renders correctly (links, code blocks, etc.)
- [ ] Test that links to notebooks work

---

## Phase 4: Create Discussion Templates (5 minutes)

### Step 4: Add Discussion Templates

**Option A: Pin template discussion (Recommended)**

1. Create new discussion in **General Discussion**
2. Title: "📝 Discussion Templates - Copy & Paste These"
3. Copy content from `discussion_templates.md`
4. Post and pin

**Option B: Add to README**
- Already linked in CONTRIBUTING.md
- Can also add section to main README

**Recommendation:** Do both for maximum visibility

- [ ] Templates pinned in General Discussion
- [ ] Templates referenced in documentation

---

## Phase 5: Seed Initial Activity (10-15 minutes)

### Step 5: Create Starter Discussions

**Goal:** Don't launch with empty forums. Create 3-5 quality starter threads.

**Seed Thread 1: Methodological Question**
- [ ] Category: Methodological Questions
- [ ] Title: "DID vs. Synthetic Control: When to use which?"
- [ ] Content: Post a thoughtful question and self-answer using FAQ content
- [ ] Purpose: Show what good methodological questions look like

**Seed Thread 2: Feature Request**
- [ ] Category: Feature Requests & Ideas
- [ ] Title: "Request: Matching methods notebook"
- [ ] Content: "Would love to see a notebook on propensity score matching and related methods. Use cases include..."
- [ ] Purpose: Demonstrate how to make good feature requests

**Seed Thread 3: Research Application**
- [ ] Category: Research & Policy Applications
- [ ] Title: "Best practices for evaluating workforce development programs?"
- [ ] Content: Post genuine question about evaluation frameworks
- [ ] Purpose: Start domain-specific conversations

**Optional Seed Thread 4: Show & Tell Example**
- [ ] Category: Show & Tell
- [ ] Title: Create example using your own work or synthetic case
- [ ] Content: Follow the template from pin #3
- [ ] Purpose: Show community what sharing looks like

**After seeding:**
- [ ] All seed threads posted
- [ ] Mix of questions, requests, and examples
- [ ] Demonstrates community culture and quality bar

---

## Phase 6: Launch Announcement (Varies)

### Step 6: Announce to Community

**Update repository:**
- [ ] Add "Discussions" section to README (see template below)
- [ ] Ensure badge in README links correctly
- [ ] Commit and push changes

**Social media:**
- [ ] Twitter/X post with link
- [ ] LinkedIn post
- [ ] Reddit: r/datascience
- [ ] Reddit: r/economics
- [ ] Reddit: r/publicpolicy

**Direct outreach:**
- [ ] Email existing KASS users (if list exists)
- [ ] Personal invitations to 5-10 known experts
- [ ] Share in relevant Slack communities

**Announcement template:**

```
🚀 Launched: KASS Community Discussions

We've opened GitHub Discussions for KASS—a space for rigorous
conversations about causal inference and policy analysis.

✅ Ask methodological questions
✅ Get implementation help
✅ Share your work
✅ Shape the roadmap

Join us: https://github.com/bcdelodx/KASS/discussions

#CausalInference #PolicyAnalysis #OpenScience #DataScience
```

---

## Phase 7: First Week Management

### Step 7: Establish Community Norms

**Daily actions (10-15 minutes/day):**

**Morning:**
- [ ] Check for new discussions
- [ ] Respond to questions (< 24 hour target)
- [ ] Thank participants
- [ ] Upvote good content

**Evening:**
- [ ] Check for unanswered questions
- [ ] Quick responses where needed
- [ ] Cross-post interesting discussions to social media

**End of Week 1:**
- [ ] Review metrics (participants, posts, response time)
- [ ] Update FAQ if recurring questions emerged
- [ ] Identify top contributors
- [ ] Plan Week 2 seeding if needed

---

## README Addition Template

Add this section to README.md after the "How to Use This" section:

```markdown
## Community & Discussions

Join the KASS community on [GitHub Discussions](../../discussions):

- **📚 [Methodological Questions](../../discussions/categories/methodological-questions)** – Get help with causal inference methods and identification strategies
- **💻 [Implementation Help](../../discussions/categories/implementation-help)** – Technical support for running notebooks
- **🔬 [Show & Tell](../../discussions/categories/show-tell)** – Share your KASS-powered analyses
- **💡 [Feature Requests](../../discussions/categories/feature-requests-ideas)** – Suggest new notebooks and improvements
- **🗺️ [Roadmap](../../discussions/categories/feature-requests-ideas)** – See what's coming and how to contribute

Before posting, check the [FAQ](../../discussions) and [discussion templates](../../discussions).
```

---

## Success Metrics

### Week 1 Targets
- [ ] 5+ unique participants (beyond maintainers)
- [ ] 10+ discussion posts
- [ ] Every question answered < 24 hours
- [ ] 1+ Show & Tell post
- [ ] 0 spam or off-topic content

### Month 1 Targets
- [ ] 20+ unique participants
- [ ] 50+ discussion posts
- [ ] Community members answering each other
- [ ] 3+ Show & Tell posts
- [ ] 1+ high-quality methodological debate

---

## Quick Reference: Files Location

All discussion materials are in `.github/discussions/`:

- `DISCUSSIONS_IMPLEMENTATION_GUIDE.md` – Detailed implementation guide
- `GITHUB_DISCUSSIONS_ARCHITECTURE.md` – Strategic architecture
- `discussion_pin_01_welcome.md` – Welcome & guidelines (pin #1)
- `discussion_pin_02_faq.md` – Methodological FAQ (pin #2)
- `discussion_pin_03_showcase.md` – Show & Tell guide (pin #3)
- `discussion_pin_04_roadmap.md` – Roadmap & contribution (pin #4)
- `discussion_templates.md` – Templates for community posts
- `SETUP_CHECKLIST.md` – This file

---

## Troubleshooting

**Problem: Can't find "Discussions" in Settings**
- Solution: May need admin access to repository
- Check you're logged into correct GitHub account

**Problem: Pin button not appearing**
- Solution: Must be repository admin/maintainer
- Check discussion was created in correct category

**Problem: Formatting looks wrong**
- Solution: Check markdown rendering in preview mode
- Ensure code blocks use triple backticks
- Verify links use correct relative paths

**Problem: Categories can't be reordered**
- Solution: Drag and drop should work
- Try refreshing page
- May need to delete and recreate if stuck

---

## Timeline Summary

| Phase | Task | Time | Status |
|-------|------|------|--------|
| 1 | Enable Discussions | 5 min | [ ] |
| 2 | Configure Categories | 10 min | [ ] |
| 3 | Pin Discussions | 15 min | [ ] |
| 4 | Discussion Templates | 5 min | [ ] |
| 5 | Seed Activity | 10-15 min | [ ] |
| 6 | Launch Announcement | Varies | [ ] |
| 7 | First Week Management | 15 min/day | [ ] |

**Total setup time:** ~45 minutes
**Ongoing time:** ~15 min/day Week 1, ~30 min/week ongoing

---

## Ready to Launch?

Once you've completed Phases 1-5:
1. Double-check all pins are live
2. Verify seed discussions are posted
3. Test that discussion templates are accessible
4. Announce on social media
5. Monitor closely for first 48 hours

**Let's build this community!** 🚀
