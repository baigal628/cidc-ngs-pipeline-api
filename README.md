# CIDC NGS Pipeline API

![Continuous Integration](https://github.com/CIMAC-CIDC/cidc-ngs-pipeline-api/workflows/Continuous%20Integration/badge.svg?branch=master)  [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) 

### Overview
This repository serves as an interface between the CIDC and Bioinformatics teams to determine specifications and documentation related to NGS pipelines.

Repository structure:
```
.
├── README.md
├── cidc_ngs_pipeline_api
│   ├── output_API.schema.json
│   ├── rna
│   │   ├── rna.md
│   │   ├── rna_config.schema.json
│   │   ├── rna_output_API.json
│   │   └── imgs
│   |       └── RIMA.png
│   ├── chips
│   │   ├── chips.md
│   │   ├── chips_output_API.json
│   │   └── imgs
│   |       └── chips.png
│   ├── tcr
│   │   ├── tcr.md
│   │   └── imgs
│   |       └── TCRseq.png
│   └── wes
│       ├── wes.md
│       ├── wes_config.schema.json
│       ├── wes_output_API.json
│       ├── wes_tumor_only_output_API.json
│       ├── wes_output_API.py
│       └── imgs
│          └── wes.png
├── tests
│   └── test_apis.py
├── requirements.dev.txt
├── requirements.txt
├── setup.cfg
├── setup.py
└── .github
    └── workflows
       └── ci.yml
    
```

## cidc_ngs_pipeline_api module

* The `output_API.schema.json` file defines the schema structure:
    - `filter_group`: Filter under which the file would appear during faceted search. It is the GCS-URI top-level hierarchy
    - `file_path_template`: Local file path used for CLI upload
    - `short_description`: Description to appear on hovering over file name in file browser
    - `long_description`: Longer description to appear on file documentation page
    - `file_purpose`: Assigns a tag to show up in a particular file-browser view configuration. Permissible values: `Source view`, `Analysis view`, `Clinical view`, `Miscellaneous`
    
* Within the directory for each assay:
  
    * The defined schema is used to structure information about pipeline-related files in the respective  `< assay >_output_API.json`.

    * Information related to YAML configurations (which are generated by the CIDC and configured with CIMAC IDs to run the pipelines), are described in the respective `< assay > config.schema.json`.

    * Documentation related to each pipeline is in the respective `< assay > .md`.

### Developer Setup

Install necessary dependencies.

```bash
pip install -r requirements.dev.txt
```

Install and configure pre-commit hooks.

```bash
pre-commit install
```
