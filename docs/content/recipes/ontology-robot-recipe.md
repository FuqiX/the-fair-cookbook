# Table of Contents
1. [Main FAIRification Objectives](#Main%20FAIRification%20Objectives)
2. [Graphical Overview of the FAIRification Recipe Objectives](#Graphical%20Overview%20of%20the%20FAIRification%20Recipe%20Objectives)
3. [FAIRification Objectives, Inputs and Outputs](#FAIRification%20Objectives,%20Inputs%20and%20Outputs)
4. [Capability & Maturity Table](#Capability%20&%20Maturity%20Table)
5. [Table of Data Standards](#Table%20of%20Data%20Standards)
6. [Executable Code in Notebook](#Executable%20Code%20in%20Notebook)
7. [How to create workflow figures](#How%20to%20create%20workflow%20figures)
8. [License](#License)

---

## Main Objectives

The main purpose of this recipe is:

> Building an application ontology from source ontologies using ROBOT via a sustainable dynamic pipeline to allow seamless integration of source ontology updates. This will constitute a cornerstone for establishing and maintaining tailor made application ontologies that can be utilized for structuring and searching dedicated data sets.

### Competency questions

General Questions

- How to identify relevant public domain ontologies suiting our needs? (Might be out of scope for ROBOT)
- How to establish an ontology covering all terms that are included in the actual data to be represented?
- How to merge the internal ontology with publicly available ontologies?
- How to remove terms from the resulting ontology that are not needed?
- How to guarantee consistency of the final ontology?
- How to identify differences in comparison to a previous version of the resulting ontology?

Questions without specifying compounds or genes

- Identify all data generated from tissues taken from patients suffering from a specific disease.
- Identify all data generated from a specific tissues obtained from mouse models that are related to a specific disease.
- Identify all data generated from lung tissue taken from patients suffering from a lung disease that is not related to oncology.
- Identify all data generated from primary cells whose origin is the lung.
- Identify all data generated from celllines whose origin is the lung.

Questions including single genes or gene sets

- What is the expression of PPARg / growths factors in lung tissue from IPF patients?
- What is the expression of PPARg / growths factors in primary cells obtained from lung tissue from healthy subjects?
- What is the expression of PPARg / growths factors in all available tissues obtained from healthy subjects? 

Questions including compound or treatment information

- Identify all data generated from primary cells treated with a kinase inhibitor.
- Identify all data from patients treated with a specific medication.
- Identify all data generated from cells / celllines that have been treated with compounds targeting a member of a specific pathway.
- What is the expression of PPARg in lung tissue upon treatment with a specific compound in patients suffering from a specific diseas
___

## Ingredients

Tools
- Ontology development kit (https://github.com/INCATools/ontology-development-kit) (comes with ROBOT included)
or
- ROBOT (http://robot.obolibrary.org/)
- Protégé/other ontology editor



## Step by step process

### Step 1: Select appropriate source ontologies & branches

reference other recipe 

### Step 2: Build the upper level "umbrella" ontology 

tools: protege/other ontology editor
considerations: ontology base URI/namespace

### Step 3: Extract ontology modules from source ontologies

discuss different approaches for extraction (TOP/BOT/MIREOT) with guidance of which to use

pros & cons of different methods

#### Module extraction - using manual text lists

#### Module extraction - using SPARQL

### Step 4: Merge extracted modules under the umbrella



### Step 5: Post-merge modifications
eg removing extraneous classes



## Graphical Overview of the FAIRification Recipe Objectives

<!-- TO DO -->

<div class="mermaid">
graph LR;
    A[Data Acquisition] -->B(Raw Data)
    B --> C{FAIR by Design}
    C -->|Yes| D[Standard Compliant Data]
    C -->|No| E[Vendor locked Data]
</div>

___

## Capability & Maturity Table

<!-- TO DO -->

| Capability  | Initial Maturity Level | Final Maturity Level  |
| :------------- | :------------- | :------------- |
| Interoperability | minimal | repeatable |

----

## FAIRification Objectives, Inputs and Outputs

| Actions.Objectives.Tasks  | Input | Output  |
| :------------- | :------------- | :------------- |
| [validation](http://edamontology.org/operation_2428)  | [Structure Data File (SDF)](https://fairsharing.org/FAIRsharing.ew26v7)  | [report](http://edamontology.org/data_2048)  |
| [calculation](http://edamontology.org/operation_3438)  | [Structure Data File (SDF)](https://fairsharing.org/FAIRsharing.ew26v7) | [InChi](https://fairsharing.org/FAIRsharing.ddk9t9) |
| [calculation](http://edamontology.org/operation_3438)  | [Structure Data File (SDF)](https://fairsharing.org/FAIRsharing.ew26v7)  | [SMILES](https://fairsharing.org/FAIRsharing.qv4b3c)  |
| [text annotation](http://edamontology.org/operation_3778)  | [Human Phenotype Ontology](https://fairsharing.org/FAIRsharing.kbtt7f)  | [annotated text](http://edamontology.org/data_3779)  |


## Table of Data Standards

| Data Formats  | Terminologies | Models  |
| :------------- | :------------- | :------------- |
| [FASTQ](https://fairsharing.org/FAIRsharing.r2ts5t)  | [LOINC](https://fairsharing.org/FAIRsharing.2mk2zb)  | [SRA XML](https://fairsharing.org/FAIRsharing.q72e3w)  |
| [DICOM](https://fairsharing.org/FAIRsharing.b7z8by)  | [Human Phenotype Ontology](https://fairsharing.org/FAIRsharing.kbtt7f)  | [OMOP](https://fairsharing.org/FAIRsharing.qk984b)  |

___


## Executable Code in Notebook


```python
import isatools
import json
import pandas as pd 
import holoview
```

___

## How to create workflow figures

one may use the following **[mermaid](https://mermaid-js.github.io/mermaid/#/)** syntax:

```
graph LR;
    A[Data Acquisition] -->B(Raw Data)
    B --> C{FAIR by Design}
    C -->|Yes| D[Standard Compliant Data]
    C -->|No| E[Vendor locked Data]
```

<div class="mermaid">
graph LR;
    A["input data"]-->B["conversion to open format"];
    A["input data"]-->C["automatic annotation"];
    B["conversion to open format"]-->D(("output data"));
    C["automatic annotation"]-->D(("output data"));  

    style A fill:#FF5733,stroke:#333,stroke-width:2px
    style D fill:#0A749B,stroke:#333,stroke-width:2px
</div>

___



## Authors:

| Name | Affiliation  | orcid | CrediT role  |
| :------------- | :------------- | :------------- |:------------- |
| Danielle Welter |  LCSB, University of Luxembourg| [0000-0003-1058-2668](https://orcid.org/0000-0003-1058-2668) | Writing - Original Draft |

___


## License:

<a href="https://creativecommons.org/licenses/by/4.0/"><img src="https://mirrors.creativecommons.org/presskit/buttons/80x15/png/by-sa.png" height="20"/></a>
