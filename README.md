
---

# 🌟 **AI-Enabled Digital Twin Framework for SME Industrial Systems**

A low-cost, open-source framework combining **IoT**, **MQTT**, **Node-RED**, **FastAPI**, and **Machine Learning** to create a real-time **AI-driven Digital Twin** for a fan-driven cooling process.

---

<div align="center">

<a href="https://youtu.be/JJkGhe9N9eg?si=Rr-97aHbw2psryBC">
  <img src="DT Demo.jpg" width="700" alt="Digital Twin Demo Video">
</a>

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

* Simulates temperature, rpm, current, vibration
* Injects realistic anomalies (overcurrent, thermal drift, vibration spikes)
* Publishes sensor data at 5 Hz using MQTT

### 🔌 **MQTT Communication Layer**

* Lightweight Mosquitto broker
* Ultra-low latency streaming (<75 ms)

### 📊 **Digital Twin (Node-RED Dashboard)**

Real-time interactive dashboard with:

* Gauges for temperature, rpm, current, vibration
* Trend charts for all process variables
* Power, energy, CO₂, and efficiency indicators
* Fault alert & system status
* AI intelligence widgets:

  * Fault classification
  * Confidence gauge
  * Fault timeline
  * Maintenance recommendations
* Clean CSV logging for AI dataset creation (20-min windows)

### 🧠 **AI Layer (FastAPI + Random Forest)**

* Trained on 7,800+ labelled samples
* ~95% accuracy (0.97 fault precision)
* Exposed as a REST API endpoint
* Node-RED queries model in real time
* Expected API response:

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

<img src="DT Architecture.png" width="750" alt="Digital Twin Architecture Diagram">

</div>

---

# 🏗️ **How the System Works**

### 1️⃣ Virtual Sensor

Arduino simulates industrial process dynamics:

* Temperature evolution
* Fan-speed closed-loop controller
* Electrical load/current behaviour
* Vibration profile
* Randomised fault injection

### 2️⃣ Communication

Data is published to MQTT and subscribed by Node-RED.

### 3️⃣ Digital Twin Dashboard

Node-RED computes key KPIs:

* Power (W)
* Energy (Wh)
* Cooling rate
* Thermal efficiency index
* Carbon footprint

### 4️⃣ AI Fault Intelligence

Integrated machine learning pipeline:

```
CSV Logging → ML Training (Python) → Random Forest Model → FastAPI Inference → Node-RED Dashboard
```


---

# 📊 **Results**

### ⚙️ Performance Summary

| Metric           | Value  | Remarks       |
| ---------------- | ------ | ------------- |
| Update Rate      | 5 Hz   | Stable        |
| Latency          | ~72 ms | Low delay     |
| MQTT Packet Loss | <0.02% | Excellent     |
| Model Accuracy   | 95%    | Strong result |
| Fault Precision  | 0.97   | Excellent     |
| Stack Cost       | < £50  | Very low-cost |

---

# 🎥 POSTER PRESENTATION


<div align="center">

<img src="Issmat DT Poster.png" width="750" alt="Poster Presentation">

</div>


---

# 🧭 **Project Roadmap**

### 🚧 Planned Enhancements

* Edge-AI deployment (Raspberry Pi)
* Integration with physical sensors
* LSTM/TCN for time-series fault prediction
* Reinforcement Learning for optimisation
* Multi-machine digital twin federation
* Cloud dashboard & mobile app

---

# 🤝 **Contributions**

Contributions are welcome — submit a PR or open an issue!

---

# 📜 **License**

MIT License.

---

# 👨‍💻 **Author**

<div align="left">

<img width="600" src="https://github.com/user-attachments/assets/d9cf09db-23e3-43fe-b90d-5b6725c89e24" alt="Author Signature"/>

**School of Computing, Engineering and Digital Technologies**
Teesside University, UK

</div>

---
