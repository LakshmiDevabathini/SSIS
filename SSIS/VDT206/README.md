# VDT206 - Value Demonstration Team 206

This folder contains SSIS packages specifically designed for VDT206 unified data processing and reporting requirements.

## Overview

VDT206 focuses on creating standardized, unified datasets from various healthcare data sources to support value-based care analysis and reporting. The packages in this project handle the extraction, transformation, and loading of healthcare data including:

- Claims data
- Member eligibility information
- Provider data
- Prescription (Rx) data
- CRSP (Claims-Related Service Provider) data
- LOCUS assessment data

## Folder Contents

- **VDTUnified/**: Main SSIS project containing all data processing packages

## Data Flow Process

1. **Extract**: Source data from various healthcare databases
2. **Transform**: Clean, validate, and standardize data formats
3. **Load**: Create unified flat files and load into target data warehouse
4. **Transfer**: SFTP processed files to designated locations

## Key Features

- Automated data validation and quality checks  
- Error handling and logging
- Configurable connection parameters
- Support for incremental data loads
- Standardized file formats for downstream consumption

## Dependencies

- Source healthcare database connections  
- Target data warehouse access
- SFTP server credentials for file transfers
- Configured Project.params file