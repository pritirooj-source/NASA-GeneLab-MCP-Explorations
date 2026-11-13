Visualize the KG schema using a Mermaid class diagram

Now let me get the relationship edge properties (for the edges with data like log2fc, adj_p_value).

Now I'll build the draft diagram and run it through the required cleaning step.

Now saving the cleaned diagram as a `.mermaid` file and presenting it.

Here's the GeneLab KG schema as a Mermaid class diagram:

```mermaid
classDiagram
direction TB

class Mission {
    string identifier
    string name
    string flight_program
    string space_program
    date start_date
    date end_date
}

class Study {
    string identifier
    string name
    string project_title
    string description
    string project_type
    string organism
    string taxonomy
    string host_organism
    string host_strain
    string host_taxonomy
}

class Assay {
    string identifier
    string name
    string technology
    string measurement
    string differential_analysis_method
    list factors_1
    list factors_2
    string material_1
    string material_2
    string material_id_1
    string material_id_2
    string material_name_1
    string material_name_2
    string factor_space_1
    string factor_space_2
}

class MGene {
    string identifier
    string symbol
    string name
    string organism
    string taxonomy
}

class Gene {
    string identifier
}

class MethylationRegion {
    string identifier
    string name
    string chromosome
    int start
    int end
    boolean in_promoter
    boolean in_exon
    boolean in_intron
    int dist_to_feature
}

class Organism {
    string identifier
    string name
}

class CellType {
    string identifier
}

class Anatomy {
    string identifier
}

class MEASURED_DIFFERENTIAL_EXPRESSION_ASmMG {
    float log2fc
    float adj_p_value
    float group_mean_1
    float group_stdev_1
    float group_mean_2
    float group_stdev_2
}

class MEASURED_DIFFERENTIAL_METHYLATION_ASmMR {
    float methylation_diff
    float q_value
    float group_mean_1
    float group_stdev_1
    float group_mean_2
    float group_stdev_2
}

class MEASURED_DIFFERENTIAL_ABUNDANCE_ASmO {
    float log2fc
    float lnfc
    float adj_p_value
    float q_value
    float group_mean_1
    float group_stdev_1
    float group_mean_2
    float group_stdev_2
}

Mission --> Study : CONDUCTED_MIcS
Study --> Assay : PERFORMED_SpAS
Assay --> MEASURED_DIFFERENTIAL_EXPRESSION_ASmMG
MEASURED_DIFFERENTIAL_EXPRESSION_ASmMG --> MGene
Assay --> MEASURED_DIFFERENTIAL_METHYLATION_ASmMR
MEASURED_DIFFERENTIAL_METHYLATION_ASmMR --> MethylationRegion
Assay --> MEASURED_DIFFERENTIAL_ABUNDANCE_ASmO
MEASURED_DIFFERENTIAL_ABUNDANCE_ASmO --> Organism
Assay --> CellType : INVESTIGATED_ASiCT
Assay --> Anatomy : INVESTIGATED_ASiA
MGene --> MethylationRegion : METHYLATED_IN_MGmMR
MGene --> Gene : IS_ORTHOLOG_MGiG
```

This maps the full backbone we've been querying: **Mission → Study → Assay**, with Assay branching out to three measurement types (expression → MGene, methylation → MethylationRegion, abundance → Organism) via intermediary relationship classes that carry the statistics (log2fc, adj_p_value, q_value, etc.). MGene also links to MethylationRegion directly (for the promoter-overlap analyses we ran on OSD-48) and to Gene via ortholog mapping. The **genelab-kg-schema** file has the raw diagram code if you want to render or edit it elsewhere.