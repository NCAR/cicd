# Welcome to the NCAR CI/CD Documentation repository!


[![Documentation Status](https://readthedocs.org/projects/ncar-cicd/badge/?version=latest)](https://ncar-cicd.readthedocs.io/en/latest/?badge=latest)


## Overview

Our CI workflows are designed as starting points and templates for NCAR scientific software projects. These workflows provide a foundation that teams can adapt and expand upon for their specific needs. The system supports multiple compiler configurations, MPI implementations, GPU acceleration options, and architecture targets to help establish basic CI/CD practices.

### Supported Build Configurations

The CI/CD system supports a wide range of build configurations:

- **Compilers**: NVHPC, Intel OneAPI, AMD AOCC, GCC (versions 12, 13, 14), Clang
- **MPI**: OpenMPI, MPICH
- **GPU**: CUDA support, CPU-only builds
- **Architecture**: x86_64

### Key Features

- **Matrix-based testing**: Basic testing framework across multiple configuration combinations
- **Build validation**: Automated compilation and linking verification
- **Runtime testing**: Small-scale test case execution with single vs. multiple rank comparisons
- **Flexible I/O options**: Support for different I/O libraries (PIO, SMIOL)
- **Acceleration support**: OpenACC integration for GPU-enabled builds

## Implementation Approach

The CI workflows are built upon proven container testing methods that have been successfully adapted for NCAR applications. These templates provide:

1. **Starting foundation**: Based on established container testing workflows
2. **Template structure**: Basic build scripts and configurations that can be customized for each codebase
3. **Extensible framework**: From basic matrix testing to more focused developer workflows as projects grow
4. **Adaptation ready**: Easy starting point for new applications to implement basic CI/CD practices

## Getting Started

To implement CI/CD workflows for your application, you'll need to set up three key files in your repository's `.github/workflows` directory:

### Required Files to get started

1. **Workflow YAML file** (e.g., `smoketest.yml`)
   - Defines the CI/CD pipeline and matrix configurations
   - Sets up environment variables and build steps
   - Configures compiler, MPI, GPU, and architecture options

2. **Build script** (e.g., `build_mpas.sh`)
   - Contains the application-specific build logic
   - Handles compiler flags and build options
   - Manages I/O library selection (PIO vs SMIOL) and acceleration flags (OpenACC)

3. **Build configuration** (`build_common.cfg`)
   - Provides common environment setup and compiler logic
   - Contains shared build configurations and dependencies
   - Ensures consistent environment across different build targets

### Implementation Steps

1. Copy these three files from an existing workflow template to your project's `.github/workflows` directory
2. Customize the workflow YAML for your application's specific needs
3. Modify the build script to handle your application's build requirements
4. Adjust the build configuration file as needed for your environment
5. Commit the files to your repository to enable the "Run workflow" button

For detailed examples and step-by-step instructions, please visit the [getting started guide](getting-started.md).


## Getting Started 🛠️

This documentation site is built using the NCAR MkDocs template. For information on how to contribute to this documentation, please visit the [getting started guide](getting-started.md).

For examples of other NCAR documentation sites, see [NCAR HPC Documentation](https://ncar-hpc-docs.readthedocs.io/en/latest/).


## License

This material is licensed under Creative Commons Attribution ShareAlike 4.0 ([CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/)).  You are free to:

- **Share** — copy and redistribute the material in any medium or format for any purpose, even commercially.

- **Adapt** — remix, transform, and build upon the material for any purpose, even commercially.


Under the following terms:

- **Attribution** - You must give appropriate credit , provide a link to the license, and indicate if changes were made . You may do so in any reasonable manner, but not in any way that suggests the licensor endorses you or your use.

- **ShareAlike** - If you remix, transform, or build upon the material, you must distribute your contributions under the same license as the original.
No additional restrictions - You may not apply legal terms or technological measures that legally restrict others from doing anything the license permits.

See [here](https://creativecommons.org/licenses/by-sa/4.0/legalcode.en) for full details.
