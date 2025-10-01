# 🌆 Smart City IoT Edge Computing Project

![IoT](https://img.shields.io/badge/IoT-Edge_Computing-blue?style=for-the-badge)
![Smart City](https://img.shields.io/badge/Smart_City-Architecture-green?style=for-the-badge)
![Latency](https://img.shields.io/badge/Focus-Latency_Reduction-orange?style=for-the-badge)

## 📋 Project Overview

**Implementing Edge Computing in Smart City IoT Architectures for Latency Reduction**

This project focuses on developing and implementing edge computing solutions to reduce latency in smart city IoT systems. By processing data closer to the source, we aim to improve response times, reduce bandwidth usage, and enhance overall system performance for critical smart city applications.

## 👥 Team Members

| Name | Roll Number | Role |
|------|-------------|------|
| **Mareddy Sai Tejas** | CB.EN.U4CYS22038 | Team Lead & System Architecture |
| **Marri Sanju** | CB.EN.U4CYS22039 | Edge Computing Implementation |
| **Tangella Sree Chandan** | CB.EN.U4CYS22076 | IoT Sensor Integration & Testing |

## 🎯 Project Objectives

- **Primary Goal**: Reduce latency in smart city IoT networks through edge computing
- **Secondary Goals**:
  - Optimize bandwidth usage
  - Improve real-time decision making
  - Enhance system scalability
  - Implement fault-tolerant edge nodes

## 🏗️ System Architecture

```
Smart City IoT Architecture
┌─────────────────────────────────────────────────┐
│                Cloud Layer                      │
│  ┌─────────────┐ ┌─────────────┐ ┌───────────┐ │
│  │   Storage   │ │  Analytics  │ │    ML     │ │
│  └─────────────┘ └─────────────┘ └───────────┘ │
└─────────────────┬───────────────────────────────┘
                  │ High Latency Path
┌─────────────────▼───────────────────────────────┐
│                Edge Layer                       │
│  ┌─────────────┐ ┌─────────────┐ ┌───────────┐ │
│  │Edge Node 1  │ │Edge Node 2  │ │Edge Node N│ │
│  │Processing   │ │Processing   │ │Processing │ │
│  └─────────────┘ └─────────────┘ └───────────┘ │
└─────────────────┬───────────────────────────────┘
                  │ Low Latency Path  
┌─────────────────▼───────────────────────────────┐
│              Device Layer                       │
│  🌡️Sensors   📹Cameras   🚦Traffic   💡Lights  │
│  📊Meters    🔊Audio     🚨Alarms    📱Mobile   │
└─────────────────────────────────────────────────┘
```

## 💻 Technology Stack

- **Programming Language**: Python 3.9+
- **Edge Computing**: MQTT, Edge Processing Algorithms
- **IoT Protocols**: MQTT, CoAP, HTTP/HTTPS
- **Data Processing**: NumPy, Pandas
- **Networking**: Socket Programming, REST APIs
- **Hardware**: Raspberry Pi, Arduino (simulated)
- **Database**: SQLite (edge), MongoDB (cloud)
- **Visualization**: Matplotlib, Plotly

## 🎓 Academic Context

- **Course**: 6th Semester Project
- **Institution**: Amrita Vishwa Vidyapeetham
- **Department**: Cybersecurity Engineering
- **Academic Year**: 2024-2025

## 📁 Repository Structure

```
IoT_project/
├── README.md                 # This file
├── Code/                     # Implementation code
├── IoT_requirements.md       # Project requirements
├── Meetings_1.md            # Meeting notes and progress
├── data/                    # Sample data and logs
├── docs/                    # Additional documentation
├── tests/                   # Unit tests
└── config/                  # Configuration files
```

## 🚀 Quick Start

1. **Clone the repository**:
   ```bash
   git clone https://github.com/mstejas610/IoT_project.git
   cd IoT_project
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the edge computing simulation**:
   ```bash
   python Code/edge_computing.py
   ```

## 📊 Expected Outcomes

- **Latency Reduction**: 60-80% improvement in response times
- **Bandwidth Optimization**: 40-50% reduction in cloud traffic
- **System Reliability**: 99.5% uptime for critical services
- **Scalability**: Support for 1000+ concurrent IoT devices

## 🤝 Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on how to contribute to this project.

## 📄 License

This project is licensed under the MIT License - see [LICENSE](LICENSE) file for details.

---

*Last updated: October 2025 | Built for academic research in IoT edge computing*