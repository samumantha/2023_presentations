
.center[


# ~~Computing environment~~ Reproducibility 

<br>

Samantha Wittke, CSC - IT center for Science
]
---


## Terminology

![](img/reproducible-definition-grid.svg)

The Turing Way project illustration. Used under a CC-BY 4.0 licence. DOI: 10.5281/zenodo.3332807.

---

## Steps towards reproducible research

![](img/reproducible-research.jpg)

---

### It all starts with a good directory structure...

```
project_name/
├── README.md             # overview of the project
├── data/                 # data files used in the project
│   ├── README.md         # describes where data came from
│   └── sub-folder/       # may contain subdirectories
├── processed_data/       # intermediate files from the analysis
├── manuscript/           # manuscript describing the results
├── results/              # results of the analysis (data, tables, figures)
├── src/                  # contains all code in the project
│   ├── LICENSE           # license for your code
│   ├── requirements.txt  # software requirements and dependencies
│   └── ...
└── doc/                  # documentation for your project
    ├── index.rst
    └── ...
```

... and version control, releases, tags ...

---

### Tracking dependencies

Avoiding "dependency hell" , i.e. different codes requiring differnt package versions, possibly incompatible.

Available tools (e.g. Conda, pip, virtualenv, Pipenv, pyenv, Poetry, renv, ...) may help with:

* Defining a **specific set of dependencies**, possibly with well defined versions
* Installing those dependencies mostly **automatically**
* **Recording the versions** for all dependencies
* **Isolate environments** -> you know and can share your dependencies
  * On your computer for projects so they can use different software
  * Isolate environments on computers with many users (and allow self-installations)
  * Using different Python/R versions per project
* Provide tools and services to **share packages**

If things go wrong, you can delete and re-create - much better use of time than debugging. 

> The more often you re-create your environment, the more reproducible it is.


---


### Recording environments

 > "It works on my machine" ¯\_(ツ)_/¯

---

#### Containers

Simplified: Shipping an entire operating system with software installed (and data) in one file.

A **container image** is like a piece of paper with all the operating system on it. When you run it, a transparent sheet is placed on top to form a container. The container runs and writes only on that transparent sheet (and what other mounts have been layered on top). When you are done, transparency is thrown away. It can be repeated as often as you want, and base is always the same.

**Definition files** (e.g. Dockerfile or Singularity definition file) are text files that contain a series of instructions to build container images

For container reproducibility: Use version tags when pulling images from repositories also in definition files.

---

### Sharing code and data

![](img/8-fair-principles.jpg)
The Turing Way project illustration. Used under a CC-BY 4.0 licence. DOI: 10.5281/zenodo.3332807.

* Findable - Will anyone else know that your data exists? -> get digital object identifier (DOI)
* Accessible - Can anyone else get your data? -> use a repository
* Interoperable - Is your data in a format that can be used by others? -> check recommendations for your field
* Reusable - Is there a license allowing others to re-use?

[Registry of Research data repositories](https://www.re3data.org), e.g. international ([Zenodo](https://zenodo.org/), [Figshare](https://figshare.com/), [EUDAT](https://eudat.eu/),...) or national repositories.

Even though this is usually referred to as “open data”, it means considering and making good decisions, even if non-open.

FAIR principles are usually discussed in the context of data, but they apply also for research software.

---


### Recording computational steps

In general: scripted solutions are more reproducible than single runs, however depending on scripting skills you might run into limitations as soon as computational steps get more or more timeconsuming.

Workflow tools to the rescue:

    * No extensive scripting skills needed
    * Record computational steps with additional arguments, requirements etc...
    * One step in the workflow changed? -> rerun only necessary steps
    
---
    
Some workflow tools:

* [Snakemake](https://snakemake.readthedocs.io/en/stable/)
* [Make](https://www.gnu.org/software/make/)
* [Common Workflow Language](https://www.commonwl.org/)
* [Long list of other general and more specialized tools](https://github.com/common-workflow-language/common-workflow-language/wiki/Existing-Workflow-systems)

Note also the tools integration with Github, containers, and usability/efficiency on HPC
Check out also CSC guide on [High Throughput Computing](https://docs.csc.fi/computing/running/throughput/).

---

### References and Resources

[CodeRefinery reproducible research lesson](https://coderefinery.github.io/reproducible-research/)

[The Turing way - Guide for reproducible research](https://coderefinery.github.io/reproducible-research/)

