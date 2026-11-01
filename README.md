![Banner](banner.png)

# configcheck-ConfigurationValidator
Validates configuration files (JSON, YAML, INI) against a schema definition provided as input. Reports errors for invalid data types, missing fields, or violations of defined constraints.

## Install
`git clone https://github.com/ShadowGuard-AI/configcheck-configurationvalidator`

## Usage
`python3 main.py CONFIG_FILE SCHEMA_FILE [--format json|yaml|ini] [--log-level LEVEL]`

## Parameters
- `-h`: Show help message and exit
- `config_file`: Path to the configuration file (JSON, YAML, or INI). Required.
- `schema_file`: Path to the schema file (JSON). Required.
- `--format`: Specify the configuration file format (json, yaml, or ini). If omitted, it will be inferred from the file extension.
- `--log-level`: Set the logging level. Choices: DEBUG, INFO, WARNING, ERROR, CRITICAL. Default: INFO.

## Verified behavior
- A JSON configuration matching its schema exits 0 with "Configuration is valid."
- A JSON configuration violating its schema exits 1 with the validation failure and its location.
- INI limitation, verified by run: INI files must have section headers, and every INI value is read as a string, so a schema requiring an integer fails for INI values even when the section structure matches. Use string schemas for INI files, or JSON or YAML for typed values.

## License
See LICENSE.
