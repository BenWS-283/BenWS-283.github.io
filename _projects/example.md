---
title: "Cantilever Beam Deflection Analysis"
excerpt: "Hand calculations and FEA comparison for an aluminum cantilever."
header:
  teaser: /assets/images/beam-teaser.jpg
  overlay_image: /assets/images/beam-header.jpg
  overlay_filter: 0.4
date: 2026-10-12
---

## Overview
A short paragraph on the problem, your role, and the tools used.

## Design Requirements
| Parameter | Value |
|-----------|-------|
| Material | 6061-T6 Aluminum |
| Length | 500 mm |
| Load | 200 N at free end |
| Max deflection | 2 mm |

## Analysis
![Beam FEA result]({{ site.baseurl }}/assets/images/beam-fea.png)
*Von Mises stress from the FEA simulation.*

```python
E = 68.9e9      # Pa
I = 8.33e-9     # m^4
delta = (200 * 0.5**3) / (3 * E * I)
print(f"Deflection: {delta*1000:.2f} mm")
```

## Results
Summarize what you found and how it compared to your requirements.

## Files
- [Full report (PDF)]({{ site.baseurl }}/assets/files/beam-report.pdf)
- [CAD drawing (PDF)]({{ site.baseurl }}/assets/files/beam-drawing.pdf)