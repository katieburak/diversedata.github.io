## How to render the website:

The [Quarto website](https://diverse-data-hub.github.io/) is deployed through GitHub Pages upon every push to `main` branch. However, for updates to be visible on the website, developers must run `quarto render` before merging updates to the `main` branch.

Rendering the website requires `Quarto` to be installed. While Quarto is usually installed with RStudio, Quarto CLI can be downloaded [here](https://quarto.org/docs/get-started/).

To preview or render the website using `quarto preview` or `quarto render` you must have all used R packages installed. For this reason, we've provided a `renv` environment for easy installation:

The following R packages are used in various analyses and must be installed to render the Quarto website:

```r

# For `Women's March Madness`:

library("tidyverse")
library("AER")
library("broom")
library("knitr")
library("MASS")

# For `Wildfire` (Additional to what's listed above)

library("lubridate")
library("gt")
library("ggmap")
library("ggspatial")
library("sf")
library("terra")
library("maptiles")
library("viridis")
library("marginaleffects")
library("broom")
library("kableExtra")

# For `How Couples Meet and Stay Together` (Additional to what's listed above)

library("scales")
library("cowplot")
library("brant")
library("knitr")

# For `Global Rights` (Additional to what's listed above)

library("patchwork")
library("car")
library("FSA")
library("PMCMRplus")

# For `Indigenous Business` (Additional to what's listed above)

TBD

# For `Gender Assessment` (Additional to what's listed above)

TBD

```

### To use the `renv` environment included in this repository

*NOTE:* Some of these steps might take a few minutes. 

**1. Clone the repository**

```bash
git clone git@github.com:diverse-data-hub/diverse-data-hub.github.io.git
cd diverse-data-hub.github.io
```

**2. Open the R project**

Open the `.Rproj` file in RStudio

Make sure your working directory is set to the project root.

**3. Restore the project environment**

If the library `renv` is not installed:

```R
install.packages("renv")  
```

Otherwise, proceed to restore the environment (already created with `rev::init()`) in the R console:

```R
renv::restore()
```

This installs the correct package versions from renv.lock.

In case this step throws an error like `Error: This project does not contain a lockfile.`, try the following command to restore the environment:

```R
renv::snapshot()
```

**4. Confirm renv status**

Close up the R project and reopen it. Check that your environment matches the lockfile and everything is synced running:

```R
renv::status()
```

You should see a message like: *No issues found - the project is in a consistent state.*

**5. Preview or Render the Quarto site**

```bash
quarto preview
```

```bash
quarto render
```

Now you are able to render your updates and they will be visible on the website when merged to the `main` branch.

**Optional** - To Update Dependencies

If you add new R packages to a new notebook, run:

```r
renv::snapshot()
```

**Optional** - To Clean Dependencies

To see which packages are installed but are not used, run:

```r
renv::clean()
```

This identifies unused packages and offers to remove them.