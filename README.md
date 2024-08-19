# mating_loci_Chaetothyriales
HMM profiles to identify the mating loci genes in Chaetothyriales (Fungi: Ascomycota)


These profiles were compiled by downloading from NCBI all genes sequences for the genes APN2,MAT-1-1, MAT-1-1-4, and MAT-1-2 previously identified by 
Teixeira et al. 2017, annotating all the sequences using InterPro v101.0 (Paysan-Lafosse et al. 2022), and correcting any previous missassingment (see the file "Teixeira_et_al_2017_IPRScan_annotations.csv"for more details). Each gene sequences were aligned using MAFFT v7 (Katoh and Standley 2013) and the “E-INS-i” 
strategy (the *.fas files). The resulting alignments were used to build HMM profiles using HMMER v3.3.2 (Eddy 2011). The generated profiles were concatenated in a 
single one, and it were able to correctly identified the genes of Teixeira et al. (2017) that obtained a full sequence scores higher than 100 (see the file "Results_Teixeira_et_al_2017_sequences_HMM_mating_loci_profile.txt").


################################# HOW TO USE THE PROFILE #######################################

For using this profile (the file "Teixeira_et_al_2017_corrected_MAT_profile_v0.1.hmm"), first you will need a working version of HMMER 3 (it can be downloaded at 
http://hmmer.org/). After installing HMMER you can run the profile search with the command below (run with everything in the same folder you are in the terminal (or 
add the paths to the files). As input you will need a fasta file with the protein sequences to be compared with the profile.

hmmsearch --tblout  NAME_YOUR_RESULTS.txt Teixeira_et_al_2017_corrected_MAT_profile_v0.1.hmm YOUR_PROTEINS.fasta 

The below are how the results should. In "target name" is the sequences titles and "query name" indicates which gene profile has a match for the target. As rule of 
thumb, a a full sequence score over 100 should be a true match, and all Domatiaceae genes identified with a full sequence score above 100 were confirmed by its 
annotation using IPRScan.

                                                               --- full sequence ---- --- best 1 domain ---- --- domain number estimation ----
target name        accession  query name           accession    E-value  score  bias   E-value  score  bias   exp reg clu  ov env dom rep inc description of target
------------------- ---------- -------------------- ---------- --------- ------ ----- --------- ------ -----   --- --- --- --- --- --- --- --- ---------------------
D134920_001188-T1    -          APN2                 -                  0 1039.5   7.5         0 1039.2   7.5   1.0   1   0   0   1   1   1   1 D134920_001188
D134920_006248-T1    -          APN2                 -              0.059   10.7  20.8     0.072   10.4  20.8   1.2   1   0   0   1   1   1   0 D134920_006248
D134920_005396-T1    -          APN2                 -               0.14    9.4   4.5      0.17    9.2   4.5   1.0   1   0   0   1   1   1   0 D134920_005396
D134920_003409-T1    -          APN2                 -                1.1    6.5  13.5       1.7    5.9  13.5   1.4   1   0   0   1   1   1   0 D134920_003409
D134920_000590-T1    -          APN2                 -                2.8    5.1  11.8       3.1    5.0  11.8   1.0   1   0   0   1   1   1   0 D134920_000590
D134920_001395-T1    -          APN2                 -                3.2    4.9  15.0       4.3    4.5  15.0   1.2   1   0   0   1   1   1   0 D134920_001395
D134920_004796-T1    -          APN2                 -                6.1    4.0  24.2       7.1    3.8  24.2   1.1   1   0   0   1   1   1   0 D134920_004796
D134920_000281-T1    -          APN2                 -                8.5    3.5  14.2        10    3.3  14.2   1.1   1   0   0   1   1   1   0 D134920_000281
D134920_001190-T1    -          MAT-1-1              -            4.2e-97  324.6  10.6   7.7e-97  323.7  10.6   1.3   1   1   0   1   1   1   1 D134920_001190
D134920_001189-T1    -          MAT-1-1              -            1.3e-07   30.2   0.0   1.5e-07   29.9   0.0   1.1   1   0   0   1   1   1   1 D134920_001189
D134920_001189-T1    -          MAT-1-1-4            -            1.5e-49  167.3   0.0   1.8e-49  166.9   0.0   1.0   1   0   0   1   1   1   1 D134920_001189
D134920_000766-T1    -          MAT-1-2              -            1.8e-13   49.4   1.5   2.9e-13   48.8   1.5   1.2   1   0   0   1   1   1   1 D134920_000766
D134920_006115-T1    -          MAT-1-2              -            3.2e-08   32.1   4.1   3.6e-08   32.0   4.1   1.0   1   0   0   1   1   1   1 D134920_006115
D134920_001390-T1    -          MAT-1-2              -              0.052   11.7   0.3     0.084   11.0   0.3   1.2   1   0   0   1   1   1   0 D134920_001390
D134920_001191-T1    -          SLA2                 -                  0 2213.4  40.7         0 2182.8  36.3   2.0   2   0   0   2   2   2   2 D134920_001191
D134920_004104-T1    -          SLA2                 -              0.073    9.4  17.3       0.1    8.9  17.3   1.2   1   0   0   1   1   1   0 D134920_004104
D134920_003931-T1    -          SLA2                 -              0.076    9.3  19.2     0.089    9.1  19.2   1.1   1   0   0   1   1   1   0 D134920_003931
D134920_000949-T1    -          SLA2                 -               0.49    6.6  16.8      0.58    6.4  16.8   1.1   1   0   0   1   1   1   0 D134920_000949
D134920_002797-T1    -          SLA2                 -                1.6    4.9  18.0       2.5    4.3  18.0   1.2   1   0   0   1   1   1   0 D134920_002797
D134920_002522-T1    -          SLA2                 -                6.2    3.0  21.2       8.6    2.5  21.2   1.1   1   0   0   1   1   1   0 D134920_002522
D134920_004968-T1    -          SLA2                 -                6.4    2.9  11.8       9.1    2.4  11.8   1.1   1   0   0   1   1   1   0 D134920_004968
D134920_002536-T1    -          SLA2                 -                7.8    2.7  25.0        10    2.3  25.0   1.1   1   0   0   1   1   1   0 D134920_002536
D134920_004182-T1    -          SLA2                 -                8.8    2.5  15.0        11    2.2  15.0   1.1   1   0   0   1   1   1   0 D134920_004182

 Program:         hmmsearch
 Version:         3.3.2 (Nov 2020)
 Pipeline mode:   SEARCH
 Query file:      /mnt/hd/Mating_loci/n/Teixeira_et_al_2017_corrected_MAT_profile_v0.1.hmm
 Target file:     /media/ricardo/crucialx9/orthofinder_domatia_jul24/prot/Domatiomyces_catenatus_CBS134920.proteins.fa
 Option settings: hmmsearch --tblout /mnt/hd/black_yeasts/domatia/jul24/mating_loci//{Domatiomyces_catenatus_CBS134920.proteins.fa}_HMM.txt /mnt/hd/Mating_loci/n/Teixeira_et_al_2017_corrected_MAT_profile_v0.1.hmm /media/ricardo/crucialx9/orthofinder_domatia_jul24/prot/Domatiomyces_catenatus_CBS134920.proteins.fa 
 Current dir:     /media/ricardo/crucialx9/orthofinder_domatia_jul24/prot
 Date:            Mon Jul 29 11:48:55 2024
 [ok]

########################### REFERENCES #############################

Teixeira et al. 2017 doi: 10.1016/j.simyco.2017.01.001
Katoh and Standley 2013 doi: 10.1093/molbev/mst010
Paysan-Lafosse et al. 2022 10.1093/nar/gkac99
Eddy 2011 doi: 10.1371/journal.pcbi.1002195
