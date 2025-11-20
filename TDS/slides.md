---
marp: true
theme: default
paginate: true
math: true
size: 16:9
style: |
  /* Project theme overrides: brand and readable code */
  section { font-family: 'Inter', 'Helvetica Neue', Arial, sans-serif; color: #0f172a; }
  h1, h2, h3 { color: #0b2545; }
  .brand { color: #42affa; font-weight: 700; }
  pre.code { background: #0b1220; color: #e6eef8; padding: 1rem; border-radius: 8px; }
  .bg-overlay { background: rgba(7,10,20,0.45); padding: 1.5rem; border-radius: 8px; display: inline-block; }
---

# Product Documentation — Analytics Engine

Contact: 24ds3000019@ds.study.iitm.ac.in

---

<!--
backgroundImage: https://images.unsplash.com/photo-1532619675605-3c2fa0a4b2d1?auto=format&fit=crop&w=1650&q=80
backgroundSize: cover
backgroundOpacity: 0.45
-->

# Architecture Overview

<div class="bg-overlay">
Core service: Real-time analytics & stream processing
</div>

<footer>Contact: 24ds3000019@ds.study.iitm.ac.in</footer>

---

## Custom Theme Notes

- Brand color: <span class="brand">#42affa</span>
- Typeface: Inter / system sans
- Code blocks styled for high contrast

This Markdown is maintainable in version control and can be exported to PDF/PPTX/HTML via Marp CLI.

---

## Algorithmic Complexity (Math)

We analyze the core aggregation algorithm. The recurrence for the merge step is:

$$T(n) = 2T(n/2) + \Theta(n)$$

By the Master theorem:

$$T(n) = \Theta(n\log n)$$

This helps with capacity planning.

---

## Example Code (Python)

```python
from collections import defaultdict

def aggregate_stream(batches):
    """Windowed aggregation over incoming batches"""
    result = defaultdict(int)
    for b in batches:
        for k, v in b.items():
            result[k] += v
    return result
```

---

## Export & Maintainability

- Keep this `slides.md` in the repo under `TDS/slides.md`.
- Use Marp CLI to export:

```bash
# install once
npm install -g @marp-team/marp-cli

# export PDF
marp TDS/slides.md --pdf

# export PPTX
marp TDS/slides.md -o slides.pptx
```

---

# Thank you

Contact: 24ds3000019@ds.study.iitm.ac.in
