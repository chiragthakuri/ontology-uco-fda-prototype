# Ontology: UCO-FDA Prototype

## Class Hierarchy

### Under UCO’s `CourseOfAction`:
- **CybersecurityControl** (Subclass)
  
  ↳ **AuthenticationControl**  
  ↳ **AuthorizationControl**  
  ↳ **CryptographyControl**  
  ↳ **IntegrityControl**  
  ↳ **ConfidentialityControl**  
  ↳ **EventDetectionAndLoggingControl**  
  ↳ **ResiliencyAndRecoveryControl**  
  ↳ **UpdatabilityAndPatchabilityControl**

### Under custom class `RegulatedProcess`:
- **CybersecurityTesting**
  - **VulnerabilityScan**
  - **PenetrationTest**
  - **FuzzTesting**
- **CybersecurityRiskAnalysis**
  - **QualitativeRiskAnalysis**
  - **QuantitativeRiskAnalysis**

### Under UCO’s `File`:
- **CybersecurityRiskManagementReport**
  - **Cybersecurity Management Plan**
  - **Residual Risk Report**
  - **Risk Acceptance Report**
- **CybersecurityThreatModel**
- **CybersecurityThreatModel**
- **SoftwareBillofMaterials**

---

## Relationships

| Relationship | Domain | Range |
|---------------|---------|--------|
| `mitigates` | CybersecurityControl | CybersecurityRiskAnalysis |
| `reveals` | CybersecurityTesting | UnresolvedSoftwareAnomaly |
| `isAddressedBy` | UnresolvedSoftwareAnomaly | CybersecurityControl |

---

## Attributes

### `CybersecurityControl`
- `controlID` → `xsd:string`
- `implementationStatus` → `xsd:string`

### `UnresolvedSoftwareAnomaly`
- `anomalySeverity` → `xsd:string`
- `discoveryDate` → `xsd:dateTime`

### `CybersecurityRiskAnalysis`
- `finalRiskScore` → `xsd:float`

### `CybersecurityTesting`
- `testingStandard` → `xsd:string`
- `testMethodology` → `xsd:string`

---

## Interoperability Modeling

I modeled **interoperability** as a relationship between **products**, which is a key requirement for regulated medical device systems.

### Object Property Definition

**Object Property:** `isInteroperableWith`  
**Domain (Starts at):** Product  
**Range (Points to):** Product  
**Purpose:** To formally state that one product (e.g., a medical device) can safely exchange and use information with another product (e.g., an EMR system or another medical device).

