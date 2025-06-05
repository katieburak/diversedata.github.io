# Diverse Data Hub

Welcome to the Diverse Data Hub repository! 👋 This repository is an Open Educational Resource (OER) that features datasets centered on a wide range of diverse topics, including EDI-related data. By curating freely available and open-source data, the repository provides users with an accessible resource to explore diverse and meaningful topics in their work or studies. 

The datasets will be easily accessible through an open-access website and as R and Python packages, enabling seamless integration into the workflows of students, educators, and practitioners. Along with the datasets, there are example case studies that showcase various types of data science questions, offering users motivation and practical inspiration for incorporating these topics into their work. Information about each dataset, along with its contextual relevance, is also documented to promote connections to real-world issues and stimulate meaningful discussions.

# Developer Notes

## How to Add a New Notebook to the Website

Go to `\website_fles\instructions\how_to_publish_a_new_notebook.md` for step by step instructions on how to add a new `.qmd` analysis to the website.

## Instructions to Re-Run Data Cleaning Process

1. Clone the repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

2. Create the Conda environment from environment.yml

```bash
conda env create -f environment.yml
```

This reads the YAML file and installs all required packages.

3. Activate the environment

```bash
conda activate your-env-name
```

4. Launch Jupyter Lab

```bash
jupyter lab
```

All data cleaning notebooks and associated narratives (`.ipynb`) are available through the `scripts\` folder to run in `jupyter lab`.

# Instructions to Render Website

The Quarto website `https://diverse-data-hub.github.io/` is deployed through GitHub Pages upon every push to main branch. Howeve, for updates to be visible on the website, developers require to `quarto render` the site before merging the updates to the main branch.

The main dependency to render the website is to have `Quarto` installed. While Quarto is usually installed with RStudio, Quarto CLI can be downloaded [here](https://quarto.org/docs/get-started/).

To preview or render the website using `quarto preview` or `quarto render` there are two avenues:

### 1 - Install all necessary packages in your computer

As a first option, you can ensure that all the required packages are installed in your computer. The following packages are used in the different analysis and having them installed is required to render the Quarto website:

```r

# For `Women's March Madness`:

install.packages("tidyverse")
install.packages("AER")
install.packages("broom")
install.packages("knitr")
install.packages("MASS")

# For `Wildfire` (Additional to what's listed above)

install.packages("lubridate")
install.packages("gt")
install.packages("ggmap")
install.packages("ggspatial")
install.packages("sf")
install.packages("terra")
install.packages("maptiles")
install.packages("viridis")
install.packages("marginaleffects")
install.packages("broom")
install.packages("kableExtra")

# For `How Couples Meet and Stay Together` (Additional to what's listed above)

install.packages("scales")
install.packages("cowplot")
install.packages("brant")
install.packages("knitr")

# For `Global Rights` (Additional to what's listed above)

install.packages("patchwork")
install.packages("car")
install.packages("FSA")
install.packages("PMCMRplus")

# For `Indigenous Business` (Additional to what's listed above)

TBD

# For `Gender Assessment` (Additional to what's listed above)

TBD

```

### 2 - Use the `renv` environment included in this repository

1. Clone the repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

2. Open the R project

Open the `.Rproj` file in RStudio

Make sure your working directory is set to the project root.

3. Restore the project environment

If the library `renv` is not installed:

```R
install.packages("renv")  
```

Otherwise, proceed to run in the R console:

```R
renv::restore()
```

This installs the correct package versions from renv.lock.

4. Confirm renv status
Check that your environment matches the lockfile and everything is synced:

```R
renv::status()
```

You should see a message like: *No issues found -- the project is in a consistent state.*

5. Preview or Render the Quarto site

```bash
quarto preview
```

```bash
quarto render
```

Now you are ready to render your updates and they will be visible on the website when merged to the main branch.

*Optional* - To Update Dependencies

If you add new R packages to a new notebook, run:

```r
renv::snapshot()
```

*Optional* - To Clean Dependencies

To see which packages are installed but are not used, run:

```r
renv::clean()
```