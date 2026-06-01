---
layout: single
title: "Coding Examples"
permalink: /coding/
author_profile: false
---

This page demonstrates code and mathematics examples from a Jupyter Notebook.

**Note:** Jekyll cannot directly ingest Jupyter Notebooks (unlike Jupyter Book). Instead, this page is a Markdown representation that displays the code, equations, and descriptions using Markdown code blocks and LaTeX math rendering.

## Imports

```python
import numpy as np
import matplotlib.pyplot as plt
```

## Mathematical Equations

We will plot the equation 

$$y = x^2$$ 

 LaTeX-style equations are not, by default, supported by MkDocs, but this barebones-setup includes mathjax capability via the `_includes/scripts.html` script.

## Plotting Example

```python
x = np.arange(0, 100)
y = x**2

plt.figure(figsize=(10, 6))
plt.plot(x, y)
plt.xlabel('x')
plt.ylabel('y')
plt.title('Plot of y = x²')
plt.grid(True)
plt.show()
```

This shows how you can present code examples, equations, and visualizations using Markdown and Jekyll.
