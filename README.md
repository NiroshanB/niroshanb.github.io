# niroshanb.github.io

The source for my personal website, built with Quarto and published with GitHub Pages
at <https://niroshanb.github.io>. It has a home page, an about page, and a blog with
two computational posts: an analysis of the Palmer Penguins data in R, and the same
analysis in Python.

## What you need before you start

Install these first. The versions listed are the ones I used.

- [Quarto](https://quarto.org/docs/get-started/) 1.10.18
- [R](https://cran.r-project.org) 4.6.1
- [uv](https://docs.astral.sh/uv/getting-started/installation/) 0.12.7

You do not need to install renv or Python. Both are set up automatically by the
commands below.

## Building the site

Run every command from the top level of the repository.

### 1. Clone the repository and move into it

In a shell:

```bash
git clone https://github.com/niroshanb/niroshanb.github.io.git
cd niroshanb.github.io
```

### 2. Restore the Python environment

In a shell:

```bash
uv sync
```

### 3. Restore the R environment

Start an R session at the top level of the repository, then in the R console:

```r
renv::restore()
```

Answer `y` when it asks to proceed, then quit R.

### 4. Render the site

In a shell:

```bash
uv run quarto render
```

## Where the built site goes

Quarto writes the site to the `docs` folder. To open the home page on macOS:

```bash
open docs/index.html
```

Or serve the site on localhost:

```bash
uv run quarto preview
```

## Where the data comes from

Both posts use the Palmer Penguins dataset, collected by Dr. Kristen Gorman and the
Palmer Station Antarctica LTER and released under a
[CC0 licence](https://creativecommons.org/publicdomain/zero/1.0/).

The build does not need network access to fetch data, because the dataset ships inside
the palmerpenguins packages that `renv::restore()` and `uv sync` install. You do need
network access for steps 1 to 3, to clone the repository and download the packages.

Each post cites the data in full, in the post itself.

## Use of AI assistance

I used Kiro to assist with the analysis code in both posts.