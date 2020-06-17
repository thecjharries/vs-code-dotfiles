# `vs_code_desired_extensions`

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)  [![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/) [![Check the NOTICE](https://img.shields.io/badge/Check%20the-NOTICE-420C3B.svg)](../../NOTICE)

## Input

`vs_code_desired_extensions` expects a list of strings named `vs_code_extensions_to_install` to be passed in. Each string will be passed to `code --install-extension` and is assumed to be an extension name.

`vs_code_extensions_dir` can be passed in as well. Its default is `~/.vscode/extensions` (Code's default).

## Action

The role checks if `<ext dir>/.obsolete` exists. If so, Code must be launched to resolve it. This is [a feature not a bug](https://github.com/Microsoft/vscode/issues/47164). The role will fail if it exists.

The role checks if Code is running. Because of the above feature, the role will fail if Code is running.

The role loops over `vs_code_extensions_to_install` and attempts to install each one.

## Example

```yaml
---
- hosts: localhost

  vars:
    vs_code_extensions_to_install:
      - EditorConfig.EditorConfig
      - nepaul.editorconfiggenerator

  roles:
    - role: vs_code_desired_extensions
```
