# EyeTTS User Study Framework — Magic Leap 1 Spatial Computing Environment

EyeTTS (Eye Tracking Test Suite) is a controlled experimental framework for evaluating gaze-tracking performance under heterogeneous mixed-reality (MR) conditions. It is designed to benchmark robustness across variations in display pipelines, spatial tracking SDKs, and locomotion constraints.

This repository implements the **front-end data collection system** for the Magic Leap 1 (ML1) platform. Built in Unity, it serves as the real-time **User Study Framework**, responsible for rendering spatial stimuli, managing experimental trials, and logging synchronized gaze, head-pose, and system timestamps.

All recorded streams are processed by the corresponding backend **EyeTTS Calibration Framework**, which performs post-hoc calibration, drift correction, and evaluation metric computation:  
https://github.com/satyam-aw/Eye-Tracking-Test-Suite_EyeTTS_Calibration-Framework


The EyeTTS User Study Framework playlist provides full experimental recordings, including task-specific trials and unedited participant sessions:  
https://www.youtube.com/playlist?list=PLQbqwztmTvAVAUClXj-sOkpQ9sBJbT5pG

---

## Cross-Platform Ecosystem

While each headset requires device-specific implementations due to proprietary SDK constraints, the experimental protocol remains standardized across platforms:

- Magic Leap 1 (This Repository):  
  https://github.com/satyam-aw/EyeTTS_User-Study-Framework_Magic-Leap-1/

- Meta Quest Pro:  
  https://github.com/sydneylim/QuestPro_EyeTracking

- HoloLens 2:  
  https://github.com/vivianross06/HoloLens-Eye-Tracking

- EyeTTS Calibration Framework:  
  https://github.com/satyam-aw/Eye-Tracking-Test-Suite_EyeTTS_Calibration-Framework

---

##  Experimental Task Architecture

The framework choreographs seven unique spatial tracking paradigms designed to systematically isolate and evaluate gaze-tracking degradation across variable anatomical and locomotor constraints:

### 1. `R` (Recalibration Task)
Participants stabilize their head via a chin rest and track a discrete stimulus that transitions pseudo-randomly to discrete positions across the display surface following a fixed temporal delay.

<p align="center">
  <a href="https://www.youtube.com/watch?v=8e9rMN_CNnw&list=PLQbqwztmTvAVAUClXj-sOkpQ9sBJbT5pG&index=2"><img src="ReadMe/r.png" alt="R Task Schema" width="230" align="top"></a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://www.youtube.com/watch?v=8e9rMN_CNnw&list=PLQbqwztmTvAVAUClXj-sOkpQ9sBJbT5pG&index=2"><img src="https://img.youtube.com/vi/8e9rMN_CNnw/maxresdefault.jpg" alt="R Task Video Playback" height="160" align="top"></a>
</p>
<p align="center"><em>Figure 1: Spatial paradigm diagram (left) next to the user trial clip (right, click to watch playback).</em></p>



### 2. `w1` / `HC` (Head-Constrained World-Stabilized Task)
Participants utilize a chin rest to eliminate head rotation while tracking a stimulus traversing a continuous geometric path bounded entirely within the display's near field-of-view (FOV).

<p align="center">
  <a href="https://www.youtube.com/watch?v=SmwadqDaDb4&list=PLQbqwztmTvAVAUClXj-sOkpQ9sBJbT5pG&index=3"><img src="ReadMe/hc.png" alt="R Task Schema" width="230" align="top"></a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://www.youtube.com/watch?v=SmwadqDaDb4&list=PLQbqwztmTvAVAUClXj-sOkpQ9sBJbT5pG&index=3"><img src="https://img.youtube.com/vi/SmwadqDaDb4/maxresdefault.jpg" alt="R Task Video Playback" height="160" align="top"></a>
</p>
<p align="center"><em>Figure 2: Spatial paradigm diagram (left) next to the user trial clip (right, click to watch playback).</em></p>

### 3. `w2` / `BC` (Body-Constrained World-Stabilized Task)
Participants sit unconstrained and execute rotational head movements to track a stimulus traversing a continuous path mapped to the world frame of reference (FOR), extending beyond the static display FOV boundaries.

<p align="center">
  <a href="https://www.youtube.com/watch?v=XAAg48gus8c&list=PLQbqwztmTvAVAUClXj-sOkpQ9sBJbT5pG&index=4"><img src="ReadMe/bc.png" alt="W2 Task Schema" width="230" align="top"></a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://www.youtube.com/watch?v=XAAg48gus8c&list=PLQbqwztmTvAVAUClXj-sOkpQ9sBJbT5pG&index=4"><img src="https://img.youtube.com/vi/XAAg48gus8c/maxresdefault.jpg" alt="R Task Video Playback" height="160" align="top"></a>
</p>
<p align="center"><em>Figure 3: Spatial paradigm diagram (left) next to the user trial clip (right, click to watch playback).</em></p>

### 4. `w3` / `WSW` (Ambulatory Walking World-Stabilized Task)
Participants navigate an ambulatory circular trajectory around a physical reference table while maintaining fixation on a continuous tracking stimulus bound to the static world FOR above the surface plane.

<p align="center">
  <a href="https://www.youtube.com/watch?v=aTP6IYBDoKY&list=PLQbqwztmTvAVAUClXj-sOkpQ9sBJbT5pG&index=5"><img src="ReadMe/wsw.png" alt="W3/WSW Task Schema" width="230" align="top"></a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://www.youtube.com/watch?v=aTP6IYBDoKY&list=PLQbqwztmTvAVAUClXj-sOkpQ9sBJbT5pG&index=5"><img src="https://img.youtube.com/vi/aTP6IYBDoKY/maxresdefault.jpg" alt="R Task Video Playback" height="160" align="top"></a>
</p>
<p align="center"><em>Figure 4: Spatial paradigm diagram (left) next to the user trial clip (right, click to watch playback).</em></p>


### 5. `s4` / `SSW` (Ambulatory Walking Screen-Stabilized Task)
Participants navigate an ambulatory circular trajectory around a physical reference table while tracking a continuous stimulus bound rigidly to the display screen's planar coordinate system.

<p align="center">
  <a href="https://www.youtube.com/watch?v=NL6pmvKADMs&list=PLQbqwztmTvAVAUClXj-sOkpQ9sBJbT5pG&index=6"><img src="ReadMe/ssw.png" alt="s4 SSW Task Schema" width="230" align="top"></a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://www.youtube.com/watch?v=NL6pmvKADMs&list=PLQbqwztmTvAVAUClXj-sOkpQ9sBJbT5pG&index=6"><img src="https://img.youtube.com/vi/NL6pmvKADMs/maxresdefault.jpg" alt="R Task Video Playback" height="160" align="top"></a>
</p>
<p align="center"><em>Figure 5: Spatial paradigm diagram (left) next to the user trial clip (right, click to watch playback).</em></p>


### 6. `b5` / `BSW` (Ambulatory Walking Body-Stabilized Task)
Participants navigate an ambulatory circular trajectory around a physical reference table while tracking a continuous stimulus structurally bound to a hardware controller attached to their thoracic body frame.

<p align="center">
  <a href="https://www.youtube.com/watch?v=as5A5Tq7IDI&list=PLQbqwztmTvAVAUClXj-sOkpQ9sBJbT5pG&index=13"><img src="ReadMe/bsw.png" alt="b5 BSW Task Schema" width="230" align="top"></a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://www.youtube.com/watch?v=as5A5Tq7IDI&list=PLQbqwztmTvAVAUClXj-sOkpQ9sBJbT5pG&index=13"><img src="https://img.youtube.com/vi/as5A5Tq7IDI/maxresdefault.jpg" alt="R Task Video Playback" height="160" align="top"></a>
</p>
<p align="center"><em>Figure 6: Spatial paradigm diagram (left) next to the user trial clip (right, click to watch playback).</em></p>

### 7. `H` (Linear Hallway Locomotion Task)
Participants navigate a linear trajectory down an open architectural hallway while tracking a continuous stimulus translating dynamically along the longitudinal vector of the corridor.

<p align="center">
  <a href="https://www.youtube.com/watch?v=Y3BtgPO-QN0&list=PLQbqwztmTvAVAUClXj-sOkpQ9sBJbT5pG&index=7"><img src="ReadMe/h.png" alt="H Task Schema" width="230" align="top"></a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://www.youtube.com/watch?v=Y3BtgPO-QN0&list=PLQbqwztmTvAVAUClXj-sOkpQ9sBJbT5pG&index=7"><img src="https://img.youtube.com/vi/Y3BtgPO-QN0/maxresdefault.jpg" alt="R Task Video Playback" height="160" align="top"></a>
</p>
<p align="center"><em>Figure 7: Spatial paradigm diagram (left) next to the user trial clip (right, click to watch playback).</em></p>

---

##  Software Architecture & Core Control Logic

The front-end runtime and data serialization mechanisms are governed by two principal execution scripts:

1.  [`welcome.cs`](https://github.com/satyam-aw/EyeTTS_User-Study-Framework_Magic-Leap-1/blob/main/Assets/Scripts/welcome.cs): Manages global execution routing, trial state progression, and cross-scene initialization. To eliminate cognitive and spatial order-bias effects across the participant cohort, it programmatically randomizes block deployment sequences utilizing a balanced **Latin Square Design**.
2.  [`Logger/TrialLogger.cs`](https://github.com/satyam-aw/EyeTTS_User-Study-Framework_Magic-Leap-1/blob/main/Assets/Scripts/Logger/TrialLogger.cs): Handles high-frequency synchronous data pooling. It samples raw gaze vectors, eye center matrices, and head pose transforms from the underlying hardware layer, serializing the data stream directly to a local non-volatile storage cache in real time. 
    *   *System Tooling:* The script exposes runtime inspector hooks for fine-grained calibration adjustments (e.g., target scale normalization, offset re-centering) and hotkeys to reset coordinate domains during technical testing.

---

## Getting Started & Local Deployment

### 1. Hardware & System Requirements
*   **Target Device:** Magic Leap 1 (ML1) Spatial Computing Headset + 3DoF Control.
*   **Workstation Environment:** Magic Leap Lab installed with configured environmental path variables.
*   **Lumin SDK Version:** `0.26.0`

### 2. Unity Project Environment Setup
1. Open this repository via **Unity Hub** using **Unity Editor 2020.3.x LTS**.
2. Confirm your platform build target is set to **Lumin** via `File > Build Settings`.
3. Navigate to `Edit > Project Settings > Player > Lumin Settings Tab`.
4. Verify that the following mandatory security and hardware manifest **Privileges** are enabled:
   * `LowLatencyLightwear`
   * `EyeTracking` (Explicit camera-array mapping authorization)
   * `WorldReconstruction` (Required for spatial meshing and world-stabilized coordinates `w1`–`w3`)

### 3. Build & Flash Deployment
1. Enable **Developer Mode** and authorize **USB Debugging** within the Magic Leap 1 device interface.
2. Connect the headset to your host workstation via a high-speed USB-C bridge.
3. Execute `Build And Run` via the Unity Build Settings window to compile the binary and push it to the device storage segment.

---

## Data Output & Pipeline Ingestion

Upon the termination of each task trial, the `TrialLogger` flushes its local stream buffer to file. 

### 1. File Naming Convention & Schema
To maintain absolute compliance with the automated parsing routines in the back-end Data Module, output logs are structured using a specific alphanumeric tokenization scheme:

```text
Schema:   [Participant_ID]/[Task_Prefix]_[Date]_[Timestamp]_[Meridiem].csv
Template: participant-012/s4_0308_132009_PM.csv
```
*   **`Task_Prefix`**: Maps directly to the task identifiers (`r`, `hc`, `bc`, `wsw`, `ssw`, `bsw`, `h`).
*   **`Participant_ID`**: Alphanumeric index corresponding to the subject.
*   **`Timestamp / Meridiem`**: Tracks chronological session initialization for unambiguous trial ordering.

### 2. CSV Column Data Schema
The output log generates a standardized data header capturing structural and biological variables synchronously at runtime:

```text
frame,PathIDX,timestamp,seconds,head_pos,head_euler,head_quaternion,gaze_confidence,gaze_pos,target_pos,gaze_vector,target_vector,gaze_vis_x,gaze_vis_y,target_vis_x,target_vis_y,local_x_axis,local_y_axis,local_z_axis,left_right_eye_center,left_right_eye_center_confidence,left_right_eye_gaze,left_right_eye_forward_gaze,left_right_eye_is_blinking,left_right_eye_pupil_size,calibration_status
```

*   **Spatial Vectors & Transforms**: `head_pos`, `gaze_pos`, `target_pos`, `left_right_eye_center` are written as serialized coordinate strings `(X_Y_Z)` which require string cleanup formatting prior to math evaluations.
*   **Temporal Fields**: `timestamp` preserves the exact systemic time block, while `seconds` establishes the relative baseline clock starting at `0.0`.
*   **Task State Metrics**: `PathIDX` controls experimental index matching. Values of `99` signify initialization buffers, positive indices signify continuous target tracking phases, and negative indices indicate static target positions. This dual-indexing schema enables synchronous capturing of both dynamic and static target responses within a single experimental session.

### 3. Ingestion Extraction Pipeline
Because data is written onto the device's localized Unix-based application data storage container, logs must be pulled using the Android Debug Bridge (ADB) CLI during post-session cleanup. 

To pull and map your logs into the target analytics engine directory, run:

```bash
# Execute local adb pull from the application sandbox to the analytical input directory
adb pull /sdcard/Android/data/com.DefaultCompany.MagicLeapEyeTracking/files/ ./participant-data/
```

Once transferred, the target script suite in the [EyeTTS Data Module](https://github.com/satyam-aw/Eye-Tracking-Test-Suite_EyeTTS_Data-Module) reads this directory structure, automatically applies post-hoc linear regression metrics based on the matching baseline task, and logs centralized metrics to `error_df.csv`.

---

## Refereed Poster Papers

This module forms the analytical foundation of, and directly links to, the engineering evaluations presented in the following peer-reviewed IEEE research contributions:

```bibtex
@inproceedings{vrw2024eyetracking,
  author    = {Awasthi, Satyam and Ross, Vivian and Lim, Sydney and Beyeler, Michael and Höllerer, Tobias},
  title     = {Eye Tracking Performance in Mobile Mixed Reality},
  booktitle = {2024 IEEE Conference on Virtual Reality and 3D User Interfaces Abstracts and Workshops (VRW)},
  year      = {2024},
  pages     = {321--322},
  doi       = {10.1109/vrw62533.2024.00321}
}

@inproceedings{ismar2023eyetts,
  author    = {Awasthi, Satyam and Ross, Vivian and Beyeler, Michael and Höllerer, Tobias},
  title     = {EyeTTS: Evaluating and Calibrating Eye Tracking for Mixed-Reality Locomotion},
  booktitle = {2023 IEEE International Symposium on Mixed and Augmented Reality Adjunct (ISMAR-Adjunct)},
  year      = {2023},
  pages     = {104--105},
  doi       = {10.1109/ismar-adjunct60411.2023.00104}
}
```
