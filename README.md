# Workshop SGS Nanopore Computational Metagenomics

A practical introduction to long-read metagenomics data science in the context of the GHPP SGS project 2023.

## Schedule links for the workshop

* [2023-09-25 - Monday: Welcome, Introduction to metagenomics, Linux re-cap](#0)  
* [2023-09-26 - Tuesday: Nanopore sequencing, data formats, QC, mapping](#1)  
* [2023-09-27 - Wednesday: Metagenomic read classification](#10)
* [2023-09-28 - Thursday: Metagenome assembly, binning, qc, and annotation](#11)
* [2023-09-29 - Friday: Final day, Miscellaneous](#4)  

## Instructors

* Martin Hoelzer (RKI MF1), Hugues Richard (RKI MF1), and Andele Conradie (RKI ZIG)

## Schedule

> All events are held at NU, room N04.03.028

### <a name="0"></a> Monday, 2023-09-25
| Time        | Welcome, Introduction to metagenomics, Linux re-cap |
| --          | --               |
| 10:00-11:00 | Talk: Long-read Metagenomics (by Josh Quick) | 
| 11:00-11:15 | [General information](day-welcome-linux-container-wms/general.md) |
| 11:15-12:30 | [Linux re-cap](day-welcome-linux-container-wms/linux.md) |
| 12:30-13:30 | Lunch break |
| 13:30-14:00 | Talk: RKI Genome Competence Center (MF1) |
| 14:00-14:30 | Continue Linux re-cap |
| 14:30-15:30 | [Hands-on & demo](day-welcome-linux-container-wms/hands-on.md) |
| 15:30-16:30 | Wrap-up & self study |

### <a name="1"></a> Tuesday, 2023-09-26
| Time        | Nanopore |
| --          | --               |
| 09:00-10:00 | Debriefing previous day and RKI MF1 intro |
| 10:00-11:00 | [Nanopore intro](day-nanopore/nanopore.md) |
| 11:00-11:30 | [Nanopore basecalling & data formats](day-nanopore/nanopore.md) |
| 11:30-12:00 | [Nanopore QC](day-nanopore/nanopore.md) |
| 12:00-13:00 | Lunch break |
| 14:00-14:30 | Coffee break |
| 14:30-16:00 | [Hands-on & demo (metagenomics)](day-nanopore/hands-on-metagenomics.md) |
| 16:00-16:15 | Wrap-up & questions |
| Bonus talks | [Metagenomic example projects](https://docs.google.com/presentation/d/1CmkZ28PHgQ8dVwmm-U82tjOR0sPEcOcTWkjQzWZd98o/edit?usp=sharing) |

### <a name="10"></a> Wednesday, 2023-09-27
| Time        | Metagenomic read classification |
| --          | --               |
| 09:00-09:30 | Debriefing previous day |
| 09:30-11:00 | [Long-read mapping](day-nanopore/mapping.md) & [Hands-on & demo, Part I Mapping](day-metagenomic-classification/hands-on.md) |
| 11:00-12:00 | [Metagenomic read classification](day-metagenomic-classification/README.md) |
| 12:00-13:00 | Lunch break |
| 13:00-14:30 | [Hands-on & demo, Part II Classification](day-metagenomic-classification/hands-on.md) |
| 14:30-15:00 | Coffee break |
| 15:00-15:45 | Continue practical session |
| 15:45-16:00 | Wrap-up & questions |

### <a name="11"></a> Thursday, 2023-09-28
| Time        | Metagenome assembly, binning, and annotation |
| --          | --               |
| 09:00-10:00 | Debriefing previous day |
| 10:00-12:00 | Continue [Hands-on & demo, Part II Classification](day-metagenomic-classification/hands-on.md) |
| 12:00-13:00 | Lunch break |
| 13:00-14:00 | [Metagenome-assembled genomes (MAGs)](day-metagenomic-assembly/README.md) |
| 14:00-14:30 | Coffee break |
| 14:30-16:00 | [Hands-on & demo](day-metagenomic-assembly/hands-on.md) |
| 16:00-16:15 | Wrap-up & questions |
| Bonus | Detour: 16S Metagenomics introduction and example pipeline |

### <a name="4"></a> Friday, 2023-09-29
| Time        | The Rest & Open Questions & Work on own data |
| --          | --               |
| 09:00-10:00 | Debriefing previous day |
| 10:00-12:00 | Work on own data |
| 12:00-13:00 | Lunch break |
| 13:00-14:00 | Continue work on own data |
| 14:00-14:30 | Wrap-up & questions |
| Bonus I | [Miscellaneous (bacteria)](day-misc/README.md) |
| Bonus II | [Hands-on & demo](day-misc/hands-on.md) |



## Acknowledgement

This course material is partly based on the following resources and on contributions from great people (no specific order):

* Martin Hoelzer, RKI MF1, content about Linux, container, Nextflow, sequencing, genomic surveillance & glueing everything together
* Hugues Richard, RKI MF1, metagenomics 
* Sebastian "Raverjay" Krautwurst, FSU Jena, some Linux and ONT content
* Stephan Fuchs, RKI MF1, some Linux and Assembly content, Slides on SARS-CoV-2 nomenclature & phylogeny 
* Matt Huska, RKI MF1, automatic test script for all md code blocks using [codedown](https://github.com/earldouglas/codedown) and general help
* Workshop structure inspired by [https://github.com/cinemaparis/2023](https://github.com/cinemaparis/2023)
* Some ONT intro slides from Josh Quick, [original](https://github.com/cinemaparis/2023/blob/main/day1-Tuesday/slides-Quick.pdf)
* [A. Murat Eren](https://merenlab.org) for awesome metagenomics slides and introductions
