# ImgNetMaker

**ImgNetMaker** is a browser-based tool that converts a CSV file and/or an image folder into network-ready data for visualising image networks with [Gephi Lite](https://gephi.org/gephi-lite/).

**Public beta:** `v0.1.0-beta`  
**Launch the tool:** [https://datavana.github.io/imgnetmkr](https://datavana.github.io/imgnetmkr)

## What ImgNetMaker does

ImgNetMaker offers two entry points:

### CSV → Images + Data URLs

Provide a CSV containing at least one image-URL column and any additional metadata needed for analysis.

ImgNetMaker:

- downloads each accessible image;
- derives a clean and stable filename;
- converts the image into a Base64 data URL;
- adds the fields `inm_status`, `inm_filename` and `inm_imgdataurl`; and
- exports an enhanced CSV together with a ZIP folder containing the downloaded images.

### Image folder → Data URLs

Provide an image folder whose filenames correspond to values in your existing dataset.

ImgNetMaker:

- processes the files locally in your browser;
- leaves the original folder unchanged;
- converts each image into a Base64 data URL; and
- exports a CSV containing `inm_status`, `inm_filename` and `inm_imgdataurl`.

You can join this output to your original dataset by matching its image-filename field with `inm_filename`.

## From ImgNetMaker to an image network

1. Use [Table2Net](https://medialab.github.io/table2net/) to construct a bipartite network from the enhanced CSV.
2. Include `inm_imgdataurl` as an attribute of the image nodes, together with any other relevant metadata.
3. Export the network as a GEXF file.
4. Open the GEXF file in [Gephi Lite](https://gephi.org/gephi-lite/).
5. Under **Appearance → Nodes → Images**, select the attribute containing `inm_imgdataurl` as the image source.
6. Apply a layout such as ForceAtlas2 and zoom into the network to inspect the images.

## Local development

The ImgNetMaker source code is contained in the [`docs`](docs) folder and is written in HTML, CSS and JavaScript.

To run it locally:

1. Clone this repository.
2. Open `docs/index.html` in a web browser.
3. Select one of the two ImgNetMaker workflows and process a test dataset.

The application runs in the browser and does not require a server-side installation.

## How to cite

Omena, J. J., & Jünger, J. (2025). *ImgNetMaker* (v0.1.0-beta) [Computer software]. GitHub. Conceptualised during Omena's 2025 research fellowship at the Centre for Digitized Public Spheres Research, University of Münster, and implemented during Methods Café Week in Münster.

## Contributors

ImgNetMaker grew out of an [invited research fellowship](https://www.uni-muenster.de/Kowi/en/mitteilungen/dr-janna-joceli-omena-neue-fellow-am-ifk.shtml) in September 2025. Janna Joceli Omena developed the conceptual framework and implementation method, while Jakob Jünger led the software engineering.

The roles below follow the [Contributor Roles Taxonomy (CRediT)](https://doi.org/10.5281/zenodo.18421449). The qualifiers *lead*, *equal* and *supporting* indicate the degree of contribution.

| Contributor | CRediT roles |
| --- | --- |
| [Janna Joceli Omena](https://orcid.org/0000-0001-8445-9502) | **Conceptualization, lead**; **Methodology, lead**; **Project administration, lead**; **Supervision, lead** (research and methodology); **Validation, equal**; **Visualization, equal** |
| [Jakob Jünger](https://orcid.org/0000-0003-1860-6695) | **Software, lead**; **Supervision, lead** (software development); **Project administration, supporting**; **Validation, equal**; **Visualization, equal**; **Methodology, supporting** |
| [Katharina Maubach](https://orcid.org/0009-0005-1466-7943) | **Software, supporting**; **Validation, supporting** |
| [Lennart Höfig](https://orcid.org/0009-0001-8500-3117) | **Software, supporting**; **Validation, supporting** |
| Jane Knispel | **Software, supporting**; **Validation, supporting** |

### Methods Café Week acknowledgements

The development process also benefited from participation and discussion during Methods Café Week by Annabell Jendrilek, [Georg Hertkorn](https://orcid.org/0009-0005-0760-2818), Henrieke Kotthoff, Johanna Stahl, [Luana Moraes Costa](https://orcid.org/0009-0004-3303-8408), [Maiia Guseva](https://orcid.org/0009-0006-5024-7919) and [Paula Dicke](https://orcid.org/0009-0001-2141-1031).

## Third-party components and design credits

- Background image by [Pawel Czerwinski](https://unsplash.com/de/@pawel_czerwinski), used under the Unsplash Licence.
- ImgNetMaker logo © 2025 Janna Joceli Omena, licensed under CC BY 4.0. Its iconography draws on B. Gobbo and J. J. Omena's *Researching visual protest and politics with ‘extra-hard’ data* (2024); the ImgNetMaker mark is a newly redrawn square-node variant.
- [Font Awesome](https://fontawesome.com/), SIL OFL 1.1.
- [Papa Parse](https://www.papaparse.com/), MIT Licence.
- [JSZip](https://stuk.github.io/jszip/), MIT Licence.
- [FileSaver.js](https://github.com/eligrey/FileSaver.js), MIT Licence.

## Licence

The ImgNetMaker software is released under the [MIT Licence](LICENSE).
