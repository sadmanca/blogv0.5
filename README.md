# Sadman's Blog

My personal website and blog built with [Quarto](https://quarto.org) and deployed with [Cloudflare](https://pages.cloudflare.com/). You can find it at [sadman.ca](https://www.sadman.ca).

## Reporting Issues

Please report issues or edits on the site by opening a "Bug Issue" in the `sadmanca/blog` repository: [New Issue](https://github.com/sadmanca/blog/issues/new/choose)

## Contributing

This section discusses how to contribute to the documentation by rendering a document locally.

### Quarto-web uses a frozen state of computation

This Quarto project uses `freeze: true`, meaning it will never run computation engines during a project render. No Knitr or Jupyter configuration is needed to build the whole website. The `_freeze` folder is tracked on the git repo for this purpose. (See about [freeze](https://quarto.org/docs/projects/code-execution.html#freeze) for a reminder of how this works).

What is the impact if you modify (or add) a document: 

- If you modify a document that doesn't use any computation (i.e default `engine: markdown` is used), committing only the changes in the document is enough.
- If you modify a document that uses `engine: knitr` or `engine: jupyter`, you need to render the document locally and commit the changes in the `_freeze` folder as well. See [incremental render](https://quarto.org/docs/projects/code-execution.html#incremental-render).

### Rendering the whole website

To render the whole website locally, you can use the following command:

```bash
# Update freeze state if needed
quarto render /docs/path/to/modified-or-added-document.qmd
# Render the whole website using freeze state for all the other docs
quarto render
```

## Licenses

- Figures are licensed under Creative Commons [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0).
- Code is licensed under [MIT License](https://github.com/sadmanca/blog/blob/main/LICENSE).