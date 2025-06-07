## Instructions to Re-Run Data Cleaning Process

**1. Clone the repository**

```bash
git clone git@github.com:diverse-data-hub/diverse-data-hub.github.io.git
cd diverse-data-hub.github.io
```

**2. Create the Conda environment from environment.yml**

```bash
conda env create -file environment.yml
```

This reads the YAML file and installs all required packages.

**3. Activate the environment**

```bash
conda activate mds_capstone_v1
```

**4. Launch Jupyter Lab**

```bash
jupyter lab
```

All data cleaning notebooks and associated narratives (`.ipynb`) are available through the `scripts/` folder to run in `jupyter lab`.

## How to re:

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
- Data Set Information section
- Download button (`href`) path
- Complete metadata table (`field-value`)
- Variable table (respect header structures)
- Ensure correct paths to notebooks
- Attribution

**3 - Add the Notebook File:**

*File*: `website_files/notebooks/<datasetfile>.qmd`

*Structure:*

- Follow the template format.
- Should include: `About the Data` (Key Features on Dataset, Purpose and Use Cases), `Case Study` (Objective, Methodology) 

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

Generate and save the image directly from your notebook using a reproducible method. Make sure the filename matches what’s referenced in Step 1.

*Example (in R)*:

```yaml
ggsave("../img/<image>.png", plot = plot_object_name, width = 6, height = 4, dpi = 300)
```

**6 - Preview and Render Changes**

Before pushing:

- Run quarto preview to check your edits.
- Run quarto render to build the site.

**Important Note**: Givent that the website counts on hard-coded links, use the host URL and the folder structure to inspect the preview/rendered local version of the website.