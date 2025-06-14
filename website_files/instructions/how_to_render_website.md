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

**1. Clone the repository**

Using your shell terminal:

```bash
git clone git@github.com:diverse-data-hub/diverse-data-hub.github.io.git
cd diverse-data-hub.github.io
```

**2. Open the R project**

Open the `.Rproj` file in RStudio

Make sure your working directory is set to the project root.

**3. Ensure installation of `renv` package**

If the library `renv` is not installed run the following line in the R console. If already installed, skip to the next step:

```R
install.packages("renv")  
```

**4. Restore the project environment**

Restore the environment (already created with `rev::init()`) in the R console:

```R
renv::restore()
```

This installs the correct package versions from renv.lock.

In case this step throws an error like `Error: This project does not contain a lockfile.`, try the following command to restore the environment:

```R
renv::snapshot()
```

Following the command, restart your R session and retry the `renv::restore()` command-

**5. Confirm renv status**

Close up the R project and reopen it. Check that your environment matches the lockfile and everything is synced running the following in your R console:

```R
renv::status()
```

You should see a message like: *No issues found - the project is in a consistent state.*

**6. Preview or Render the Quarto site**

*NOTE:* Rendering time may vary depending on the number of updates applied across multiple files.

Now in your shell console, you can run:

```bash
quarto preview
```

```bash
quarto render
```

Now you are able to render your updates and they will be visible on the website when merged to the `main` branch.

**Optional** - To Update Dependencies

If you add new R packages to a new notebook, run in the R console with the R project opened and the environment restored:

```r
renv::snapshot()
```

**Optional** - To Clean Dependencies

To see which packages are installed but are not used, run in the R console with the R project opened and the environment restored:

```r
renv::clean()
```

This identifies unused packages and offers to remove them.