---
jupytext:
  formats: ipynb,md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.14.5
    html_theme_options: {hide_sidebar: true}
    number_source_lines: true
kernelspec:
  display_name: Python 3 (ipykernel)
  language: python
  name: python3
---

+++ {"user_expressions": []}

# This is all directly from a live Jupyter nb

```{code-cell} ipython3

import pandas as pd

# load data
df = pd.read_csv("_static/example.csv")

print(df.head())
```



```{code-cell} ipython3
---
tags: [scroll-output,scroll_output]
pygments_style: sphinx
---

# Describe the columns one by one
for c in df.columns:
    print(df[c].describe())
```

```{code-cell} ipython3
---
tags: [hide-output]
---
## # Don't want to mess up the original data
df_copy = df.copy()

results = dict()
for c in df_copy.columns:
    if df_copy[c].dtype == "object":
        break
    elif df_copy[c].dtype in [
        "int64",
        "float64",
        "int32",
        "float32",
        "int16",
        "float16",
        "int8",
        "float8",
    ]:
        # take Xth percentile
        results[c] = [
            df_copy[c].quantile(0.25),
            df_copy[c].quantile(0.5),
            df_copy[c].quantile(0.75),
        ]

# Create a new dataframe
df_results = pd.DataFrame(results)

print(df_results)
print("\n")
print(type(df_results))
```

```{code-cell} ipython3
## keep scientific notation but cap at 2 decimal places
pd.options.display.float_format = "{:,.2f}".format
print(df_results.T)
```

## Using skimpy to automate a lot of this

```{code-cell} ipython3
---
tags: [hide-input]
---
from skimpy import skim

# suppress warnings
import warnings

warnings.filterwarnings("ignore")

skim(df)
```

## Pandas profiling


```{code-cell} ipython3
from pandas_profiling import ProfileReport

profile = ProfileReport(
    df, title="Pandas Profiling Report", html={"style": {"full_width": True}}
)
```

## Sidenotes and marginnotes

Here's a sentence[^sn1] with multiple [^sn2] sidenotes.

[^sn1]: Test sidenote 1.
[^sn2]: Test sidenote 2.

Here's a sentence[^mn1] with multiple marginnotes[^mn2].

[^mn1]: {-} Test marginnote 1.
[^mn2]: {-} Test marginnote 2.


Sidenotes inside of admonitions should behave the same:

:::{note}
An admonition with a sidenote defined in the admonition[^snam1] and another defined outside of the admonition [^snam2].

[^snam1]: Sidenote defined in the admonition.

:::

[^snam2]: Sidenote defined outside the admonition.


## Nested admonitions

These aren't theme-specific, but we still show below to make sure they work.

::::{note} Here's a note!
:::{tip} And a tip!
:::
::::

## MyST Markdown elements

Here are a few design elements to show off MyST Markdown.

### Table alignment

To ensure that markdown alignment is rendered properly.

| Default Header | Left Align | Right Align | Center Align |
| -------------- | :--------- | ----------: | :----------: |
| Cell 1 | Cell 2 | Cell 3 | Cell 4 |
| Cell 1 | Cell 2 | Cell 3 | Cell 4 |

### List table width

Testing list tables take width as expected.

```{list-table}
:width: 100%
* - a
  - b
* - c
  - d
```