---
marp: true
theme: default
paginate: true
math: true
size: 16:9
style: |
  /* Custom theme: brand colors and readable code blocks */
  section {
    font-family: 'Inter', 'Helvetica Neue', Arial, sans-serif;
    color: #0f172a;
  }
  h1, h2, h3 { color: #0b2545; }
  .brand { color: #42affa; font-weight: 700; }
  footer { font-size: 0.75rem; color: #475569; }
  pre.code { background: #0b1220; color: #e6eef8; padding: 1rem; border-radius: 8px; }
  /* Small helper for background slides so text remains readable */
  .bg-overlay { background: rgba(7,10,20,0.45); padding: 1.5rem; border-radius: 8px; display: inline-block; }
---

# Product Documentation — Analytics Engine

24ds3000019@ds.study.iitm.ac.in

---

<!--
backgroundImage: url('https://images.unsplash.com/photo-1532619675605-3c2fa0a4b2d1?auto=format&fit=crop&w=1650&q=80')
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

You can maintain this Markdown in version control and export to PDF, PPTX, or HTML using Marp CLI.

---

## Algorithmic Complexity (Math)

We analyze the core aggregation algorithm. The worst-case time complexity for the merge step is:

$$T(n) = 2T(n/2) + \Theta(n)$$

By the Master theorem:

$$T(n) = \Theta(n\log n)$$

This guides capacity planning for input size and shard count.

---

## Example Code (Python)

```python
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

- Keep this `slides.md` in the repo at `slides.md`
- Use Marp CLI for exporting:

```bash
# Install marp-cli (once)
npm install -g @marp-team/marp-cli

# Export to PDF or PPTX
marp slides.md --pdf
marp slides.md -o slides.pptx
```

---

## Notes

- Custom CSS is included in the front-matter `style` block for quick, version-controlled tweaks.
- Page numbers are enabled with `paginate: true`.
- Math blocks use KaTeX via `math: true` and standard $$...$$ notation.

---

# Thank you

Contact: 24ds3000019@ds.study.iitm.ac.in
