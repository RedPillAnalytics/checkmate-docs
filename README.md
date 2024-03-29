# Checkmate Studio

## What is Checkmate Studio?

A front-end desktop class application that works as Checkmate CLI’s interface designed to mostly import and export BI development artifacts.

Checkmate enables Continuous Delivery for products or platforms that don't naturally support it. This tool is also used on real multi-user development with git for source control management (SCM).

Currently Checkmate Studio supports:

- OBIEE (Oracle Business Intelligence Enterprise Edition)
- ODI (Oracle Data Integrator).
- INFA (Informatica PowerCenter)

## Checkmate Menu

### File

- Configure Modules: Click to open configuration window.
- Checkmate Versions Refresh - Click to update the Checkmate version

### Window

- Minimize: Mark for minimize current window
- Close: Mark for closing current window
- Reload: Mark for reloading current window
- Copy: Mark for copying selected text to clipboard
- Paste: Mark for pasting text where specified from clipboard

### Help

- Version installed
- Documentation
- Website
- Social
- Videos

## General Actions

 - Clear task history: Mark for troubleshooting.
 - Terminate Gradle Tasks: Stop all gradle processes.
 - Write Gradle Build File: Create (if not created) or update build.gradle file with the settings defined.
 - Open command prompt build directory: Used for command line execution.
 - Test Connection: Run a task that validates the connection to the BI Tool repo using the parameters specified
 - Save to File: Save the parameters in the settings to a file called 'initial.json'

## OBI

### Typical Workflow

1. Turn on OBI server and configure Studio settings
2. Clone a git repository that contains working catalog and repo metadata to git
3. Import source controlled data into OBI using Studio
4. Make OBI changes
5. Export OBI changes into source control using Studio
6. Commit and push changes to git.

### Settings

Source Base: 'directory where you cloned git repo' Ex: c:\git  
Domain Home: 'directory where you installed OBI' Ex: c:\fmw\product\12.2.1.4\user_projects\domains\bi  
Checkmate Version: 10.1.2 (latest as of time of writing)  
OBIEE Version: 'version of OBI you are working with'  
Source Base Type: MDS-XML (unless otherwise needed)  
Metadata Project: 'blank'  
Admin User: weblogic (or as specified)  
Admin Pass: Admin123 (or as specified)  
Repo Pass: Admin123 (or as specified)  
Service Instance: ssi (or as specified)  
Remote: localhost:9502 (or as specified)  
Use REST API(s): Marked by Default, Checkmate leverages on existing product REST APIs  
Catalog Archive: Mark for using presentation catalog archive file instead of direct catalog file copies  
Online Catalog: Mark for using online presentation catalog instead of the offline presentation catalog whenever possible  

### Preferences

Options for command line utility:

- Verbose output: Mark to get a more detailed task output
- Re-run tasks: Mark run tasks ignoring 'UP-TO-DATE' state

### Tasks

- Import

    Catalog: Mark for importing catalog
    Metadata: Mark for importing metadata

- Export

  Catalog: Mark for exporting catalog
  Metadata: Mark for exporting metadata

- Reload

- Publish (feature still being implemented)

### Quickstart
You can drag and drop .rpd and .catalog files onto the settings sidebar to initiate a quick import.

## ODI

### Typical User Workflow

1. Clone a git repository that contains ODI working repository to git
2. Import ODI objects using Studio (specifies type of import).
3. Make ODI changes
4. Export ODI changes using Studio (specifies type of export).
5. Commit and push changes to git

### Settings

Project Name: ‘name project as you wish’   
Source Base: ‘directory where you cloned git repo’  
Checkmate Version: 0.1.22 (latest as of time of writing)  
ODI Version: ‘version of ODI you are working with’  
URL: ‘jdbc:oracle:thin:@hostname:1521/ORCL’ (specify repo url)  
Driver Name: oracle.jdbc.OracleDriver (or as specified)  
Master Repo: DEV_ODI_REPO (or as specified)  
Master Password: ‘master repo password’  
Work Repo: WORKREP (or as specified)  
ODI User: SUPERVISOR (or as specified)  
ODI Password: ‘password’  
Content Policy: Directory (or as specified)
Work Repository: Development (or as specified)

### Preferences

Enable import/export optional parameters:

- Import Parameters: Mark to show import manual types as options
- Export Parameters: Mark to show export manual types as options
Options for task execution utility:

Mark any of the below options to consider the respective object in an import or export.

- Enable Projects
- Enable Globals
- Enable Topologies
- Enable Models
- Enable LoadPlans
- Enable Scenarios

Options for command line utility:

- Verbose output: Mark to get a more detailed task output
- Re-run tasks: Mark run tasks ignoring 'UP-TO-DATE' state

### Tasks

#### Standard Import/Export

- Import
- Export

#### Importing with optional parameters

Import Project Directory

   - Source Path: path to project directory.

Import Project File

   - Source File: project file exported.

Import Model Directory  

   - Source Path: path to project model directory.

Import Load Plan Directory

   - Source Path: path to project load plans directory.

#### Exporting with optional parameters

Export Project Directory

   - Folder Name: The folder to export.
   - Object Type: The type of the object to export (reusable mapping, mapping, procedure and package).
   - Object Name: The name of the object to export.

Export Project File

- No parameters

Export Model Directory

   -  Model Code: model code to export.

Export Load Plans Directory

  - Source Path: path to project load plan directory.

## INFA

### Typical User Workflow

1. Clone a git repository that contains INFA working repository to git
2. Import INFA objects using Studio (specifies type of import).
3. Make INFA changes
4. Export INFA changes using Studio (specifies type of export).
5. Commit and push changes to git

### Settings

Infa Home: ‘name project as you wish’      
Installation Type: Client (or specified)     
Source Base: ‘directory where you cloned git repo’       
Repo Name: INFA_REPO_RPA (or as specified)    
Domain: DOMAIN_RPA (or as specified)    
Checkmate Version: 1.0.0 (only current available version)     
Admin: 'admin'   
Admin Password: 'password'   

### Preferences

Options for command line utility:

- Verbose output: Mark to get a more detailed task output
- Re-run tasks: Mark run tasks ignoring 'UP-TO-DATE' state

### Tasks

Import Objects

- No parameters

Import Directory

  - Folder Name: The folder to import.
  - Object Type: The type of the object to import (workflow, worklet, mapping, mapplet, source and target).
  - Object Name: The name of the object to import.

Import File

- Folder Name: The folder to import.

Export Objects

- No parameters

Export Directory

- Folder Name: The folder to import.
- Object Type: The type of the object to import (workflow, worklet, mapping, mapplet, source and target).
- Object Name: The name of the object to import.

Export File

- Folder Name: The folder to export.
