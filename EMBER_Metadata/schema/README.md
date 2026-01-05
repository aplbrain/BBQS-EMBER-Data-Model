### Getting Started
This environment is used to validate EMBER project metadata against the BBQS participants data using LinkML. The schema is derived from EMBER-DANDI metadata, and participant metadata is collected from each BBQS team as YAML files.

The steps below walk through setting up a clean environment and installing the LinkML tools needed to validate metadata and generate schemas. Using an isolated environment helps avoid dependency conflicts with other Python projects.

LinkML does not support Python 3.7 or earlier. Use Python 3.10 or newer to avoid compatibility issues.
Create and activate a environment:
```
conda create -n linkmlenv python=3.10 -y
```
```
conda activate linkmlenv
```

## Install LinkML:
Minimal install:
```
pip install linkml-cli
```
If that does not work, install the full suite:

```
pip install "linkml[cli]"
```
Or explicitly:
```
pip install linkml linkml-runtime linkml-dataops linkml-cli
```
Test that the CLI works:
```
linkml-validate --help
```
If the help menu prints, your installation is correct.

## Validate Schema
The LinkML schema is the source of truth for EMBER project metadata. Field requirements, allowed values, and identifier patterns are enforced directly by the schema. Some fields allow empty strings to support cases where identifiers are assigned later (for example, DOIs). When values are present, the expected format is still enforced by validation.

Validate a metadata file against the schema:
```
linkml-validate -s ember_project_metadata.yaml <award identifier number>.yaml
```
To validate all projects at the same time against the schema:
```
linkml-validate \
  -s EMBER_Metadata/schema/ember_project_metadata.yaml \
  EMBER_Metadata/data/*.yaml
```

## Generate a full JSON Schema using the generator:
```
python -m linkml.generators.jsonschemagen \
  --top-class EmberProject \
  EMBER_Metadata/schema/ember_project_metadata.yaml \
  > EMBER_Metadata/schema/ember_project_metadata.schema.json
```
Check that the file was created:
```
ls -lh ember_project_metadata.schema.json
```