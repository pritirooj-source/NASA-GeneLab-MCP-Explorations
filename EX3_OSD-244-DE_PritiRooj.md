Create a Venn diagram comparing differentially expressed genes across assays in OSD-48

I now have two RNA-Seq expression assays for OSD-48: **Carcass** (Space Flight vs Ground Control) and **Upon euthanasia** (Space Flight vs Ground Control). Creating a Venn diagram comparing DEGs across these two.

Here's the Venn diagram comparing differentially expressed genes (|log2FC| ≥ 1.0) across OSD-48's two Space Flight vs. Ground Control liver comparisons:

**Assay 1** = Carcass timepoint, **Assay 2** = Upon euthanasia timepoint

- **Upregulated:** 112 genes in Carcass, 45 in Upon euthanasia, with only **2 genes shared** between them
- **Downregulated:** 72 genes in Carcass, 12 in Upon euthanasia, with **zero overlap**

The minimal overlap suggests the transcriptional response in liver is largely **timepoint-specific** — the genes altered immediately upon euthanasia are quite different from those altered in the carcass samples, rather than representing a shared, consistent spaceflight signature.

Want me to identify which 2 genes overlap in the upregulated set, or explore why the two timepoints diverge so much (e.g., checking if euthanasia-method stress response dominates one assay)?

Find differentially abundant organisms for OSD-267

The 16S, Space Flight vs. Ground Control (leaf) comparison is assay `OSD-267-63f37f540b5f6ade8dc6aab9e49a56ac` (DESeq2).

No organisms passed the significance threshold (adj. p ≤ 0.05) for the 16S Space Flight vs. Ground Control leaf comparison using DESeq2 — i.e., no significant differences in bacterial abundance were detected in leaf tissue between flight and ground conditions.

A couple of options to dig further:
- Check the **ANCOM-BC** version of this same comparison (`OSD-267-c706e14a4ca5ce137333f38fe9dba1e8`), since the two methods can disagree
- Loosen the significance threshold (e.g., q/adj.p ≤ 0.1) to see near-significant hits
- Try the **root** tissue comparison instead, where microbiome shifts are sometimes more pronounced

Want me to run any of these?

Find common differentially abundant organisms across assays in OSD-267

No common differentially abundant organisms between the 16S (bacterial) and ITS (fungal) root comparisons (Space Flight vs. Ground Control, DESeq2, both at adj. p ≤ 0.05) — which makes biological sense, since bacteria and fungi are entirely different organism sets with no shared taxa to overlap on in the first place. This comparison type is really more useful for checking overlap *within* the same marker (e.g., DESeq2 vs. ANCOM-BC agreement on the same 16S assay, or 16S root vs. 16S leaf).

Want me to try one of those instead — e.g., checking whether DESeq2 and ANCOM-BC agree on the 16S root comparison, or whether the same bacterial taxa shift in both root and leaf?

