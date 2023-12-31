# Lunaapahkiing Princeton Timetree

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.8040363.svg)](https://doi.org/10.5281/zenodo.8040363)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Hugo](https://img.shields.io/badge/hugo-0.117-blue.svg)](https://gohugo.io)
![Node version](https://img.shields.io/badge/node-18-blue)

This project contains an archived version of source code and content for the CDH-sponsored [Lunaapahkiing Princeton Timetree](https://cdh.princeton.edu/projects/lenape-timetree/) research project. In September 2023 the repository was split out to separate content and code, in order to simplify maintenance and ownership.  

Current versions of the content and code for this project are avialable at [Princeton-CDH/lenape-timetree-content](https://github.com/Princeton-CDH/lenape-timetree-content) and [Princeton-CDH/lenape-timetree](https://github.com/Princeton-CDH/lenape-timetree).


## License

### Content

Site content is licensed under the [Creative Commons Attribution 4.0 International License (CC-BY)](http://creativecommons.org/licenses/by/4.0/).

### Software

The software for this project is licensed under the [Apache 2.0 License](LICENSE).

## Developer + contributor setup instructions

For instructions on editing site content, refer to [CONTRIBUTING](CONTRIBUTING.md).
Local setup is not required for content editing.

### Hugo setup

To set the site up locally for development or content editing,
first follow the [instructions to install Hugo](https://gohugo.io/installation/).
You can check that Hugo is installed with:

```sh
hugo version
```

This should result in output something like this:

> hugo v0.101.0+extended darwin/amd64 BuildDate=unknown

Make sure the version you installed is at least as new as the version shown in the Hugo badge at the top of the project readme (this file).

Once hugo is installed, you'll need to install the javascript dependencies that are used to compile the site's javascript and scss resource files. To check if you have node installed:

```sh
node --version
```

This should output a version string that is at least as new as the version shown in the node badge at the top of this file. To install dependencies, run npm in the project's root directory:

```sh
npm install
```

If the install completes without errors, you're ready to run the site locally.

### Serving locally

To run a development server with auto-reload:

```sh
hugo server
```

You should see some debug output, followed by:

> Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
> Press Ctrl+C to stop

Open a web browser to the above address to see a local version of the site. When you make changes and save files locally, hugo will automatically refresh the page.

## Install pre-commmit hooks

Anyone planning to do development on the site (i.e., contributing to javascript,
scss, or templates), you need to install pre-commit hooks to automatically
ensure tht code is consistently formatted. This step is not required
for anyone who is working on site content and not modifying code or templates.

Commit hooks are managed with [pre-commit](https://pre-commit.com/).
To install, run:

```{bash}
pre-commit install
```

Current hooks include [Black](https://github.com/psf/black) for python code formatting, [isort](https://pycqa.github.io/isort/) for standardized python imports, and [Prettier](https://prettier.io/) for javascript, css, markdown, and other supported file types.

Standardized code styles were instituted after some development was done on this project.
To configure `git blame` to ignore the styling commit, use the following:

```{bash}
git blame <FILE> --ignore-revs-file .git-blame-ignore-revs
```

Or configure git to always ignore the styling revision commit:

```{bash}
git config blame.ignoreRevsFile .git-blame-ignore-revs
```
