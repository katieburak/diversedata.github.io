## How to add a new notebook:

These steps assume you already have a completed working **.qmd notebook file** that you want to publish to the website.

 **Strong recommendation**: Use equivalent "hcmst" or "marchmadness" files for reference.

**1 - Fill Out the Data Set Card**

*File*: `website_files/grid_items/<datasetfile>.qmd` 

*Fields to Complete:*

- `data-featured` - `true` or `false` (should be `false` by default - K. Burak approves featured status)
- `data-tags` - `python` or `r` (programming language used)
- `img src` - Path to image to display in card
- `<h3>` - dataset title
- Data set description
- `href` - link to full notebook (e.g., `https://diverse-data-hub.github.io/website_files/description_pages/<datasetname>.html`)

**2 - Add the Data Set Description Page:**

*File*: `website_files/description_pages/<datasetfile>.qmd`

*What to include:*

- Page title (`title:`)
- `About the Data` section
- Download button (`href`) path
- Complete metadata table (`field-value`)
- Variable table (respect header structures)
- Ensure correct paths to notebooks
- Attribution

**3 - Add the Notebook File:**

*File*: `website_files/notebooks/<datasetfile>.qmd`

*Structure:*

- Follow the template format.
- Should include: `Key Features on Dataset`, `Purpose and Use Cases`, `Case Study` (Objective, Methodology) 

**4 - Feature the Dataset (Optional).**

*File*: `website_files/grid_items/<file>.qmd`

*Action:*

If approved to be featured, update:

```yaml
class="grid-item" data-featured="true" data-tags="r"
```

**5 - Create a Reproducible Featured Image**

*File*: `website_files/img/<image>.png`

*Action:*

Generate and save a `ggplot` image directly from your notebook using a reproducible method. Make sure the filename matches what’s referenced in Step 1.

*Example (in R)*:

```yaml
ggsave("../img/<image>.png", plot = plot_object_name, width = 6, height = 4, dpi = 300)
```

In case you are interested in saving an html-based image, you can use the `htmlwidgets` and `webshot2` libraries. A usage example is available on the `bcindigenousbiz` notebook.

**6 - Preview and Render Changes**

Before pushing:

- Run quarto preview to check your edits.
- Run quarto render to build the site.
 Links to hosted notebooks won’t work locally—use the host URL to inspect the rendered version.