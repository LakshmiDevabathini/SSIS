# VDT206 Unified Data Processing Packages

This folder contains the complete SSIS solution for VDT206 unified data processing, including all packages, configurations, and deployment artifacts.

## SSIS Packages Overview

### Data Extraction Packages
- **CreateVDT206 Unified ClaimsFlatFile.dtsx**: Extracts and processes healthcare claims data into standardized flat file format
- **CreateVDT206 Unified CRSPFlatFile.dtsx**: Processes Claims-Related Service Provider data  
- **CreateVDT206 Unified EligibilityFlatFile.dtsx**: Extracts member eligibility and enrollment information
- **CreateVDT206 Unified MemberFlatFile.dtsx**: Processes member demographics and related data
- **CreateVDT206 Unified ProviderFlatFile.dtsx**: Extracts healthcare provider information and credentials
- **CreateVDT206 Unified RxFlatFile.dtsx**: Processes prescription and pharmacy data

### Assessment Data Packages  
- **CreateVDT206 Unified LOCUS Flat File.dtsx**: Processes LOCUS (Level of Care Utilization System) assessment data
- **CreateVDT206 Unified LocusFlatFile.dtsx**: Alternative LOCUS data processing workflow

### Control and Orchestration Packages
- **Load VDT206 Unified Driver.dtsx**: Master control package that orchestrates the execution of all data processing workflows
- **Load All VDT206 Unified Tables.dtsx**: Coordinates loading of all processed data into target tables/warehouse

### File Transfer Package
- **SFTP VDT206 Unified Files.dtsx**: Handles secure file transfer of processed data files to designated SFTP locations

### Utility Packages
- **Package1.dtsx**: Utility package for supplementary data processing tasks
- **Package2.dtsx**: Additional utility package for specialized workflows

## Project Configuration

### Solution Files
- **VDT206Unified.sln**: Visual Studio solution file for loading all packages
- **VDT206Unified.dtproj**: SSIS project definition file
- **Project.params**: Contains project-level parameters and connection strings

### Database Configuration  
- **VDTUnified.database**: Database project configuration for target schema

### Build and Deployment
- **bin/Azure/**: Contains compiled package deployment files (.ispac)
- **obj/Azure/**: Build artifacts and intermediate compilation files

## Configuration Parameters

Key parameters in `Project.params` include:
- Database connection strings (source and target)
- File path configurations  
- SFTP server credentials
- Processing date ranges
- Error handling thresholds

## Execution Order

1. **Load VDT206 Unified Driver.dtsx** (Master controller)
   - Orchestrates execution of all extraction packages
   - Monitors completion status and error handling
   
2. **Data Extraction Packages** (Executed in parallel where possible)
   - Claims, Eligibility, Member, Provider, Rx, CRSP, LOCUS packages
   
3. **Load All VDT206 Unified Tables.dtsx**
   - Loads processed data into target warehouse tables
   
4. **SFTP VDT206 Unified Files.dtsx**
   - Transfers final output files to designated locations

## Monitoring and Logging

- Built-in SSIS logging for package execution tracking
- Error handling with detailed logging to database tables
- Performance monitoring and execution statistics
- Email notifications for critical failures (if configured)

## Deployment Notes

- Deploy using the .ispac file in bin/Azure/ folder
- Configure environment-specific parameters before deployment
- Ensure all source database connections are accessible
- Verify SFTP credentials and target folder permissions

## Upgrade History

- **UpgradeLog.htm**: Documentation of package upgrades and migrations
- **UpgradeLog2.htm, UpgradeLog3.htm, UpgradeLog4.htm**: Historical upgrade records