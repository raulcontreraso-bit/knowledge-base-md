
# Post-Mortem & Diagnostic Guide: Firebase Data Connect Setup

## 1. Executive Summary: Why It Works Now

The Firebase Data Connect emulator setup is now functional because three critical alignment issues were resolved across your configuration files and cloud environment:

1. **Correct YAML Root-Level Hierarchy:**
    
    In `dataconnect.yaml`, the `datasource:` configuration block was originally indented under `schema:`. Because `firebase-tools` expects `datasource` at the root level of the configuration object, accessing `config.datasource.postgresql` caused a JavaScript runtime crash (`TypeError: Cannot read properties of undefined (reading 'postgresql')`). Aligning `datasource:` at the root level resolved the crash.
    
2. **Compliance with the Two-File Specification:**
    
    Firebase Data Connect strictly enforces a two-file architecture. The root file (`dataconnect/dataconnect.yaml`) defines service metadata, schema sources, and data source targets using `connectorDirs`. The individual connector folder (`dataconnect/connector/connector.yaml`) defines specific connector properties (`connectorId`, `authMode`). Attempting to define connectors inline inside `dataconnect.yaml` caused the underlying build tool (`fdc`) to fail with `connector must have an ID`.
    
3. **Cloud & Schema Metadata Parity:**
    
    The service configuration was updated to match the exact attributes provisioned in your Firebase Cloud console:
    
    - **Service ID:** `firebase-sql-sandbox` (previously `library-sql-test`)
        
    - **Location:** `us-east4` (previously `us-central1`)
        
    - **Schema:** A valid `.gql` schema file (`schema.gql`) was present under `dataconnect/schema/`, resolving the `no schema found for service` deployment metadata warning.
        

## 2. Analysis: Why It Took So Long to Fix

Troubleshooting this issue required multiple iterations due to several factors inherent to early-stage CLI tooling and silent failure modes:

- **Cryptic & Cascading Error Messages:**
    
    When `firebase emulators:start` fails, the underlying Go binary (`fdc`) and the Node.js CLI wrapper fail at different stages. An initial Go error (such as a missing connector ID) stops the Go process, which then causes the Node.js wrapper to try reading properties from uninitialized objects, masking the actual configuration error with a JavaScript `TypeError`.
    
- **Visual Whitespace/Indentation Sensitivity:**
    
    YAML relies on whitespace rather than brackets. In VS Code, a two-space over-indentation under `schema:` is visually subtle, but semantically changes `datasource` from a primary configuration key into an invalid sub-property of `schema`.
    
- **Disconnect Between Local Configs and Cloud State:**
    
    Local configuration files were originally pointed to `library-sql-test` in `us-central1`. However, your actual active project on Firebase Cloud had initialized `firebase-sql-sandbox` in `us-east4`. Diagnosing this required inspecting the cloud control plane rather than just local files.
    

## 3. Primary Rules for Firebase Data Connect Configurations

When setting up or debugging Firebase Data Connect in the future, check these core structural rules first:

### Rule 1: Key Alignment in `dataconnect/dataconnect.yaml`

Ensure `specVersion`, `serviceId`, `location`, `schema`, `datasource`, and `connectorDirs` are all placed at the **root level** (zero leading indent):

```
specVersion: v1
serviceId: <your-exact-service-id>
location: <your-exact-region>
schema:
  source: "./schema"
datasource:
  postgresql:
    database: <database-name>
    cloudSql:
      instanceId: <instance-id>
connectorDirs:
  - "./connector"
```

### Rule 2: Strict Directory Separation

- **Root config:** `dataconnect/dataconnect.yaml`
    
- **Schema definitions:** `dataconnect/schema/*.gql`
    
- **Connector config:** `dataconnect/connector/connector.yaml`
    

### Rule 3: Cloud Resource Matching

The `serviceId` and `location` in `dataconnect.yaml` **must match** what is deployed in Firebase. Any mismatch prevents the emulator hub from registering the schema service.

## 4. Key Diagnostic Commands & Toolkit

When troubleshooting Firebase Data Connect, use these commands in sequence to isolate issues:

### A. Cloud Control Plane Verification

To check what service ID and region exist in your cloud project:

```
firebase dataconnect:services:list
```

To verify which Firebase project your directory is linked to:

```
firebase use
```

### B. Configuration Parsing Test

To force the CLI to parse schema and config files without booting the emulator or database sockets:

```
firebase dataconnect:sdk:generate
```

### C. Log Inspection

When `firebase emulators:start` exits abruptly, inspect the last 50 lines of the detailed debug log:

```
Get-Content firebase-debug.log -Tail 50
Get-Content firebase-debug.log -Tail 30
```

### D. CLI Version Check

Ensure `firebase-tools` is up to date, as Data Connect updates frequently:

```
firebase --version
```

_(If version is below 13.7.0, run `npm install -g firebase-tools@latest`)_