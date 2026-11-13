Get study information and available assays for OSD-267

## OSD-267: Veggie Hardware Validation Test (VEG-01)

**Study type:** Spaceflight study examining microbiota on red romaine lettuce (*Lactuca sativa* cv. 'Outredgeous') grown aboard the ISS Veggie plant growth chambers vs. ground controls.

- **Mission:** SpaceX-3
- **Organism studied:** Microbiota (not the plant itself — this is a microbiome study)
- **Host:** Lactuca sativa, Outredgeous strain

**Data available:** This study has no RNA-Seq or methylation data — it's purely microbial community profiling, with **24 total assays** split evenly:
- **12 assays**: 16S amplicon sequencing (bacterial community)
- **12 assays**: ITS amplicon sequencing (fungal community)

Each marker (16S/ITS) has 6 comparisons run through both DESeq2 and ANCOM-BC (12 assays each), covering combinations of:
- Space Flight vs. Ground Control (same tissue)
- Root vs. Leaf (same condition)
- Cross comparisons (e.g., Space Flight root vs. Ground Control leaf)

So for a question like "what changed between space flight and ground control," you'd want the **root-vs-root** or **leaf-vs-leaf** same-tissue comparisons (e.g., `OSD-267-eefc7edb4dfa19f3698f4d6c6c9b2406` for 16S root, DESeq2).

Want me to pull differentially abundant organisms for a specific comparison (e.g., Space Flight vs. Ground Control in roots or leaves, 16S or ITS)?

Find differentially methylated regions in the promoter for OSD-48

Since OSD-48 has two replicate methylKit assays for the Space Flight vs. Ground Control (Carcass) comparison, I'll pool both for the combined evidence.

Here are the differentially methylated **promoter** regions for OSD-48 (Space Flight vs. Ground Control, liver, Carcass), pooled across the two replicate methylKit assays (q ≤ 0.05):

**Hypermethylated (576 total passing the promoter filter) — top hits:**
*Magel2* shows the largest shift (+58.9 percentage points), followed by *Nr4a3* (+45.8), *Mta1* (+37.2), and *Epha2* (+36.5). Notably, *Hmga1* (+29.9) is hypermethylated in its promoter here, which is interesting in light of *Hmga1b* being strongly *upregulated* in the OSD-105 muscle expression data we looked at earlier — a different tissue/study, but worth noting if you're tracking that gene family.

**Hypomethylated (442 total) — top hits:**
*Dusp28* dropped by -48.6 points, with *Twsg1* (-37.4), *Tmc8* (-34.9), and *C2* (complement C2, -33.7) also strongly hypomethylated.

Would you like me to:
- Pull the full CSV (all 576 hyper / 442 hypo rows)
- Check whether any of these promoter-methylated genes also show differential expression (classical epigenetic silencing analysis)
- Generate a volcano plot for the methylation data