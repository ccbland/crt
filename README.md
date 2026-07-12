# CRISPR Recognition Tool

The CRISPR Recognition Tool (CRT) is software for detecting clustered regularly interspaced palindromic repeats in single sequence FASTA files. This repository includes both the graphical user interface (GUI) version and the command-line interface (CLI) version.

**Requirements:** Java 8 or later. If you don't already have Java installed, download it from [java.com/download](https://www.java.com/download) — if you plan to build from source, you'll need a JDK (Java Development Kit) instead, e.g. from [Adoptium's releases page](https://adoptium.net/temurin/releases/).

---

## Graphical User Interface

### Run the GUI

Double-click `CRT-GUI.jar`.

> The first time you double-click `CRT-GUI.jar`, your OS may warn about an unrecognized app or ask how to open it. Right-click the file, choose **Open** (or **Open with → Java**), and confirm. You'll only need to do this once — after that, double-clicking works normally.

Or it can be run from the command line:

```bash
java -jar dist/CRT-GUI.jar
```

### Build and Run the GUI from Source

Compile the source files:

```bash
javac src/*.java
```

Run the GUI main class:

```bash
java -cp src CRTGUI
```

---

## Command Line Interface (CLI)

### Run the CLI

```bash
java -cp dist/CRT-CLI.jar CRTCLI [options] inputFile [outputFile]
```

Where:

- `CRTCLI` is the main class.
- `[options]` is optional. If no options are given, default values are used.
- `inputFile` is required and should be a single sequence FASTA file.
- `outputFile` is optional. If no output file is given, results are written to `a.out`.

### Examples

```bash
java -cp dist/CRT-CLI.jar CRTCLI data/ecoli.fna
```

```bash
java -cp dist/CRT-CLI.jar CRTCLI data/ecoli.fna ecoli.out
```

```bash
java -cp dist/CRT-CLI.jar CRTCLI -minNR 3 -minRL 21 data/ecoli.fna
```

### CLI Options

| Option | Description | Default |
|---|---|---|
| `-minNR` | Minimum number of repeats a CRISPR must contain | `3` |
| `-minRL` | Minimum length of a CRISPR repeated region | `19` |
| `-maxRL` | Maximum length of a CRISPR repeated region | `38` |
| `-minSL` | Minimum length of a CRISPR spacer/non-repeated region | `19` |
| `-maxSL` | Maximum length of a CRISPR spacer/non-repeated region | `48` |
| `-screen` | Print results to screen instead of a file; range `0–1` | `0` |
| `-searchWL` | Length of search window used to discover CRISPRs; range `6–9` | `8` |

### Build and Run the CLI from Source

Compile the source files:

```bash
javac src/*.java
```

Run the CLI main class:

```bash
java -cp src CRTCLI [options] inputFile [outputFile]
```

Example:

```bash
java -cp src CRTCLI data/ecoli.fna ecoli.out
```

---

### Optional: Create a Unix Alias for the CLI

To avoid typing the full command each time, you can create an alias.

For Bash:

```bash
alias crt="java -cp dist/CRT-CLI.jar CRTCLI"
```

For C shell or tcsh:

```csh
alias crt "java -cp dist/CRT-CLI.jar CRTCLI"
```

Then CRT can be run more simply:

```bash
crt data/ecoli.fna
```

```bash
crt data/ecoli.fna ecoli.out
```

```bash
crt -minNR 3 -minRL 21 data/ecoli.fna
```

To make the alias permanent, add it to your shell configuration file, such as `.bashrc`, `.zshrc`, or `.cshrc`.

---

## Contact

Questions, bug reports, and suggestions.

Email: `bland.charles@gmail.com`

---

## Citation

If you use CRT in your research, please cite:

Bland C, Ramsey TL, Sabree F, Lowe M, Brown K, Kyrpides NC, Hugenholtz P.

**CRISPR Recognition Tool (CRT): a tool for automatic detection of clustered regularly interspaced palindromic repeats.**

*BMC Bioinformatics.* 2007;8:209.
