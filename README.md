# Diverse Data Hub

Welcome to the Diverse Data Hub repository! 👋 This repository is an Open Educational Resource (OER) that features datasets centered on a wide range of diverse topics, including EDI-related data. By curating freely available and open-source data, the repository provides users with an accessible resource to explore diverse and meaningful topics in their work or studies. 

The datasets will be easily accessible through an open-access website and as R and Python packages, enabling seamless integration into the workflows of students, educators, and practitioners. Along with the datasets, there are example case studies that showcase various types of data science questions, offering users motivation and practical inspiration for incorporating these topics into their work. Information about each dataset, along with its contextual relevance, is also documented to promote connections to real-world issues and stimulate meaningful discussions.

# Developer Notes

## How to Render Website

Go [here](https://github.com/diverse-data-hub/diverse-data-hub.github.io/blob/main/website_files/instructions/how_to_render_website.md) for step by step instructions on how to re-render website while using the provided `renv` environment.

## How to Add a New Notebook to the Website

Go [here](https://github.com/diverse-data-hub/diverse-data-hub.github.io/blob/main/website_files/instructions/how_to_publish_a_new_notebook.md) for step by step instructions on how to add a new `.qmd` analysis to the website.

## How to Re-Run Data Cleaning Process

Go [here](https://github.com/diverse-data-hub/diverse-data-hub.github.io/blob/main/website_files/instructions/how_to_rerun_data_cleaning.md) for step by step instructions on how to re-run the `.ipynb` notebooks that describe the data cleaning processes while using the provided `environment.yaml` conda environment provided.

## How to Re-Run Independent Analysis

Go [here](https://github.com/diverse-data-hub/diverse-data-hub.github.io/blob/main/website_files/instructions/how_to_rerun_independent_analysis.md) for step by step instructions on how to re-run any analysis `.qmd` isolated from the website.

## How to Install the `diversedata` R Package

Please, refer to the R Package [repository's README](https://github.com/diverse-data-hub/diversedata/blob/main/README.md) for detailed instructions.

# Repository Structure

diverse-data-hub/
│
├── README.md                           # Project overview and Developer Instructions
├── LICENSE                             # License file
├── .gitignore                          # Git ignored files
├── environment.yaml                    # Python environment for cleaning scripts reproducibility
├── _quarto.yml                         # Quarto Website configuration
├── index.qmd                           # Website homepage
├── .Rprofile                           # R Profile
├── diverse-data-hub.github.io.Rproj    # R Project
├── renv.lock                           # R Environment
│
├── website_files/                      # Website pages and assets
│   ├── notebooks/                      # QMD files with data set analysis
│   │   ├── wildfire_exA.qmd
│   │   └── ...
│   ├── description_pages/              # QMD with data set attributes
│   ├── instructions/                   # MD files with website instructions
│   ├── grid_items/                     # Data Cards for Website CSS elements
│   ├── img/                            # Website Images
│   ├── citation.qmd                    # QMD for Citation page
│   ├── styles.scss                     # CSS attributes modifying template
│   └── styles.css                      # Custom CSS for website
│
├── docs/                               # Rendered Quarto site output (for GitHub Pages)
│
├── renv/                               # R project environment files
│
├── data/
│   ├── raw/                            # All original data sources
│   │   ├── LGBTIQ-rights/
│   │   ├── gender-assessment/
│   │   ├── how-couples-meet-and-stay-together/
│   │   ├── indigenous-businesses/
│   │   ├── wildfire/
│   │   └── womens-march-madness/
│   └── clean/                          # Cleaned datasets for analysis
│       ├── womens-match-madness-clean.csv
│       └── ...
│
├── scripts/                            # Notebooks with data cleaning narrative
│   ├── march_madness_clean.ipynb
│   └── ...