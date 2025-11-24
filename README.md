# 🌟 **AI-Enabled Digital Twin Framework for SME Industrial Systems**

A low-cost, open-source framework combining **IoT**, **MQTT**, **Node-RED**, **FastAPI**, and **Machine Learning** to create a real-time **AI-driven Digital Twin** for a fan-driven cooling process.

---

<div align="center">

### 🎥 **[Watch Demo Video]([(https://youtu.be/JJkGhe9N9eg?si=Rr-97aHbw2psryBC)])**

### 🖼️ **Architecture Diagram**

<img src="DT Demo.jpg" width="650">

</div>

---

# 🚀 **Overview**

Small and medium-sized manufacturing enterprises (SMEs) struggle with expensive, complex digital twin solutions.
This project provides a **fully open-source**, **AI-enabled**, and **low-cost** digital twin that:

* Simulates real industrial behaviour
* Streams live virtual sensor data
* Computes sustainability metrics (energy, power, CO₂)
* Detects faults and anomalies
* Uses an integrated ML model for **real-time fault classification**
* Shows all behaviour on a rich, interactive **Node-RED dashboard**

It bridges the gap between **Industry 5.0 research** and **practical SME adoption**, offering an end-to-end framework anyone can replicate.

---

# 🧩 **Key Features**

### 🔧 **Virtual Sensor Layer (Arduino UNO R4 WiFi)**

* Simulates temp, rpm, current, vibration
* Injects realistic anomalies (overcurrent, thermal drift, vibration spikes)
* Publishes at 5 Hz using MQTT

### 🔌 **MQTT Communication Layer**

* Lightweight messaging (Mosquitto)
* Ultra-low latency streaming (<75 ms)

### 📊 **Digital Twin (Node-RED Dashboard)**

Interactive real-time dashboard with:

* Gauges for temperature, rpm, current, vibration
* Trend charts
* Energy, power, CO₂ panels
* Efficiency index
* Fault alert panel
* AI intelligence widgets

  * Fault classification
  * Confidence gauge
  * Fault timeline
  * Maintenance recommendations
* Clean CSV logging for AI training

### 🧠 **AI Layer (FastAPI + Random Forest)**

* Trained on 7,800+ labelled samples
* ~95% accuracy (0.97 fault precision)
* Exposed as a REST API endpoint
* Node-RED queries the model in real time
* Returns:

  ```json
  {
    "fault_code": 1,
    "fault_label": "Overcurrent Fault",
    "confidence": 0.92,
    "severity": "High",
    "advice": "Inspect load or worn components."
  }
  ```

---

# 🧱 **System Architecture**

<div align="center">

<img src="DT Architecture.png" width="750">

</div>

---

# 🏗️ **How the System Works**

### 1️⃣ Virtual Sensor

Arduino simulates real process dynamics:

* Temperature model
* Fan-speed controller
* Current draw model
* Vibration profile
* Randomized fault injection

### 2️⃣ Communication

All data published to MQTT → subscribed by Node-RED.

### 3️⃣ Digital Twin Dashboard

Node-RED computes KPIs:

* Power = V × I
* Energy (Wh)
* Cooling rate
* Thermal efficiency index
* CO₂ footprint

### 4️⃣ AI Fault Intelligence

Pipeline:

```
CSV Logging → ML Training (Python) → Random Forest Model → FastAPI Inference → Node-RED Dashboard
```


# 📦 **Repository Contents**

```
📁 digital-twin-mqtt-ai/
│
├── arduino/
│   └── virtual_sensor.ino        # Full simulation firmware for UNO R4 WiFi
│
├── node-red/
│   ├── flows.json                # Complete AI-enabled Node-RED flow
│   └── dashboard_screenshots/
│
├── fastapi/
│   ├── serve_model.py            # FastAPI inference server
│   ├── train_model.py            # ML training pipeline
│   ├── fan_fault_classifier.joblib   # Trained model (optional)
│
├── data/
│   └── fan_digital_twin_log.csv  # Sample dataset
│
├── docs/
│   ├── architecture_diagram.png
│   ├── methodology_overview.png
│   └── system_design_block.png
│
└── README.md                     # This documentation
```

---

# ⚙️ **Installation & Quick Start**

## 🛰️ 1. Clone the Repository

```bash
git clone https://github.com/ogatech4real/digital-twin-mqtt-ai.git
cd digital-twin-mqtt-ai
```

---

## 🔧 2. Flash Arduino UNO R4 WiFi

Upload:

```
arduino/virtual_sensor.ino
```

Set WiFi + MQTT IP.

---

## 🐍 3. Install Python Dependencies

```bash
pip install -r requirements.txt
```

---

## 🚀 4. Start the AI Model Server

```bash
uvicorn serve_model:app --host 0.0.0.0 --port 8000
```

Test:

```
http://localhost:8000/docs
```

---

## 📡 5. Start Mosquitto Broker

```bash
sudo systemctl start mosquitto
```

---

## 🟥 6. Launch Node-RED

```bash
node-red
```

Import `flows.json`.

Access dashboard:

```
http://localhost:1880/ui
```

---

# 🧠 **Training Your Own AI Model**

```bash
python fastapi/train_model.py
```

This will:

* Clean dataset
* Train a Random Forest Classifier
* Print classification report
* Save the model as:

  ```
  fan_fault_classifier.joblib
  ```

---

# 📊 **Results**

### ⚙️ Performance Summary

| Metric           | Value  | Remarks     |
| ---------------- | ------ | ----------- |
| Update Rate      | 5 Hz   | Stable      |
| Latency          | ~72 ms | Low delay   |
| MQTT Packet Loss | <0.02% | Rock solid  |
| Model Accuracy   | 95%    | High        |
| Fault Precision  | 0.97   | Excellent   |
| Stack Cost       | < £50  | Low-cost DT |

---

🎥 Demo Video:

```

https://youtu.be/JJkGhe9N9eg?si=Rr-97aHbw2psryBC

```

---

# 🧭 **Project Roadmap**

### 🚧 Planned Features

* Edge-AI deployment on Raspberry Pi
* Integration with **physical sensors**
* LSTM / TCN models for time-series prediction
* Reinforcement Learning for control optimisation
* Multi-machine DT federation
* Cloud dashboard + mobile app

---

# 🤝 **Contributions**

Contributions are welcome!
Submit a PR or open an issue.

---

# 📜 **License**

MIT License.

---

# 👨‍💻 **Author**

**<img width="1424" height="62" alt="image" src="https://github.com/user-attachments/assets/d9cf09db-23e3-43fe-b90d-5b6725c89e24" />**

School of Computing, Engineering and Digital Technologies

Teesside University, UK

---

