## Document Format

This document utilizes a combination of Markdown and LaTeX, following the [pandoc](https://pandoc.org/) flavors for creating versatile outputs in PDF and HTML formats. The aim is to ensure clarity and consistency in documenting EpicChain's specifications and related materials.

For text that is manually generated and not part of an automated process, we adhere to a single line paragraph style, ensuring that content remains clean and easily readable.

## Build Instructions (Manual Build)

To manually build the specification documents, you will need to install both `pandoc` and a LaTeX base. For a detailed list of necessary components, refer to the Dockerfile provided in this repository.

Once you have `pandoc` and LaTeX installed, the build process is straightforward. Simply run the command `make`, and it will generate the specification paper in both PDF and HTML formats, ensuring that all documentation requirements are met.

## Build Using Docker

For the most convenient method of building the specification document, you can use [Docker](https://www.docker.com). Docker simplifies the process by providing a containerized environment with all the required tools pre-installed. 

To compile the specification paper in PDF format using Docker, execute:
```
make docker/pdf
```
The output will be generated and saved as `output/epicchain-spec-<revision>.pdf`. This method ensures that all dependencies are managed within the container, streamlining the build process.

If you need to build the Docker image locally, you can do so with the following command:
```
make image
```

## How to Contribute

If you have expertise in epicchain technology and are interested in contributing to the documentation, you are welcome to submit a Pull Request with your proposed changes. 

Our initial goal is to develop a comprehensive and broad version of the document. Future revisions and polishing will enhance the document's quality and detail.

## Adding Pictures

When adding pictures to the document, place them in the `pic` directory of the relevant section. We recommend using vector formats for the best quality and editability. Always provide the source file of the picture to facilitate future modifications.

Acceptable picture formats include:
* [PlantUML](https://plantuml.com/)
* [Draw.io](https://github.com/jgraph/drawio-desktop)
* SVG
* PDF
* PNG
* JPG

When referencing a picture in the document, do not include the file extension. The most appropriate format will be selected based on the output format of the document.

Example:
```
![Architecture Overview](pic/overview-sc2)
```

To convert all PlantUML files to SVG format, use:
```
make puml2svg
```
or
```
make docker/puml2svg
```

To convert all SVG files to PDF, use:
```
make svg2pdf
```
or
```
make docker/svg2pdf
```

### PlantUML

Place your [PlantUML](https://plantuml.com/) files in the `pic/` directory of the corresponding section, using `.puml` or `.plantuml` file extensions. These files will be automatically rendered to SVG format by the `puml2svg` make target.

### Draw.io

Diagrams created with [Draw.io](https://github.com/jgraph/drawio-desktop) should be exported to SVG format and saved in the `pic/` directory of the respective section. To prevent text rendering issues, please refer to [this guide](https://desk.draw.io/support/solutions/articles/16000042487). Ensure that the `Embed Images` checkbox is not selected to avoid saving raster image versions in PDF. Additionally, place the source `.drawio` file in the same directory as the exported SVG to allow for future edits.

## License

This document is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License (CC BY-NC-SA 4.0).

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.

The Pandoc/LaTeX template used, [Eisvogel](https://github.com/Wandmalfarbe/pandoc-latex-template/), is licensed under the BSD 3-Clause License.

