---
file_format: mystnb
kernelspec:
  name: python3
otherkey1: val1
otherkey2: val2

---

# Data load

::::{grid}
:gutter: 3

:::{grid-item-card} One!
Here's the first card.
:::

:::{grid-item-card} Two!
Here's the second card.
:::

:::{grid-item-card} Three!
Here's the third card.
:::
::::



```{code-block} python
def print(text):
    sys.stdout.write(text)
```


The original development of MLCC was in the cloud so the code was developed using this route but it's actually more efficient to run the code locally. This is because the cloud is not optimised for data science and the code is not optimised for the cloud. The code is optimised for local machines and the cloud is optimised for web services. The code is also optimised for the local machine because it's easier to debug and it's easier to run the code locally. The code is also optimised for the local machine because it's easier to debug and it's easier to run the code locally. 

```{code-cell} ipython3
import sys
sys.path.append("../")

print("Hello world")
```

