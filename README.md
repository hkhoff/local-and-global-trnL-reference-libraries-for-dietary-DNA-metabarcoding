# local-and-global-trnL-reference-libraries-for-dietary-DNA-metabarcoding
This repository provides comprehensive trnL-P6 reference libraries (global ENA sequences and local data for Yellowstone National Park) for use in dietary DNA metabarcoding, updated approximately every six months. Users who would like to skip the steps to generate reference libraries can download these files for immediate use. For users who would like to generate more current or customized libraries themselves, code pipelines are also provided.

**Instructions:**
_For users interested to download files for immediate use, we provide the following resources:_
a) A global library (titled 'PLN_global_library_YYYYMMDD'), which was created using all trnL-P6 sequences available from the European Nucleotide Archive (ENA) in the European Molecular Biology Laboratory’s European Bioinformatics Institute (EMBL-EBI). This file was created using the code pipeline provided for building global libraries ('obitools_step1_global_reference_library_YYYY.Rmd') and can be used to assign taxonomic information to plant sequences detected in herbivore diets.
b) A local library for Yellowstone National Park (titled 'YNP_local_library_YYYYMMDD'), created using unique trnL-P6 sequences from the 'Plants of Yellowstone' dataset developed in the Kartzinel Lab at Brown University (https://www.kartzinellab.com) published on the Barcode of Life Datasystems (most recent release: https://portal.boldsystems.org/recordset/DS-YNPBPR3). 

_For users interested to generate their own local or global reference libraries, we provide the following code:_
a) Creating a global _trn_L-P6 reference library ('obitools_step1_global_reference_library_YYYY.Rmd'). We use the ecoPCR program in obitools to simulate a PCR and to extract all sequences from the European Molecular Biology Laboratory (EMBL) that may be amplified in silico by the two primers (GGGCAATCCTGAGCCAA and CCATTGAGTCTCTGCACCTATC) used for PCR amplification. Primers and other parameters can be customized in the 'params' section of this notebook. 

  The list of steps for building this reference database are:
  1) Download the whole set of EMBL/ENA sequences from Globus
  2) Download the NCBI taxonomy
  3) Format sequences into the ecoPCR format
  4) Use ecoPCR to simulate amplification and build a reference database based on putatively amplified barcodes together with their recorded taxonomic information

b) Creating a local _trn_L-P6 reference library ('obitools_step1_global_reference_library_YYYY.Rmd'). We use the ecoPCR program in obitools to simulate a PCR. All local barcode sequences can be downloaded from BOLD and can be amplified in silico by the desired primers (e.g., GGGCAATCCTGAGCCAA and CCATTGAGTCTCTGCACCTATC for _trn_L-P6) for PCR amplification. The code results in the creation of the file 'projectcode_regionofinterest_completeDB_YYYYMMDD.fasta.'

  The list of steps for building this reference database are:
  1) Extract trnL-P6 from BOLD sequences
  2) Format sequences into the ecoPCR format
  3) Use ecoPCR to simulate amplification and build a reference database based on putatively amplified barcodes together with their recorded taxonomic information

_Steps 1-2 require the following python packages:_
cutadapt
obitools

We use these as interactive notebooks for our analyses; steps can be run on a high-performance cluster or a local computer; we have made comments in each notebook to describe the appropriate file paths at each step. We use RMarkdown files with the intention of having users run code in chunks and understand outputs at each step.
