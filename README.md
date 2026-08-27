# Nanorod uptake and colocalization analysis

Automated pipeline to quantify and characterize the uptake and colocalization of fluorescently labeled Nanorods (NRs) in brown adipocytes. Pipeline analyses confocal laser scanning microscopy data with stainings for lysosomes (LAMP1) and endosomes (EEA1). 

Developed as part of a master's thesis at Karolinska Institutet, Stockholm, 2026.

### Workflow overview:

**Image pre-processing** by using a PixelClassifier ([APOC](https://github.com/haesleinhuepf/napari-accelerated-pixel-and-object-classification)) to remove debris:
- Notebook 1: Label annotation
- Notebook 2: PixelClassifier Training
- Notebook 3:  Mask generation

*Environment:* APOC

**Image processing** (Notebook 4: Analysis) <br>
Quantification and analysis of NR uptake and of colocalization with lysosomes and endosomes. This step is fully automated and only requires initial selection/adjustment of:
- Cellpose parameters (not inevitably necessary but the segmentation efficiency should be checked beforehand)
- adjustment of absolute thresholds for segmentation of vesicles
- adjustment of relative thresholds for segmentation of vesicles

*Environment:* Cellpose

**Data extraction** (Notebook 5: Data extraction) <br>
Extract and filter data for plots and statistical analyses

*Environment*: Base

### Requirements
| Environment | Package | Version |
|-------------|---------|---------|
| **Cellpose** | cellpose | 3.1.1 |
| | matplotlib | 3.10.9 |
| | numpy | 2.0.2 |
| | pandas | 2.3.3 |
| | scikit-image | 0.25.2 |
| | scipy | 1.15.3 |
| | tifffile | 2025.5.10 |
| | | |
| **APOC** | apoc | 0.12.0 |
| | matplotlib | 3.9.4 |
| | napari | 0.5.6 |
| | napari-accelerated-pixel-and-object-classification | 0.14.1 |
| | numpy | 1.26.4 |
| | pandas | 2.3.3 |
| | scikit-image | 0.24.0 |
| | scikit-learn | 1.6.1 |
| | scipy | 1.13.1 |
| | tifffile | 2024.8.30 |
| | | |
| **Base** | matplotlib | 3.10.6 |
| | matplotlib-scalebar | 0.9.0 |
| | numpy | 2.3.5 |
| | pandas | 2.3.3 |
| | scipy | 1.16.3 |
| | seaborn | 0.13.2 |
| | tifffile | 2025.10.4 |


### References

Cellpose: <br>
Stringer, C., Wang, T., Michaelos, M., & Pachitariu, M. (2021). Cellpose: a generalist algorithm for cellular segmentation. Nature Methods, 18(1), 100-106.

APOC: <br>
R. Haase, K. Yamauchi, J. Müller, and Isuru Fernando. Haesleinhuepf/Apoc: 0.12.0. Zenodo. Dec. 2022. DOI: 10.5281/ZENODO.5813514.

napari: <br>
Sofroniew, N., Lambert, T., Evans, K., et al. (2022). napari: a multi-dimensional image viewer for Python. Zenodo. https://doi.org/10.5281/zenodo.3555620

scikit-image: <br>
S. Van Der Walt, J. L. Schönberger, J. Nunez-Iglesias, F. Boulogne, J. D. Warner, N. Yager, E. Gouillart, and T. Yu. “Scikit-Image: Image Processing in Python”. In: PeerJ 2 (June 2014), e453. DOI: 10.7717/peerj.453

scipy: <br>
P. Virtanen et al. “SciPy 1.0: Fundamental Algorithms for Scientific Computing in Python”. In: Nature Methods 17.3 (Mar. 2020), pp. 261–272. DOI: 10.1038/s41592-019-0686-2.

numpy: <br>
C. R. Harris, K. J. Millman, S. J. Van Der Walt, R. Gommers, P. Virtanen, D. Cournapeau, E. Wieser, J. Taylor, S. Berg, N. J. Smith, R. Kern, M. Picus, S. Hoyer, M. H. Van Kerkwijk, M. Brett, A. Haldane, J. F. Del Río, M. Wiebe, P. Peterson, P. Gérard-Marchant, K. Sheppard, T. Reddy, W. Weckesser, H. Abbasi, C. Gohlke, and T. E. Oliphant. “Array Programming with NumPy”. In: Nature 585.7825 (Sept. 2020), pp. 357–362. DOI: 10.1038/s41586-020- 2649-2.

