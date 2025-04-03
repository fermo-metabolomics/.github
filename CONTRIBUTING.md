Thank you for your interest in contributing to FERMO! We welcome and appreciate all contributions.

All contributors, maintainers, and participants of the FERMO projects are expected to follow our [Code of Conduct](CODE_OF_CONDUCT.md). 

This document is organized as follows:

1. [Code Contribution](#code-contribution)
   1. [FERMO](#fermo)
   2. [fermo core](#fermo-core)


## Code Contribution

All repositories in the FERMO Metabolomics Organisation follow the [GitHub Flow](https://guides.github.com/introduction/flow) model for code contributions.

While code contributions are welcome, please discuss your ideas first on the FERMO Metabolomics [Discussions Board](https://github.com/orgs/fermo-metabolomics/discussions) before submitting a pull request.

#### Step-by-step guide

To contribute code, follow these steps. For repository-specific details, refer to the README of the respective repository.

1. [Create a fork](https://help.github.com/articles/fork-a-repo) using your GitHub account (or an organization you belong to).
2. [Clone your fork](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) to your local machine.
3. Install `hatch` using one of the recommended methods.
4. Install the package using `hatch env crate`
5. Initialize `pre-commit` with `hatch run pre-commit install`
6. Make changes to the code
7. Test that your code passes quality assurance by running `pytest`
8. Commit changes to your fork with `git commit`. `pre-commit` will run a set of linters to ensure high code quality.
9. Push changes to your fork with `git push`
10. Repeat steps 5-8 as needed
11. Describe your changes in the `CHANGELOG.md` file
12. Submit a pull request back to the upstream repository
13. A code review takes place, resulting in accept, accept with revision, or reject. 
14. If accepted and revisions have taken place, the fork is merged into `main` and deleted.

#### Code style

- All projects use a `pyproject.toml` file for metadata management, including dependencies. Semantic versioning and keeping a CHANGELOG are mandatory.
- `pydantic` models are preferred where applicable. Static typing outside the use of `pydantic` is strongly encouraged but not enforced.
- `ruff` is used for linting and formatting (applied automatically using `pre-commit`). This code style mostly adheres to the commonly used `black` style. See the `pyproject.toml` files for a list of plugins.
- Functions, classes, and methods must have expressive documentation using `numpy`-style docstrings. In-line comments are strongly discouraged.
- Logging is performed using the built-in `logging` module.
- Unit testing is performed exclusively using the `pytest` library.
- A continuous integration service using GitHub Actions is in place that run automated checks once a pull request is submitted. 

### FERMO

The [FERMO](https://github.com/mmzdouc/fermo) repository contains the FERMO GUI.
As a web application, unit testing is less strictly enforced. However, a local rebuild of the Docker container is required before submitting a pull request.

### fermo core

The [fermo_core](https://github.com/mmzdouc/fermo_core) repository contains the code for FERMO backend processing pipeline.
To maintain the integrity of the project, all new functionality must be unit tested.