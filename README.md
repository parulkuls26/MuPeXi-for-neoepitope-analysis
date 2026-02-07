# MuPeXi-for-neoepitope-analysis

Introduction
Tumour neoantigens are peptides derived from somatic mutations that can be presented on major histocompatibility complex (MHC) molecules and recognised by T cells. Due to their tumour specificity, neoantigens represent promising targets for cancer immunotherapy. In this study, neoantigen prediction was performed on four skin tumour samples (WD06, WD13, WD14 and WD22) using MuPeXi. Somatic variants were analysed against matched normal samples, focusing on HLA-A02:01 and HLA-A24:02 alleles and peptide lengths of 8–11 amino acids. The analysis aimed to quantify tumour neoantigen burden, identify strong tumour-specific neoantigens, and assess whether any neoantigens are shared across tumours.
The VCFs (the VCF files of four skin tumour samples, namely WD06, WD13, WD14, WD22, with somatic mutations called against the matched normal reported with the coordinates in the hg38 format). are avaliable in the folder uploaded separately in this reporsitory.
The outputs : log and MuPeXi files have been uploaded separately in folder 2.

I followed the method published by Anne-Mette Bjerregaard and Aron C. Eklund
Given a list of somatic mutations (VCF file) as input, MuPeXI returns a table containing all mutated peptides (neo-peptides) of user-defined lengths, along with several pieces of information relevant for identifying which of these neo-peptides are likely to serve as neo-epitopes.

NEW: MuPeXI is now tested and compatible for suquencing data of murine origin.

License:

MuPeXI is freely available for academic users (see License) , other users are requested to contact CBS Software Package Manager at software@cbs.dtu.dk.

Citation:

Original paper

Bjerregaard AM, Nielsen M, Hadrup SR, Szallasi Z, Eklund AC.
MuPeXI: Prediction of neo-epitopes from tumor sequencing data.
Cancer Immunol Immunother. 2017 Apr 20. doi: 10.1007/s00262-017-2001-3.
PubMed ID: 28429069
You can read the paper here: http://rdcu.be/rwVP

Murine compatible version

For use of the murine species option additonal citation of the following would be highly appreciated. Bjerregaard AM, Pedersen TK, Marquard AM, Hadrup SR. Prediction of neoepitopes from murine sequencing data. Cancer Immunol Immunother. 2018 Oct 05. doi: 10.1007/s00262-018-2254-5. PubMed ID: 30291365 You can read the paper here: https://rdcu.be/8ExV

Web servers:

For limited data, MuPeXI can be run on our human specific web server and mouse specific web server
Web servers:

For limited data, MuPeXI can be run on our human specific web server and mouse specific web server

Dependencies

Hardware:

MuPeXI currently runs only on x86_64 machines running Linux or Darwin.

Required software:

Python 2.7
NetMHCpan 4.0
Variant Effect Predictor (VEP)
Required Python modules:

Biopython
numpy
pandas
Note: These modules are already included if using Python through Anaconda.

Optional software, required only for liftover from HG19

Picard tools
Java 8
Installation

Install all software listed above.

Download or clone the MuPeXI repository to your local system

 git clone https://github.com/ambj/MuPeXI.git
Obtain the reference files from GRCh38. These include cDNA, peptide and COSMIC files; see the References section in the user manual for a detailed description.

Fill in the config.ini file

Provide the full path to NetMHCpan and VEP.
Provide the full path to the reference files:
cDNA
peptide
COSMIC
Additional peptide references and liftover paths can be provided in the config.ini file; see the user manual for detailed information. Instructions on how to fill in the config.ini file are found within the file. config.ini is automatically found if it is in the same directory as MuPeXI.py script, but it can also be placed elsewhere and specified by the -c option.

Usage

Here is a simple example in which somatic mutation calls and gene expression data are provided, and MHC binding is predicted for HLA types HLA-A01:01 and HLA-B08:01.

path/to/MuPeXI.py -v mutations.vcf -a HLA-A01:01,HLA-B08:01 -e expression.tsv
MuPeXI can be used for both peptide extraction, giving immunogenicity information for peptide selection (the default), and for generation of a FASTA-formatted mutant-peptide file suitable for input to mass spectrometry peptide search software (with the -f option).

All options can be displayed using the usage information with the -h option:

path/to/MuPeXI.py -h
User Manual

For detailed information about usage, input and output files, test examples and data preparation read the MuPeXI User Manual

FAQs

We pronounce it moo-PECKS-ee

