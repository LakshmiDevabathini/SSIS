# SSIS Data Processing Repository

This repository contains SQL Server Integration Services (SSIS) packages for managing and processing healthcare data across multiple Value Demonstration Team (VDT) projects.

## Repository Structure

- **SSIS/**: Main folder containing all SSIS projects
  - **VDT206/**: VDT206 unified data processing packages
  - **VDT207/**: VDT207 unified data processing packages  
  - **Racial Disparity/**: Analysis packages for racial disparity studies
- **movies.lsdl.yaml**: Configuration file for data schema definitions

## Purpose

This repository serves as the central location for:
- Healthcare data ETL (Extract, Transform, Load) processes
- Unified data processing for VDT compliance reporting
- Data integration workflows for multiple healthcare systems
- Quality assurance and validation packages

## Getting Started

1. Open the appropriate VDT folder (VDT206 or VDT207)
2. Load the Visual Studio solution file (.sln)
3. Configure connection parameters in Project.params
4. Deploy packages to your SSIS environment

## Requirements

- SQL Server Data Tools (SSDT)
- SQL Server Integration Services
- Visual Studio 2019 or later
- Access to source healthcare databases

## Support

For questions or issues related to these SSIS packages, please contact the Data Engineering team.