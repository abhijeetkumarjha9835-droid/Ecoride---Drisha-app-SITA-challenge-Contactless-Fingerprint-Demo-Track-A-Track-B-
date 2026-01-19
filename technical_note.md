# Technical Note – Drisha (Track A & Track B)

Startup Name: EcoRide  
App Name: Drisha  
Challenge: SITAA Contactless Fingerprint Authentication Challenge  

---

## Objective

The objective of this Android APK is to demonstrate a reduced-scope, working prototype for contactless fingerprint capture, real-time quality assessment, and fingerprint-oriented image enhancement using a standard smartphone camera.  
This demonstrator is submitted as part of the execution evaluation assignment for Track A and Track B.

---

## Track A – Contactless Finger Capture & Quality Assessment

### System Overview
The application captures finger images in a contactless manner using the mobile camera. A live camera preview is provided along with an on-screen visual guide to assist the user in proper finger positioning.

### Finger Detection and Segmentation
Finger detection is performed using rule-based computer vision techniques suitable for real-time execution on mobile devices. The pipeline isolates the finger region from the background using shape, intensity, and contour-based analysis.

### Quality Assessment
The following quality indicators are evaluated on live frames before allowing capture:

1. **Blur / Focus Assessment**  
   Image sharpness is evaluated using focus-related metrics to detect motion blur or defocus.

2. **Illumination Check**  
   Pixel intensity statistics are analyzed to identify underexposed or overexposed capture conditions.

3. **Finger Coverage and Orientation**  
   The segmented finger region is evaluated to ensure sufficient coverage within the frame and acceptable orientation.

### Capture Decision Logic
Image capture is enabled only when all defined quality thresholds are satisfied. If any quality condition fails, the user is prompted to adjust finger position or lighting conditions. This ensures that only usable finger images are captured.

---

## Track B – Finger Image Enhancement & Template Readiness

### Finger Region Isolation
The captured finger image is further processed to isolate the region of interest required for fingerprint enhancement.

### Image Enhancement Pipeline
The enhancement pipeline focuses on improving the visual quality of fingerprint patterns for downstream processing. The following steps are applied:

- Noise reduction to suppress background artifacts  
- Contrast normalization to improve overall clarity  
- Enhancement of ridge–valley visibility suitable for fingerprint analysis  

The enhancement is designed using lightweight, classical image-processing techniques suitable for mobile execution.

### Output
The system produces an enhanced finger image that is visually improved and better suited for subsequent stages such as template generation or matching, though matching itself is outside the scope of this demonstrator.

---

## Design Considerations

- Rule-based and classical image-processing methods were selected for explainability and real-time performance.
- The implementation prioritizes clarity of execution, user guidance, and robustness under varying capture conditions.
- The prototype is designed to demonstrate approach and execution capability rather than production readiness.

---

## Scope Limitation

This demonstrator focuses on:
- Contactless finger capture
- Quality assessment
- Fingerprint-oriented image enhancement  

Fingerprint matching, similarity scoring, and identity verification are intentionally excluded, in line with the defined scope of Track A and Track B.
