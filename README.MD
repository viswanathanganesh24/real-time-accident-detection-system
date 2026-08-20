# Real-Time Accident Detection System (YOLOv8)

Road traffic incidents can result in devastating outcomes, and every second lost in dispatching help can escalate the damage. This system is built to strengthen traffic safety by leveraging YOLOv8 to spot collision events automatically, whether from a live camera feed, a saved video file, or a still image.

---

## Getting Started (Environment & Dependencies)

Before running any scripts, set up your local workspace with these preparation steps:

1. **Create and activate** a dedicated Python virtual environment:  
   ```bash
   python -m venv venv && source venv/bin/activate
   ```

2. **Install** all required libraries:  
   ```bash
   pip install -r requirements.txt
   ```

3. **Clone** the project source code from GitHub:  
   ```bash
   git clone https://github.com/viswanathanganesh24/real-time-accident-detection-system.git
   ```

   You're now ready to move on to the execution phase below.

---

## Running the Detection Pipelines

The system supports two distinct operational modes, depending on your input source.

### 1. Processing Offline Media (Images & Pre-Recorded Videos)

If you have static snapshots or locally stored video clips to analyze, head over to the `ML` folder and trigger the dedicated script:

```bash
python detecting_static.py
```

Once launched, the tool:
- Loads the pretrained YOLOv8 weights
- Runs inference on the files placed inside the `inputs` directory
- Writes the annotated outputs (with bounding boxes and incident labels) neatly into the `results` folder for later review

### 2. Monitoring Live Video Feeds (Streaming Input)

For real-time surveillance scenarios such as traffic cameras or IP-based streams, use the streaming handler found in the same `ML` directory:

```bash
python detecting_videostream.py
```

This script:
- Initializes the model
- Connects to the source defined by the `stream_url` variable
- Continuously dissects the incoming footage into individual frames
- Performs frame-by-frame object detection to identify accident patterns as they unfold in real time

---
