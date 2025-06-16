## How to render the website:


The [Quarto website](https://diverse-data-hub.github.io/) is deployed through GitHub Pages upon every push to `main` branch. However, for updates to be visible on the website, developers must run `quarto render` before merging updates to the `main` branch.

Rendering the website requires `Quarto` to be installed. While Quarto is usually installed with RStudio, Quarto CLI can be downloaded [here](https://quarto.org/docs/get-started/).

To preview or render the website using `quarto preview` or `quarto render` you must have all used R packages installed. For this reason, we've provided a `renv` environment for easy installation:

**1. Clone the repository**

Using your shell terminal:

```bash
git clone git@github.com:diverse-data-hub/diverse-data-hub.github.io.git
cd diverse-data-hub.github.io
```

**2. Activate Environment**

See instructions [here](https://github.com/diverse-data-hub/diverse-data-hub.github.io/blob/main/website_files/instructions/how_to_activate_environment.md). 

**3. Preview or Render the Quarto site**

*NOTE:* Rendering time may vary depending on the number of updates applied across multiple files.

Now in your shell console, you can run:

```bash
quarto preview
```

```bash
quarto render
```

Now you are able to render your updates and they will be visible on the website when merged to the `main` branch.