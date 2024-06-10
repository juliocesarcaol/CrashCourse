# GenBank Sequence Downloader

**Author:** Julio Cesar Carrión-Olmedo  
**Date:** 2024-06-10  

## Overview

This project provides a step-by-step guide on how to download sequences from GenBank using R. The guide is written in an R Markdown document (`Genbank_Sequences.Rmd`) and includes instructions on installing necessary packages, searching for sequences, and saving them in FASTA format.

## Prerequisites

Before you begin, ensure you have the following installed:
- R (version 4.0.0 or later)
- RStudio (optional but recommended)

## Installation

You need to install the `rentrez` package, which provides an interface to the NCBI's E-utilities API. You can install it using the following command in your R console:

```r
install.packages("rentrez")
Usage

    Clone the Repository:

    sh

    git clone https://github.com/yourusername/genbank-sequence-downloader.git
    cd genbank-sequence-downloader

    Open the R Markdown Document:

    Open Genbank_Sequences.Rmd in RStudio or your preferred text editor.

    Run the R Markdown Document:

    Follow the instructions in the document to:
        Load the rentrez package
        Search for sequences related to a specific gene
        Fetch the sequence data
        Save the sequences to a file

    Save the Sequences:

    The sequences will be saved in a file named sequences.fasta in your working directory.

Example Code

Here is an example of how to search for and download sequences for the "cytochrome c oxidase I" gene in humans:

r

# Load the rentrez package
library(rentrez)

# Search for sequences
search_results <- entrez_search(db = "nucleotide", term = "cytochrome c oxidase I[Gene] AND Homo sapiens[Organism]", retmax = 10)

# Fetch the sequence data
accession_numbers <- search_results$ids
sequences <- entrez_fetch(db = "nucleotide", id = accession_numbers, rettype = "fasta")

# Save the sequences to a file
writeLines(sequences, "cytochrome_c_oxidase_I_sequences.fasta")

Customization

You can customize the search terms and the number of sequences retrieved by modifying the parameters in the entrez_search function. Additionally, if you already have a list of accession numbers, you can use those directly to fetch the sequence data.
License

This project is licensed under the MIT License. See the LICENSE file for details.
Contact

For questions or comments, please contact Julio Cesar Carrión-Olmedo at [julio.c.carrion97@gmail.com].
