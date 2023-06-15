
.center[

<img src="img/reproducibility.jpg" style="height: 300px;"/>

# ~~Computing environment~~ Reproducibility 

Samantha Wittke, CSC - IT Center for Science

![](https://i.creativecommons.org/l/by/4.0/88x31.png)

June 2023

]
---


<img src="img/reproducible-definition-grid.svg" style="height: 600px;"/>


The Turing Way project illustration (also front page). Used under a CC-BY 4.0 licence. DOI: 10.5281/zenodo.3332807.

---

<img src="img/reproducible-research.jpg" style="height: 600px;"/>


---

## It all starts with a good directory structure...



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

<br>
<br>

... and version control, tags, releases ...

---

## Tracking dependencies

<img src="img/python_environment.png" style="height: 500px;"/>
[https://xkcd.com/](https://xkcd.com/1987/)

---
## Tools

Conda, pip, virtualenv, Pipenv, pyenv, Poetry, renv, ... :

* **Specify** set of dependencies
* **Automatic** installation
* **Version record** for all dependencies
* **Isolate environments** -> you know and can share your dependencies
* Provide tools and services to **share packages**

<br>
<br>

If things go wrong, you can delete and re-create - much better use of time than debugging. 

> The more often you re-create your environment, the more reproducible it is.


---


## Recording environments



<br>
<br>
<br>
<br>


.center[
 
 "It works on my machine" 
 
 ¯\_(ツ)_/¯
 
 ]
 
<br>

---

## Containers

Simplified: Shipping an entire operating system with software installed (and data) in one file.

A **container image**  - a piece of paper with all the operating system on it. When you run it, a transparent sheet is placed on top to form a container. The container runs and writes only on that transparent sheet. When you are done, only original paper left. 

**Definition files** (e.g. Dockerfile or Singularity definition file) are text files that contain a series of instructions to build container images

> Container reproducibility: Version tags for pulling images from repositories; also in definition files.

---

## Sharing code and data


.left-column50[

<br>

<img src="img/8-fair-principles.jpg" style="height: 250px;"/>

]

.right-column50[

- **Findable** 
    - Will anyone else know that your data exists? -> get digital object identifier (DOI)
-  **Accessible** 
    - Can anyone else get your data? -> use a repository
- **Interoperable**
    - Is your data in a format that can be used by others? -> check recommendations for your field
- **Reusable** 
    - Is there a license allowing others to re-use?
]

---

## Data repositories

[Re3data: Registry of Research data repositories](https://www.re3data.org)

Some general international repos:

* [Zenodo](https://zenodo.org/)
* [Figshare](https://figshare.com/) 
* [EUDAT](https://eudat.eu/) 

<br>

FAIR data != “open data”; it means considering and making good decisions, even if non-open.

FAIR principles also apply for research software!

---

## Recording computational steps

<br>

> GUI < CLI runs < scripts < workflows ? 

<br>

Workflow tools, e.g. [Snakemake](https://snakemake.readthedocs.io/en/stable/), [Make](https://www.gnu.org/software/make/), [Common Workflow Language](https://www.commonwl.org/):

* No extensive scripting skills needed
* Record computational steps with additional arguments, requirements etc...
* One step in the workflow changed? -> rerun only necessary steps
 
<br>
 
> Check also integration with Git*, containers, and usability/efficiency on HPC!

---

## References and Resources

<br>

[CodeRefinery reproducible research lesson](https://coderefinery.github.io/reproducible-research/)

[The Turing way - Guide for reproducible research](https://coderefinery.github.io/reproducible-research/)
-> All scriberia illustrations: The Turing Way project illustration. Used under a CC-BY 4.0 licence. DOI: 10.5281/zenodo.3332807.

[CSC High Throughput Computing](https://docs.csc.fi/computing/running/throughput/)

[Long list of other general and specialized tools](https://github.com/common-workflow-language/common-workflow-language/wiki/Existing-Workflow-systems)

Slides brought to you by [Cicero](https://cicero.xyz/)

