### Time
2022-01-10
### Person
Chen Yinghui [chen-yh19@mails.tsinghua.edu.cn]
Wang Hongke  [wanghk17@mails.tsinghua.edu.cn]
Tao Yuhuan  [tyh19@mails.tsinghua.edu.cn]
### Directoy
- processed
Main data storage directory. Including Bam, Gene_Expression_Quantification, etc.

- Metadata
The detailed clinical information for specific samples. The directory structure is same as "processed".

- backup
The backup directory.

- APP
gdc-client software for data download.

### Method
- mRNA analysis
[mRNA analysis pipeline](https://docs.gdc.cancer.gov/Data/Bioinformatics_Pipelines/Expression_mRNA_Pipeline/)
Alignment: STAR-2.4.2a
Quantification: HTSeq-0.6.1p1
Annotation: gencode.v22.annotation.gtf

- miRNA analysis
[miRNA analysis pipeline](https://docs.gdc.cancer.gov/Data/Bioinformatics_Pipelines/miRNA_Pipeline/)
Annotation: miRBase v21 and UCSC

### Download

- example pipeline: TCGA-KICH
- Step1: download metadata
  Search your interested cancer type on https://portal.gdc.cancer.gov, such as TCGA-KICH (Kidney Chromophobe, kidney cancer).
  Select your target 'Experimental Strategy', such as RNA-seq or miRNA-seq from https://portal.gdc.cancer.gov/projects/TCGA-KICH.
  Select the file type(s) required, such as 'HT-seq - Counts' or 'STAR 2-Pass'.
  Add all files to Cart.
  Download 'Biospecimen','Clinical','Sample Sheet','Metadata','Manifest'. Among all, 'Manifest' is the file list for downloading.
  Save 'Biospecimen','Clinical','Sample Sheet','Metadata' to related metadata directory.

- Step2: download files by gdc-client
  Option1: nohup /Share2/home/lulab1/TCGA/APP/gdc-client-v1.6.0 download -m /Share2/home/lulab1/TCGA/processed/Bam/RNA-Seq/mainfest/KICH_gdc_manifest_20220110_035206.txt --dir /Share2/home/lulab1/TCGA/processed/Bam/RNA-Seq/KICH --log-file /Share2/home/lulab1/TCGA/processed/Bam/RNA-Seq/download_logfile/KICH_log.txt -t /Share2/home/lulab1/TCGA/gdc-user-token.2022-01-10T04_05_12.147Z.txt > KICH_RNAseq_bam_count_download.log 2>&1 &
  Option2: /Share2/home/lulab1/TCGA/TCGA_download.sh

- [More readings](https://pumped-top-d2c.notion.site/TCGA-2f8079db8b6f4da4ae6fc031b561b0b9) 
