# BIOC3301_Data_Processing

QIIME Illumina data processing workflow

Map file used for analysis:
Map.tsv

To join forward and reverse Illumina reads:
join_paired_ends.pbs

Demultiplex sequences:
split_libraries_joined.pbs

Closed OTUs were picked using Greengenes 13_8 (2006):
Otus_closed_GG.pbs

Singleton OTUs were removed:
Otus_no_singletons.pbs

OTUs were summarised at levels L1-6:
summarize_otus_taxa.pbs

Core diversity analysis was run at sampling depth 35000 to include all samples except one outlier with significantly low counts/sample:
CDA_GG_FRESH_35000.pbs

2D PCoA plots were generated using weighted Unifrac distance coordinates:
make_2D_plots.pbs

ANOSIM statistical tests were performed on weighted UniFrac distances to identify any sample clustering based on metadata categories: 
ANOSIM_K.pbs 
ANOSIM_N.pbs 
ANOSIM_P.pbs 
ANOSIM_depth.pbs 
ANOSIM_moisture.pbs 
ANOSIM_pH.pbs

Procrustes analysis was performed to compare unweighted and weighted UniFrac matrices to ensure the same beta diversity inferences were made regardless of the metric adopted for comparing samples:
Procrustes.pbs

Procrustes analysis showed the weighted and unweighted UniFrac matrices were statistically different, hence ANOSIM was repeated using the unweighted UniFrac distance matrix to remove the influence of dominant OTUs:
ANOSIM_K_unweighted.pbs 
ANOSIM_N_unweighted.pbs 
ANOSIM_P_unweighted.pbs 
ANOSIM_depth_unweighted.pbs 
ANOSIM_moisture_unweighted.pbs 
ANOSIM_pH_unweighted.pbs

Kruskal-Wallis variance tests were performed at phylum-level to establish whether there were significant differences between the samples’ actual phyla abundances as a result of grouping based on a metadata category:
GS_K.pbs 
GS_Depth.pbs 
GS_Moisture.pbs 
GS_N.pbs 
GS_P.pbs 
GS_pH.pbs
