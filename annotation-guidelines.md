# Medical Image Annotation Guidelines  
Radiology AI Training Datasets

**Author:** Ingrid Bernal  
**Role:** Senior Medical Data Specialist & Radiology Technologist  
**Experience:** 16+ years in diagnostic imaging (X-ray, CT, MRI, Mammography)  
**Last updated:** March 2026

## 1. Objective
Standardize high-quality annotation of radiological images (Chest X-ray, Mammography, CT, MRI) to train robust AI models for pathology detection, segmentation and clinical decision support.  
Emphasis on clinical accuracy, inter-observer consistency, edge-case handling and reduction of bias in healthcare AI datasets.

## 2. General Annotation Principles
- **Precision over speed:** Boundaries must tightly follow the pathological finding without including healthy tissue.  
- **Completeness:** Label all visible manifestations of a pathology, even subtle or partial.  
- **Polygons preferred:** Use polygons for irregular shapes (microcalcifications, spiculated masses, abscesses, cysts). Bounding boxes only for large/round lesions when speed is critical.  
- **Transparency:** Keep fill opacity low (0.3–0.5) to avoid obscuring underlying anatomy.  
- **Clinical context:** Annotations must reflect real-world diagnostic interpretation (e.g., inspiration level, projection, contrast phase).

## 3. Tools & Workflow
- **2D Annotation:** MakeSense.ai (quick polygons & boxes), Label Studio (advanced control, export formats)  
- **3D/Volumetric Segmentation:** 3D Slicer (Segment Editor + Islands for isolation + Fill between slices)  
- **Quality Control:** Double-check against clinical knowledge and reference reports (when available)

## 4. Specific Pathology & Structure Protocols (Examples)
### A. Cardiomegaly (Chest X-ray)
- Definition: Cardiothoracic ratio > 0.5 on PA view  
- Tool: Bounding box (tight around cardiac silhouette)  
- Tip: Exclude poor inspiration artifacts; label associated devices separately.

### B. Pneumonia / Consolidation / Ground Glass (Chest X-ray / CT)
- Definition: Increased opacity in lung parenchyma  
- Tool: Polygon (preferred for irregular shapes) or Bounding box (localized)  
- Boundary: Include all areas of density change distinguishable from normal parenchyma.

### C. Microcalcifications & Spiculated Masses (Mammography)
- Tool: Polygon (essential for cluster and border detail)  
- Attributes: Label distribution (grouped, linear, segmental), morphology (amorphous, heterogeneous).

### D. Brain Tumor (MRI – contrast-enhanced)
- Tool: 3D Slicer (multi-slice segmentation + Islands for isolation)  
- Boundary: Follow contrast-enhancing rim; label necrosis/cystic components separately if visible.

### E. Medical Devices & Artifacts (All Modalities)
- Pacemaker: Generator + leads until cardiac entry  
- CVC / PICC / ET tube: Full length visible  
- Surgical hardware: Wires, clips, plates  
- Note: Label to prevent misclassification as pathology.

## 5. Quality Assurance (QA) & Edge Cases
1. **First Pass:** Identify findings based on image appearance and clinical context.  
2. **Second Pass:** Verify boundary tightness, label consistency and exclusion of artifacts.  
3. **Edge Cases:**  
   - Poor inspiration / motion artifact → label as "Artifact" if impacts interpretation  
   - Overlapping findings → label each separately with hierarchy  
   - Subtle findings → use polygon for better precision  
4. **Inter-observer Agreement:** Random double-annotation on 10–20% of cases; aim for >90% IoU on polygons.

These guidelines evolve with new modalities and datasets. Feedback welcome.

Ingrid Bernal  
ingridbm5184@gmail.com  
March 2026
