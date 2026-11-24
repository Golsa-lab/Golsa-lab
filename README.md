<p align="center">
  <img src="assets/banner.svg" alt="Golsa Shokri: AI & LLM engineering, full-stack, automation" width="100%">
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/golsa-s-518629303"><img src="https://img.shields.io/badge/LinkedIn-connect-8C1C3A?style=flat-square&logo=linkedin&logoColor=white&labelColor=5E1224" alt="LinkedIn"></a>
  <img src="https://img.shields.io/badge/focus-AI%20engineering-8C1C3A?style=flat-square&labelColor=5E1224" alt="Focus: AI engineering">
</p>

<p align="center"><i>
I build LLM agents that call typed tools instead of making things up,<br>
the full-stack apps around them, and the data pipelines that feed them.
</i></p>

---

### ✦ About

- 🎓 **M.Sc. Automation Engineering** at Politecnico di Milano (2026–), admitted directly after my B.Sc. there (2022–2026)
- 🤖 Main interest: **AI engineering**, meaning LLM agents with tool / function calling, model training and evaluation, and checking results independently
- 🧱 Hands-on full-stack: **Next.js / React / TypeScript**, **PostgreSQL** schemas and SQL, **Python** ETL, **Docker**
- 🔌 Background in control and embedded systems, so I'm comfortable where software meets sensors and actuators

### ✦ Right now

| | |
|:--|:--|
| **InVox** · Polimi Data Science & BEA | AI/ML team on a wearable that helps people with speech impairments communicate. Facial-muscle movements read by motion sensors are classified into intended phrases. I built the training dataset from scratch and the **SVM classifier** in Python (currently a 5-phrase vocabulary). |
| **Leg Aid** · AEA Polimi | Software team for a wearable robotic **exoskeleton**: integration and control logic, mainly in Python. |

---

### ✦ Featured: an LLM agent you can audit

<a href="https://github.com/Golsa-lab/air-quality-mvp"><img src="assets/card-air-quality.svg" alt="Air Quality MVP" width="49%" align="right"></a>

**[Air Quality MVP](https://github.com/Golsa-lab/air-quality-mvp)** analyses ARPA Lombardia air-quality data, and you can ask it
questions in plain Italian.

The model **never sees the database and never writes SQL**. It chooses one of **5 typed tools**. Invalid arguments are
rejected and sent back so the model can correct itself, and every answer shows the tools that produced it.
The dashboard and the agent go through the **same domain layer**, so they cannot give different numbers for the same question.
A separate pandas script recomputes the SQL aggregations from the raw CSVs as an independent check.

<br clear="right">

```mermaid
%%{init: {'theme':'base','themeVariables':{'primaryColor':'#FBF6F7','primaryTextColor':'#1A1A1D','primaryBorderColor':'#8C1C3A','lineColor':'#8C1C3A','secondaryColor':'#F3E3E7','tertiaryColor':'#FFFFFF','fontFamily':'Helvetica, Arial, sans-serif'}}}%%
flowchart LR
    U([question]) --> L[LLM<br/>OpenAI-compatible]
    L -->|picks a tool + args| T{typed tools ×5}
    T -->|invalid args| L
    T --> D[domain layer<br/>single source of truth]
    D --> P[(PostgreSQL)]
    D --> W[dashboard]
    D -->|numbers only| L
    L --> A([answer + tool trace])
```

---

### ✦ Projects

<p align="center">
  <a href="https://github.com/Golsa-lab/iot-nodered"><img src="assets/card-nodered.svg" alt="ZigBee to MQTT to ThingSpeak" width="49%"></a>
  <a href="https://github.com/Golsa-lab/iotChallenge-2--IoTScope-Network-Protocol-Analysis-Platform"><img src="assets/card-iotscope.svg" alt="IoTScope" width="49%"></a>
</p>
<p align="center">
  <a href="https://github.com/Golsa-lab/dc-motor-drive-tramway"><img src="assets/card-dc-motor.svg" alt="DC Motor Drive" width="49%"></a>
  <a href="https://github.com/Golsa-lab/iot-project-wokwi-esp32"><img src="assets/card-iot.svg" alt="Sleepy Sensor Node" width="49%"></a>
</p>
<p align="center">
  <a href="https://github.com/Golsa-lab/OpenExo"><img src="assets/card-openexo.svg" alt="OpenExo fork" width="49%"></a>
</p>

| Project | Highlights |
|:--|:--|
| [**Air Quality MVP**](https://github.com/Golsa-lab/air-quality-mvp) | Next.js + PostgreSQL in Docker, layered architecture, LLM agent with tool calling and self-correction, Python ETL with `COPY` bulk load, duplicate/conflict detection, Vitest |
| [**ZigBee → MQTT → ThingSpeak**](https://github.com/Golsa-lab/iot-nodered) | Node-RED flow over a Dockerised Mosquitto broker: O(1) packet lookup, ZCL attribute mining (RMS V/I, active power), rate-limited ThingSpeak upload, live charts |
| [**IoTScope**](https://github.com/Golsa-lab/iotChallenge-2--IoTScope-Network-Protocol-Analysis-Platform) | CoAP and MQTT-SN analysis of raw `.pcapng` captures with Python + tshark, plus a verification script for every answer |
| [**DC Motor Drive**](https://github.com/Golsa-lab/dc-motor-drive-tramway) | Cascade PI speed/current control, field weakening, variable torque limit, anti-windup, gravity feed-forward (MATLAB/Simulink) |
| [**Sleepy Sensor Node**](https://github.com/Golsa-lab/iot-project-wokwi-esp32) | ESP32 + PIR + LDR, ESP-NOW broadcast, timer deep sleep, per-phase `micros()` timing |
| [**OpenExo** (fork)](https://github.com/Golsa-lab/OpenExo) | Fork of the open-source exoskeleton platform (Teensy firmware, Python GUI, apps) |

<details>
<summary><b>Not on GitHub (yet)</b></summary>
<br>

- **AutoPrice Analyzer** (group project, PyTorch). A multi-branch network that assigns a car to a price band from its image and attributes. I wrote the **feature sub-network**, a fully-connected regressor on make, fuel, year, km and gearbox, trained with MSE + Adam.
- **Wearable denture locator**. Event-driven **BLE** firmware with a wake-on-motion state machine. I modelled 24-hour power consumption and IEEE 802.15.4 / frame-slotted ALOHA efficiency.

</details>

---

### ✦ Toolbox

<p>
  <b>AI / ML</b>&nbsp;
  <img src="https://img.shields.io/badge/LLM%20tool%20calling-FBF6F7?style=flat-square" alt="LLM tool calling">
  <img src="https://img.shields.io/badge/PyTorch-FBF6F7?style=flat-square&logo=pytorch&logoColor=8C1C3A" alt="PyTorch">
  <img src="https://img.shields.io/badge/SVM-FBF6F7?style=flat-square" alt="SVM">
  <img src="https://img.shields.io/badge/pandas-FBF6F7?style=flat-square&logo=pandas&logoColor=8C1C3A" alt="pandas">
</p>
<p>
  <b>Languages</b>&nbsp;
  <img src="https://img.shields.io/badge/Python-FBF6F7?style=flat-square&logo=python&logoColor=8C1C3A" alt="Python">
  <img src="https://img.shields.io/badge/TypeScript-FBF6F7?style=flat-square&logo=typescript&logoColor=8C1C3A" alt="TypeScript">
  <img src="https://img.shields.io/badge/Java-FBF6F7?style=flat-square&logo=openjdk&logoColor=8C1C3A" alt="Java">
  <img src="https://img.shields.io/badge/C%20%2F%20C%2B%2B-FBF6F7?style=flat-square&logo=cplusplus&logoColor=8C1C3A" alt="C / C++">
  <img src="https://img.shields.io/badge/SQL-FBF6F7?style=flat-square&logo=postgresql&logoColor=8C1C3A" alt="SQL">
  <img src="https://img.shields.io/badge/MATLAB-FBF6F7?style=flat-square" alt="MATLAB">
</p>
<p>
  <b>Web &amp; data</b>&nbsp;
  <img src="https://img.shields.io/badge/Next.js-FBF6F7?style=flat-square&logo=nextdotjs&logoColor=8C1C3A" alt="Next.js">
  <img src="https://img.shields.io/badge/React-FBF6F7?style=flat-square&logo=react&logoColor=8C1C3A" alt="React">
  <img src="https://img.shields.io/badge/Node.js-FBF6F7?style=flat-square&logo=nodedotjs&logoColor=8C1C3A" alt="Node.js">
  <img src="https://img.shields.io/badge/PostgreSQL-FBF6F7?style=flat-square&logo=postgresql&logoColor=8C1C3A" alt="PostgreSQL">
  <img src="https://img.shields.io/badge/REST%20APIs-FBF6F7?style=flat-square" alt="REST APIs">
</p>
<p>
  <b>DevOps</b>&nbsp;
  <img src="https://img.shields.io/badge/Docker%20Compose-FBF6F7?style=flat-square&logo=docker&logoColor=8C1C3A" alt="Docker">
  <img src="https://img.shields.io/badge/Linux-FBF6F7?style=flat-square&logo=ubuntu&logoColor=8C1C3A" alt="Linux">
  <img src="https://img.shields.io/badge/Git-FBF6F7?style=flat-square&logo=git&logoColor=8C1C3A" alt="Git">
  <img src="https://img.shields.io/badge/Vitest-FBF6F7?style=flat-square&logo=vitest&logoColor=8C1C3A" alt="Vitest">
</p>
<p>
  <b>IoT &amp; embedded</b>&nbsp;
  <img src="https://img.shields.io/badge/ESP32-FBF6F7?style=flat-square&logo=espressif&logoColor=8C1C3A" alt="ESP32">
  <img src="https://img.shields.io/badge/MQTT-FBF6F7?style=flat-square&logo=mqtt&logoColor=8C1C3A" alt="MQTT">
  <img src="https://img.shields.io/badge/Node--RED-FBF6F7?style=flat-square&logo=nodered&logoColor=8C1C3A" alt="Node-RED">
  <img src="https://img.shields.io/badge/BLE%20·%20ESP--NOW-FBF6F7?style=flat-square" alt="BLE, ESP-NOW">
  <img src="https://img.shields.io/badge/Simulink-FBF6F7?style=flat-square" alt="Simulink">
</p>

---

<p align="center">
  <sub>🇮🇹 Italian C2 · 🇬🇧 English C1 · 🇩🇪 German A1</sub><br>
  <sub>Politecnico di Milano · Milano / Brescia</sub>
</p>
