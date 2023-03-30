# Markdown Files

Whether you write your book's content in Jupyter Notebooks (`.ipynb`) or
in regular markdown files (`.md`), you'll write in the same flavor of markdown
called **MyST Markdown**.
This is a simple file to help you get started and show off some syntax.

## Admonitions

Admonitions (also known as callouts) highlight a particular block of text,
that exists slightly apart from the narrative of your page, such as a note or a warning.


:::{tip}
Let's give readers a helpful hint!
:::



## Admonition types

The following core admonition types are available:

::::{tab-set}

:::{tab-item} Label1
```{attention} 
Content 1
```   

:::

:::{tab-item} Label2
```{caution} 
Content 2
```

:::

:::{tab-item} Label3
```{danger} 
Content 3
```

:::

:::{tab-item} Label4
```{error} 
Content 4
```

:::


::::




These admonitions take no argument, but may be specified with options:

:class: A space-separated list of CSS classes to add to the admonition.
:name: A reference target for the admonition (see 



:::{tip}
:class: myclass1,myclass2
:name: a-tip-reference
Let's give readers a helpful hint!
:::





Sphinx also adds a number of additional admonition types, for denoting changes to the documentation, or to the codebase:



:::{versionadded} 1.2.3
Explanation of the new feature.
:::

:::{versionchanged} 1.2.3
Explanation of the change.
:::

:::{deprecated} 1.2.3
Explanation of the deprecation.
:::



## Admonition titles

To provide a custom title for an admonition, use the `admonition` directive.
If you also want to style the admonition as one of the core admonition types,
you can use the `admonition` directive with the `class` option.



:::{admonition} My custom title with *Markdown*!
:class: tip

This is a custom title for a tip admonition.
:::



## Collapsible admonitions

The [sphinx-togglebutton](https://sphinx-togglebutton.readthedocs.io) extension allows you to create collapsible admonitions, by adding a `dropdown` class to the admonition.



:::{note}
:class: dropdown

This admonition has been collapsed,
meaning you can add longer form content here,
without it taking up too much space on the page.
:::



## Other Containers (grids, tabs, cards, etc.)

Using the extension,
content block can be wrapped in containers with a custom CSS class.

`````{note}
\:\:\:bg-primary
This is a container with a custom CSS class.

- It can contain multiple blocks
\:\:\:

`````

Using the [sphinx-design](https://github.com/executablebooks/sphinx-design) extension,
it is also possible to create beautiful, screen-size responsive web-components.


:::{card} Card Title
Header
^^^
Card content
+++
Footer
:::





::::{tab-set}

:::{tab-item} Label1
Content 1
:::

:::{tab-item} Label2
Content 2
:::

::::

## What is MyST?

MyST stands for "Markedly Structured Text". It
is a slight variation on a flavor of markdown called "CommonMark" markdown,
with small syntax extensions to allow you to write **roles** and **directives**
in the Sphinx ecosystem.

For more about MyST, see [the MyST Markdown Overview](https://jupyterbook.org/content/myst.html).

## Sample Roles and Directives

Roles and directives are two of the most powerful tools in Jupyter Book. They
are kind of like functions, but written in a markup language. They both
serve a similar purpose, but **roles are written in one line**, whereas
**directives span many lines**. They both accept different kinds of inputs,
and what they do with those inputs depends on the specific role or directive
that is being called.

Here is a "note" directive:

```{note}
Here is a note
```

It will be rendered in a special box when you build your book.

Here is an inline directive to refer to a document: {doc}`markdown-notebooks`.

## Learn more

This is just a simple starter to get you started.
You can learn a lot more at [jupyterbook.org](https://jupyterbook.org).
