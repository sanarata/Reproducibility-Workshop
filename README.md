
# Acute Myeloid Leukemia Heatmap

This repository contains an R notebook that performs an analysis on an acute myeloid leukemia (AML) sample dataset. The analysis creates a heatmap to visualize RNA-sequencing results of AML under controlled treatment conditions. The data is obtained from 19 AML model mice.

The original analysis has been adapted from this [refine.bio-examples notebook](https://alexslemonade.github.io/refinebio-examples/03-rnaseq/clustering_rnaseq_01_heatmap.html) and the dataset can be downloaded from this [refine.bio page](https://www.refine.bio/experiments/SRP070849).

## Set Up

The R notebook makes use of several libraries. The main one used for generating the heatmap is `pheatmap` [Source 2](https://www.reneshbedre.com/blog/heatmap-with-pheatmap-package-r.html). Other libraries used include `magrittr` for the pipe operator and `readr` for reading in the data [Source 1](https://davetang.org/muse/2018/05/15/making-a-heatmap-in-r-with-the-pheatmap-package/).

Before running the notebook, ensure you have the following packages installed. If not, you can install them using the commands provided in the notebook:

```r
if (!("pheatmap" %in% installed.packages())) {
  # Install pheatmap
  install.packages("pheatmap", update = FALSE)
}
```

## Data

The data for this analysis was downloaded from refine.bio and has been pre-processed and quantile normalized [Source 4](https://www.geeksforgeeks.org/draw-heatmap-with-clusters-using-pheatmap-in-r/). The data includes 19 samples obtained from 19 acute myeloid leukemia (AML) model mice, containing RNA-sequencing results for types of AML under controlled treatment conditions.

The data files are stored in the `data` directory and include:

- `SRP070849.tsv`: This file contains the gene expression data.
- `metadata_SRP070849.tsv`: This file contains the metadata for the samples.

## Analysis

The analysis involves several steps:

1. Reading in the data and metadata.
2. Ensuring that the data and metadata are in the same order.
3. Selecting genes of interest based on their variance.
4. Preparing the metadata for annotation.
5. Creating an annotated heatmap.
6. Saving the heatmap as a PNG image.

The heatmap is created using the `pheatmap` function from the `pheatmap` package. The heatmap shows the expression levels of the selected genes across the different samples. The samples and genes are clustered using hierarchical clustering to show similarities and differences [Source 2](https://www.reneshbedre.com/blog/heatmap-with-pheatmap-package-r.html).

## Output

The output of the analysis is a PNG image of the annotated heatmap, which is saved in the `plots` directory. The image shows the expression levels of the selected genes across the different samples, with samples and genes that have similar expression patterns clustered together [Source 4](https://www.geeksforgeeks.org/draw-heatmap-with-clusters-using-pheatmap-in-r/).

In addition to the heatmap, a TSV file containing the selected genes is saved in the `results` directory.

## Session Info

The session info provides detailed information about the R environment in which the analysis was run. This includes information about the version of R and the packages that were loaded during the session. This can be useful for troubleshooting and for replicating the analysis [Source 1](https://davetang.org/muse/2018/05/15/making-a-heatmap-in-r-with-the-pheatmap-package/).