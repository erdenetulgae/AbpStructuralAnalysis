## Introduction

Dental caries is a widespread health concern with significant consequences on nutrition and well-being. The primary agent in the formation of caries is acid-producing bacteria that occupy oral biofilms, which constitute a dense network of interactions between the oral microbiome, the salivary pellicle and its constituent proteome. Salivary α-amylase (SA) forms key interactions in the formation of the salivary pellicle, the immediate layer atop the dental surface (Scannapieco, Torres & Levine, 1993). Amylase-binding proteins (ABP) are a family of proteins that interact with SA that allow for early colonisers of the dental surface to adhere and promote the formation of oral biofilm (Nikitkova Anna E., Haase Elaine M., & Scannapieco Frank A., 2013). It has been well characterised that AbpA of _S. parasanguinis_ and its homologues bind with high affinity and specificity to SA (Liang et al., 2016). There is a gap in research for the structure of the bound complex of AbpA and SA, which may be filled in with initial guidance from protein-protein docking tools. Information provided from the docking has further implications in structure-based drug design.
## Multiple sequence alignment of AbpA

A wide range of modern bioinformatics tools allow us to find evolutionarily conserved regions of proteins that may reveal crucial residues in their binding interactions. A BLAST (Altschul et al., 1990) search found multiple variants of AbpA and close homologues present in other species. The search results were aligned using Clustal Omega (default parameters) through the EMBL-EBI Job Dispatcher (Madeira et al., 2024).  The sequence alignment of AbpA points to 5 helices as very well conserved regions with Y28 and H45 as exceptionally well conserved residues. The equivalent of H45 of _S. gordonii_ AbpA (H572MXX) is also shown to be well conserved through multiple sequence alignment (Sethi et al., 2015). Other sequence alignment programs like MAFFT (Kuraku et al., 2013) and adjustment of the size of BLAST search, and parameters of the sequence alignments consistently suggested H45 as exceptionally well conserved. This residue may provide a good reference point for the docking analysis of AbpA to SA.

### Data

- Link to .html file of Jalview image
	- [ClustalO_MSA_AbpA.html](multiple_sequence_alignment/ClustalO_MSA_AbpA.html)

---
## Docking of AbpA to SA

Structures for the complex of AbpA-SA may be useful in structure-based drug design for the treatment of dental caries, however it has not been openly resolved. My analysis of the docking of AbpA to SA was driven by 2 separate approaches. My first approach assumed that exceptionally well conserved residues from the multiple sequence alignment are directly involved in the binding interactions. My second approach was based on experimentally documented residues that are suggested to be involved in binding interactions to SA.

A previous mutation based analysis on the secondary binding sites of SA probed the residues involved directly in SA binding to bacteria and AbpA (Ragunath et al., 2008). These results reveal residues W284, Y276 and W203 as a critical binding site for the interaction of AbpA to SA. The first binding site, W284 and Y276, is part of the interface of dimerised SA as visualised in figure 4. This may suggest that the binding of AbpA is primarily to the dimerised form of SA. Another study on the binding of _Fusobacterium_ showed more binding to the dimeric form than the monomeric form of amylase (Zulfiqar et al., 2013), however more research is needed to confirm if _Fusobacterium_ binding protein is similar to AbpA.

In the first run, the highly conserved residue H45 of AbpA was input to HADDOCK (van Zundert et al., 2016) as directly involved in the binding interactions of AbpA and HSA. On the receptor side, the critical residue W203 of SA was used to anchor the docking of AbpA to SA in HADDOCK. W284 and Y276 were not specified as actively participating in the binding.

interactions with the hindsight that they are direct participants in the dimerization of SA, not conclusively AbpA binding; it is worth noting that these buried residues were not completely ruled out of docking simulations. The output provided 10 clusters of binding conformations with comparable binding scores and energies.

Liang et al. (2016) studied the residues directly involved in the binding of AbpA through NMR titration and found that the residues K26/27, Y121/Y122, V106/L107 reside in the interface of the AbpA-SA complex. These residues were input in the second run instead of the highly conserved residues from the multiple sequence alignment. The results showed 2 new clusters with more favourable HADDOCK scores than the first run (Clusters 1 and 2). The scores and binding energies were more variable compared to the first run, likely due to the input of more anchoring points.

### Parameters

Parameters of multiple sequence alignment based docking:
- Receptor: [1smd](HADDOCK_docking/1smd_ligands_removed.pdb)
	- Modified to remove ligands
	- Active residues: W203
- Ligand: [2nd4](HADDOCK_docking/2nd4.pdb)
	- Active residues: H45
- Link to job: [HADDOCK job 1](https://rascar.science.uu.nl/haddock2.4/result/6983437677/402746-HSA-ABP)

Parameters of NMR titration based docking:
- Receptor: [1smd](HADDOCK_docking/1smd_ligands_removed.pdb)
	- Modified to remove ligands
	- Active residues: W203
- Ligand: [2nd4](HADDOCK_docking/2nd4.pdb)
	- Active residues: K26/27, Y121/122, V106, L107
- Link to job: [HADDOCK job 3](https://rascar.science.uu.nl/haddock2.4/result/6983437677/403219-HSA_ABP3)
--- 
## Hot segments in the binding interactions

Further analysis on the docking structures were performed to find which residues, or which stretch of residues were responsible for the binding interactions. The top model from each 10 clusters was submitted to the Peptiderive protocol (Sedan et al., 2016) accessed through ROSIE (Lyskov et al., 2013). The protocol outputs hot segments, which point to stretches of hot spot residues that contribute most significantly to the free energy release in protein-protein interactions. The algorithm searches

The hot segments derived from the top 10 docking clusters in each run are visualised in the following figures. The first run shows very similar docking behaviour between the clusters. The second runs output showed less consensus among clusters.

### Data

Peptiderive (Sedan et al., 2016) jobs for MSA based docking (ranked by HADDOCK score)
- [Cluster 2.1](https://rosie.rosettacommons.org/peptiderive/viewjob/121944)
- [Cluser 3.1](https://rosie.rosettacommons.org/peptiderive/viewjob/121945)
- [Cluster 6.1](https://rosie.rosettacommons.org/peptiderive/viewjob/121946)
- [Cluster 2.1](https://rosie.rosettacommons.org/peptiderive/viewjob/121947)
- [Cluster 12.1](https://rosie.rosettacommons.org/peptiderive/viewjob/121948)
- [Cluster 11.1](https://rosie.rosettacommons.org/peptiderive/viewjob/121949)
- [Cluster 10.1](https://rosie.rosettacommons.org/peptiderive/viewjob/121950)
- [Cluster 8.1](https://rosie.rosettacommons.org/peptiderive/viewjob/121951)
- [Cluster 5.1](https://rosie.rosettacommons.org/peptiderive/viewjob/121952)
- [Cluster 4.1](https://rosie.rosettacommons.org/peptiderive/viewjob/121953)

Peptiderive (Sedan et al., 2016) jobs for NMR titration based docking (ranked by HADDOCK score)
- [Cluster 2.1](https://rosie.rosettacommons.org/viewjob/122006)
- [Cluster 1.1](https://rosie.rosettacommons.org/viewjob/122005)
- [Cluster 4.1](https://rosie.rosettacommons.org/viewjob/122008)
- [Cluster 5.1](https://rosie.rosettacommons.org/viewjob/122009)
- [Cluster 3.1](https://rosie.rosettacommons.org/viewjob/122007)
- [Cluster 7.1](https://rosie.rosettacommons.org/viewjob/122011)
- [Cluster 6.1](https://rosie.rosettacommons.org/viewjob/122010)

---
## References

Altschul, S.F., Gish, W., Miller, W., Myers, E.W. & Lipman, D.J. (1990) Basic local alignment search tool. _Journal of Molecular Biology_. 215 (3), 403–410. doi:[10.1016/S0022-2836(05)80360-2](https://doi.org/10.1016/S0022-2836(05)80360-2).

Kuraku, S., Zmasek, C.M., Nishimura, O. & Katoh, K. (2013) aLeaves facilitates on-demand exploration of metazoan gene family trees on MAFFT sequence alignment server with enhanced interactivity. _Nucleic Acids Research_. 41 (Web Server issue), W22-28. doi:[10.1093/nar/gkt389](https://doi.org/10.1093/nar/gkt389).

Liang, X., Liu, B., Zhu, F., Scannapieco, F.A., Haase, E.M., Matthews, S. & Wu, H. (2016) A distinct sortase SrtB anchors and processes a streptococcal adhesin AbpA with a novel structural property. _Scientific Reports_. 6 (1), 30966. doi:[10.1038/srep30966](https://doi.org/10.1038/srep30966).

Madeira, F., Madhusoodanan, N., Lee, J., Eusebi, A., Niewielska, A., Tivey, A.R.N., Lopez, R. & Butcher, S. (2024) The EMBL-EBI Job Dispatcher sequence analysis tools framework in 2024. _Nucleic acids research_. 52 (W1), W521–W525. doi:[10.1093/nar/gkae241](https://doi.org/10.1093/nar/gkae241).

Nikitkova Anna E., Haase Elaine M., & Scannapieco Frank A. (2013) Taking the Starch out of Oral Biofilm Formation: Molecular Basis and Functional Significance of Salivary α-Amylase Binding to Oral Streptococci. _Applied and Environmental Microbiology_. 79 (2), 416–423. doi:[10.1128/AEM.02581-12](https://doi.org/10.1128/AEM.02581-12).

Scannapieco, F.A., Torres, G. & Levine, M.J. (1993) Salivary alpha-amylase: role in dental plaque and caries formation. _Critical Reviews in Oral Biology and Medicine: An Official Publication of the American Association of Oral Biologists_. 4 (3–4), 301–307. doi:[10.1177/10454411930040030701](https://doi.org/10.1177/10454411930040030701).

Sedan, Y., Marcu, O., Lyskov, S. & Schueler-Furman, O. (2016) Peptiderive server: derive peptide inhibitors from protein–protein interactions. _Nucleic Acids Research_. 44 (W1), W536–W541. doi:[10.1093/nar/gkw385](https://doi.org/10.1093/nar/gkw385).

Sethi, A., Mohanty, B., Ramasubbu, N. & Gooley, P.R. (2015) Structure of amylase-binding protein A of Streptococcus gordonii: a potential receptor for human salivary α-amylase enzyme. _Protein Science: A Publication of the Protein Society_. 24 (6), 1013–1018. doi:[10.1002/pro.2671](https://doi.org/10.1002/pro.2671).

van Zundert, G.C.P., Rodrigues, J.P.G.L.M., Trellet, M., Schmitz, C., Kastritis, P.L., Karaca, E., Melquiond, A.S.J., van Dijk, M., de Vries, S.J. & Bonvin, A.M.J.J. (2016) The HADDOCK2.2 Web Server: User-Friendly Integrative Modeling of Biomolecular Complexes. _Journal of Molecular Biology_. 428 (4), 720–725. doi:[10.1016/j.jmb.2015.09.014](https://doi.org/10.1016/j.jmb.2015.09.014).

