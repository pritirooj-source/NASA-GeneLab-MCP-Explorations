Find DE genes that overlap with DM regions (promoter hypermethylation reducing expression) for OSD-48

Here's the expression-methylation coupling analysis for OSD-48 (liver, Space Flight vs. Ground Control, Carcass), looking specifically at **promoter** methylation:

Out of 184 DE genes and 955 DM genes, only **8 genes** show both signals, split across four directional categories:

**Classical epigenetic silencing (promoter hypermethylation → downregulation)** — the pattern you're specifically interested in:
- ***Cux2*** (log2FC −2.06, meth diff +14.5%) — the strongest hit in this category
- ***Pcsk4*** (log2FC −1.21, meth diff +31.6%) — notably the largest methylation shift of any gene here, and this same *Pcsk4* promoter region showed up as a top hypermethylated hit in our earlier standalone DMR search
- ***Tns2*** (log2FC −1.00, meth diff +6.8%)

These 3 genes fit the textbook model where added methylation in the promoter is suppressing transcription.

The other categories (for context, not the classical pattern):
- **Up + hypermethylated** (non-canonical, e.g. gene-body-like activation): *Cyp26a1*, *Dnmt3b*, *Loxl4*
- **Down + hypomethylated** (non-canonical — loss of methylation but still downregulated, so something else is driving it): *Adam11*, *Rnf186*

Given how small this overlap is (8 of 184 DE genes), most of the spaceflight transcriptional response in liver doesn't appear to be directly explained by promoter methylation changes — other regulatory mechanisms are likely at play for the bulk of the DE genes.