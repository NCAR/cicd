# Welcome to NCAR CI/CD Documentation!

[![Documentation Status](https://readthedocs.org/projects/ncar-cicd/badge/?version=latest)](https://ncar-cicd.readthedocs.io/en/latest/?badge=latest)

This documentation site covers NCAR's Continuous Integration and Continuous Deployment (CI/CD) processes, workflows, and best practices. It's built using the [MkDocs](https://www.mkdocs.org/) platform with a customized Material for MkDocs theme that aligns with NCAR branding and colors.

## Overview

Our CI/CD workflows are designed as starting points and templates for NCAR scientific software projects. These workflows provide a foundation that teams can adapt and expand upon for their specific needs. The system supports multiple compiler configurations, MPI implementations, GPU acceleration options, and architecture targets to help establish basic CI/CD practices.

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

The CI/CD workflows are built upon proven container testing methodologies that have been successfully adapted for NCAR applications. These templates provide:

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

For detailed examples and step-by-step instructions, please visit the [Getting Started](getting-started) page.

## Support

If you have any questions regarding these workflows or need assistance implementing CI for your project, please reach out to [Cena Brown](mailto:cmille73@ucar.edu) or the Applied Computing Sciences team in CISL (mailto:acs@ucar.edu) for assistance.
