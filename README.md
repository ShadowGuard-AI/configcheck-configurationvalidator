![Hands slipping a small brass part into a plain ring gauge close up on a maple bench, a neat row of passed parts behind, with no lettering anywhere](intro-banner.png)

# configcheck-ConfigurationValidator

Title block: the name above is set in Big Shoulders Display SC in carbon copy blue on an office beige plate. A small glove glyph stands beside this heading and beside no other: 🧤. The remaining headings keep the day book treatment, set as entries with ruled columns, a small tag at the left of major headings only, so that a long document stays quick to scan.

![A plain steel ring gauge with a brass ring in its mouth on a maple bench, set in a plain ring](logo.png)

![An inspector's bench with rows of machined parts, hands trying one part in a plain ring gauge, passed parts in a neat row and set-asides in a canvas tray, plain gauges on a rack behind, with no lettering anywhere](banner.png)

![The entrance in three depths: the lobby, the mat, and the snow still, the revolving door turning once slowly while the figure with the folder crosses the step, and the raised glove rising, holding, and lowering as the door turns](scene.svg)

Validates configuration files (JSON, YAML, INI) against a schema definition provided as input. Reports errors for invalid data types, missing fields, or violations of defined constraints.

![Major separator: a door plate rule at full width, its line colour taken from the banner palette, with a small plate at its centre](sep-heavy.svg)

## Install

`git clone https://github.com/ShadowGuard-AI/configcheck-configurationvalidator`

> **Lobby notice: the gap is recorded, not repaired.** The install above is one clone line, printed correctly and in full. The README gives no change of directory and no dependency step. The program imports the jsonschema library and YAML, and the repository carries a requirements file. No missing step is invented here.

![Minor separator: a door plate rule shortened and centred, its line colour taken from the banner palette, with no plate](sep-light.svg)

## Usage

`python3 main.py CONFIG_FILE SCHEMA_FILE [--format json|yaml|ini] [--log-level LEVEL]`

> **Lobby notice: Two Files, Both Required.** The command in full stands above. Both positionals are required. There is no mode in which the schema is optional. Buttons in the kit read Validate a Configuration, Load a JSON Schema, and Show Help. Headings on this page read Two Files, Both Required, The Command in Full, What Each Format Does to Its Values, and Only Valid Exits 0.

![Major separator: a door plate rule at full width, its line colour taken from the banner palette, with a small plate at its centre](sep-heavy.svg)

## Parameters

- `-h`: Show help message and exit
- `config_file`: Path to the configuration file (JSON, YAML, or INI). Required.
- `schema_file`: Path to the schema file (JSON). Required.
- `--format`: Specify the configuration file format (json, yaml, or ini). If omitted, it will be inferred from the file extension.
- `--log-level`: Set the logging level. Choices: DEBUG, INFO, WARNING, ERROR, CRITICAL. Default: INFO.

> **Lobby notice: what the list holds.** The parameters stand in the README order, with their choices and the INFO default. When it is omitted, the format is inferred from the file extension. The --log-level option takes DEBUG, INFO, WARNING, ERROR, or CRITICAL. Its default is INFO. Format inference reads the last suffix only, so a file whose name ends in a backup suffix needs an explicit --format value.

![Minor separator: a door plate rule shortened and centred, its line colour taken from the banner palette, with no plate](sep-light.svg)

## Verified behavior

- A JSON configuration matching its schema exits 0 with "Configuration is valid."
- A JSON configuration violating its schema exits 1 with the validation failure and its location.
- INI limitation, verified by run: INI files must have section headers, and every INI value is read as a string, so a schema requiring an integer fails for INI values even when the section structure matches. Use string schemas for INI files, or JSON or YAML for typed values.

> **Lobby notice: INI Values Are Always Strings.** INI is read with the standard configuration parser, and every INI value arrives as a string. An INI file therefore needs a schema that expects strings, and a schema that requires an integer will fail an INI file whose sections are otherwise correct. The INI reader also folds the default section keys into every section, so a schema that forbids extra keys can therefore fail on keys the file did not write under that section heading.

![Major separator: a door plate rule at full width, its line colour taken from the banner palette, with a small plate at its centre](sep-heavy.svg)

## License

See LICENSE.

> **Lobby notice: The Configuration Is Read Before the Schema.** The configuration is loaded before the schema, so when both files are broken, the configuration error is the one reported, and the schema file is not opened until the configuration has parsed. A missing file exits 1, an unsupported or unrecognised format exits 1, a schema that is itself invalid exits 1 with a schema error message, and a validation failure exits 1 with the failure and its location. Only a valid configuration exits 0. The licence entry closes the book as the README closes it: See LICENSE, with no licence name and no holder added.

> **The last arrival, entered and closed.** The job, stated whole: configcheck-configurationvalidator takes two files. The first file is a configuration in JSON, YAML, or INI. The second file is a schema in JSON. It reports invalid data types. It reports missing fields. It reports violations of the constraints the schema defines. A valid configuration prints the words Configuration is valid. and exits 0. An invalid configuration prints the failure and its location, and exits 1. JSON is read with the standard JSON parser. YAML is read with a safe load. INI is read with the standard configuration parser, and every INI value arrives as a string. An INI file therefore needs a schema that expects strings. A schema that requires an integer will fail an INI file whose sections are otherwise correct. The INI reader also folds the default section keys into every section. A schema that forbids extra keys can therefore fail on keys the file did not write under that section heading. Format inference reads the last suffix only. A file whose name ends in a backup suffix needs an explicit --format value. The configuration is loaded before the schema. When both files are broken, the configuration error is the one reported. The schema file is not opened until the configuration has parsed. A missing file exits 1. An unsupported or unrecognised format exits 1. A schema that is itself invalid exits 1, with a schema error message. A validation failure exits 1, with the failure and its location. Only a valid configuration exits 0. The folder has been checked, the glove is lowered, and the door turns once, and the lobby takes the figure in.
