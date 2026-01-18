# Medical Image Annotation Guidelines: Radiology AI Training
**Author:** Ingrid Bernal, Senior Medical Data Specialist (16+ years Clinical Experience)

## 1. Objective
The goal of these guidelines is to standardize the annotation process for Chest X-ray datasets (NIH/VinDr-CXR), ensuring clinical accuracy and reducing inter-observer bias for AI model training.

## 2. General Labeling Standards
* **Precision:** Bounding boxes must tightly encompass the finding without including unnecessary healthy tissue.
* **Completeness:** All visible manifestations of a pathology must be labeled, even if subtle.
* **Attributes:** Each annotation should specify if the finding is associated with medical devices (artifacts).

---

## 3. Specific Pathology Protocols (Examples)

### A. Cardiomegaly
* **Definition:** Enlargement of the cardiac silhouette (Cardiothoracic ratio > 0.5 on PA view).
* **Annotation Rule:** Use a Bounding Box.
* **Boundary:** The box must touch the lateral-most borders of the heart on both sides and the base of the heart at the diaphragmatic level.
* **Clinical Tip:** Ensure the patient is in full inspiration; poor inspiration can mimic cardiomegaly.

### B. Pneumonia / Infiltration
* **Definition:** Areas of increased opacity within the lung parenchyma.
* **Annotation Rule:** Use Polygons for irregular shapes or Bounding Boxes for localized opacities.
* **Boundary:** Include the entire area of consolidation. If borders are ill-defined (ground-glass appearance), include the area where the density increase is clearly distinguishable from normal parenchyma.

---

## 4. Medical Devices & Artifacts (Critical for Model Robustness)
AI models often confuse devices with pathologies. We apply strict labeling for:
* **Pacemakers:** Label the generator and the leads (wires) until they enter the cardiac silhouette.
* **Support Lines:** Label CVC (Central Venous Catheters), PICC lines, and Endotracheal tubes.
* **Surgical Hardware:** Sternal wires and humeral plates must be labeled to avoid "foreign body" misclassification.

## 5. Quality Assurance (QA) Process
1.  **First Pass:** Initial identification of findings based on clinical history and image density.
2.  **Verification:** Cross-referencing with official radiology reports (if available).
3.  **Refinement:** Review of box tightness and label metadata.
   
