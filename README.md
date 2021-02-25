# ESDS Community Development Best Practices

The NASA ESDS Community Development Best Practices Working Group (CDBP) aims to
develop actionable tools and best practices that help new and existing open 
source projects make progress within the NASA Earth Science community.

See our guide at <https://ESIPFed.github.io/esds-community-guide/>

# Contributing to the guide

The ESDS community guide built using [MkDocs](https://www.mkdocs.org/) and the
[Material theme](https://squidfunk.github.io/mkdocs-material/). 

## How to

### Setting up a development environment

In order to easily manage dependencies, we recommend using dedicated project environments
via [Anaconda/Miniconda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html).
or [Python virtual environments](https://docs.python.org/3/tutorial/venv.html).

Once your environment is created, you can install the required dependencies with
```shell
python -m pip install -r requirements.txt
```

### Build and view the guide

With your development environment activated, run

```shell
mkdocs serve
```

to generate the guide. This will allow you to view it at <http://127.0.0.1:8000/>.
MkDocs will automatically watch for new/changed files in this directory and
rebuild the website for a live preview of your changes (just refresh the webpage!).

*Note: `mkdocs serve` captures your terminal; use `crtl+c` to exit. It is recommended you
use a second/dedicated terminal so that you can keep this command running.*

### Deploy

This guide is deployed to [GitHub Pages](https://pages.github.com/)at 
<https://ESIPFed.github.io/esds-community-guide/>. The website is served out of the 
special `gh-pages` branch of this repository and deployment is handled automatically 
with the [`deploy_to_github_io.yml`](.github/workflows/deploy_to_github_io.yml) 
Github Action for any merge to `main`.

## Markdown formatting

The way MkDocs and GitHub parse markdown documents is slightly different. Some compatibility tips:

* Raw links should be wrapped in carrots: `<https://example.com>`
* MkDocs is pickier about whitespace between types (e.g., headers, paragraphs, lists) and seems to 
expect indents to be 4 spaces. So to get a representation like:

    <hr/>
    
    - A list item
    
         ##### A sub list heading
        - A sub-list item
    
    <hr/>
      
    in MkDocs, you'll want to write it like: 
        
    ### Good
    ```markdown
    - A list item
    
        ##### A sub list heading
        - A sub-list item
    ```
    
    ### Bad
    ```markdown
    - A list item
      ##### A sub list heading
      - A sub-list item
    ```
    
    ```markdown
    - A list item
        ##### A sub list heading
        - A sub-list item
    ```
    
    ```markdown
    - A list item
    
      ##### A sub list heading
      - A sub-list item
    ```