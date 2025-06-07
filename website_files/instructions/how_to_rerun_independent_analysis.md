## Instructions to Re-Run Independent Analysis

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

**5. Open and Interact with Analysis**

All analysis notebooks are stored in `website_files/notebooks/`.

Open the `.qmd` file of interest in RStudio and interact with it as needed. 