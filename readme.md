# Mantella Documentation repository

The built documentation can be accessed at [https://leidtier.github.io/MantellaDocs/](https://leidtier.github.io/MantellaDocs/)

This is the repository for the source of the documentation of [Mantella](https://github.com/art-from-the-machine/Mantella)

The documentation for Mantella is created using [Sphinx](https://www.sphinx-doc.org/) and the [Furo theme](https://github.com/pradyunsg/furo)

# Contribute
To contribute to Mantella's documentation follow the chapters below.

## Requirements
- Git
- Python 3.11
- A markdown editor
    - Visual Studio Code is doing a quite good job here

## Quick Setup
This part is a fast setup guide for people who know how to work with Git and Python

1. Clone the repo to your machine
2. `cd` to your new local repo
3. Create a virtual environment via `py -3.11 -m venv MantellaEnv` in your console
4. Start the environment in your console (`.\MantellaEnv\Scripts\Activate`)
5. Install the required packages via `pip install -r requirements.txt`

You can now already work with and build this Sphinx project:

1. `cd` to your new local repo
2. call `make html`
3. Sphinx will build the repository as a static site and place it in `/your_repo/build/html`
4. Open the new site by opening `/your_repo/build/html/index.html` in your browser

To edit the project, Visual Studio Code has proven to be a useful tool with some support for Markdown already installed:

1. Install [Visual Studio Code](https://code.visualstudio.com/)
2. Open the source by `File -> Open Folder...` and then opening `/your_repo/source`
3. Open a markdown file ended in `.md` like `index.md` directly in the source folder
4. Right click its tab and select `Open Preview` or press `CTRL+SHIFT+V` to open a preview of the markdown file (Note: the built result will look different in style, but this helps to find issues in your markdown) 
5. Add extensions to Visual Studio to make your life easier
    - MyST-Markdown <- This adds support for the markdown syntax extension used by Sphinx to the preview in Visual Studio Code
    - Todo Tree <- Highlights different versions of `%ToDo: XXX` in the project and is able to generate a list of them

Push your changes to the repository to trigger an automatic build and deplox using Github worksflow.
It is recommended to check your changes first on your local system