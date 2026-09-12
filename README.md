# Dobby

*This repository was created to present my individual contributions to DOBBY. DOBBY was orignally built as a team project at Milstein's Summer Program at Cornell Tech.*

## Project Description:
DOBBY is a facade crack-detection model, tied to NYC's Local Law 11 inspection requirement, aimed to replace the slow, expensive, and energy-consuming process of the inspection. 

### Project Goal:
Using a drone, we aim to capture video footage of a buildings facade that then gets processed into photos for inspection. After inspection, cracks are not only identified but categorized into types for all parties involved in the process to have access to and understand. This device and model is not meant to replace QEWIs (Qualified Exterior Wall Inspectors) but to assist them in their inspection to avoid unnecessary costs like extensive rig set-up, scaffolding set-up, and more. We hope to then create a 3D rendering of the building with crack defects being shown on relative locations, labeled as SAFE, SWARMP (Safe with a Maintenance and Repair Program), or UNSAFE. This is meant to act as an interactive and accessible record to replace the tedious process of crack submissions and view the inspection history of buildings.

### My Role:
I trained a RF-DETR model and was involved in the decisions around labeling strategy and video-to-frame processing. I also was in charge of outreach and reguarly conducted calls to various parties involved in the Local Law 11 process to best understand the situation from all perspectives.

### Technical Decisions: 
- We used RF-DETR for defect detection since it gives real-time object detection with bounding boxes, localizing cracks on the facade rather than just flagging their presence.
- We started with 6 defect classes, transitioned down to 1 class to test whether improve accuracy at our scale, the rebuilt back up to 5 classes, a intentional tradeoff of granularity for reliability (61.8% mAP@50, 57.2% precision).
- Video was sampled into frames at 2-4fps with overlap minimized and blurry/redundant frames auto-filtered, to keep full facade coverage without overwhelming the pipeline with near-duplicate data.
