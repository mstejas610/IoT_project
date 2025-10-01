# 🚀 Installation & Setup Guide

## 📋 Prerequisites

### System Requirements
- **Operating System**: Ubuntu 20.04+ / Raspberry Pi OS / macOS / Windows 10+
- **Python**: 3.9 or higher
- **Memory**: Minimum 4GB RAM (8GB recommended)
- **Storage**: At least 2GB free space
- **Network**: WiFi or Ethernet connectivity

### Hardware Requirements (for full setup)
- **Edge Node**: Raspberry Pi 4B (4GB RAM) or equivalent
- **Sensors**: Temperature, humidity, motion sensors
- **Network**: Router with port forwarding capability
- **Optional**: Arduino for sensor simulation

## 🔧 Installation Steps

### 1. Clone the Repository
```bash
git clone https://github.com/mstejas610/IoT_project.git
cd IoT_project
```

### 2. Set Up Python Virtual Environment
```bash
# Create virtual environment
python3 -m venv iot_env

# Activate virtual environment
# On Linux/macOS:
source iot_env/bin/activate
# On Windows:
iot_env\Scripts\activate
```

### 3. Install Python Dependencies
```bash
# Install all required packages
pip install -r requirements.txt

# Verify installation
python -c "import numpy, pandas, paho.mqtt.client; print('All packages installed successfully!')"
```

### 4. Configure Environment Variables
```bash
# Copy environment template
cp config/env.template config/.env

# Edit configuration (use your preferred editor)
nano config/.env
```

Add your specific settings:
```bash
# MQTT Broker Settings
MQTT_BROKER=localhost
MQTT_PORT=1883
MQTT_USERNAME=your_username
MQTT_PASSWORD=your_password

# Edge Node Configuration
EDGE_NODE_ID=edge_node_001
PROCESSING_INTERVAL=1.0
BATCH_SIZE=100

# Cloud Connection
CLOUD_API_URL=https://your-cloud-endpoint.com/api
CLOUD_API_KEY=your_api_key_here
```

### 5. Set Up MQTT Broker (Local Development)
```bash
# Install Mosquitto MQTT broker
# On Ubuntu:
sudo apt update
sudo apt install mosquitto mosquitto-clients

# On macOS:
brew install mosquitto

# On Windows:
# Download from https://mosquitto.org/download/

# Start MQTT broker
sudo systemctl start mosquitto
sudo systemctl enable mosquitto
```

### 6. Database Setup
```bash
# Create local SQLite database
python scripts/setup_database.py

# Verify database creation
ls -la data/iot_edge.db
```

### 7. Test Installation
```bash
# Run system diagnostics
python scripts/test_installation.py

# Expected output:
# ✅ Python environment: OK
# ✅ Dependencies: OK  
# ✅ MQTT connection: OK
# ✅ Database: OK
# ✅ Configuration: OK
```

## 🎨 Development Setup

### IDE Configuration
**Recommended**: VS Code with extensions:
- Python
- Python Docstring Generator
- GitLens
- MQTT Explorer

### Code Formatting
```bash
# Install development tools
pip install black flake8 mypy

# Format code
black Code/

# Lint code
flake8 Code/

# Type checking
mypy Code/
```

## 🔍 Testing the Setup

### 1. Simulate IoT Sensors
```bash
# Terminal 1: Start edge processing
python Code/edge_computing.py

# Terminal 2: Simulate sensor data
python Code/sensor_simulator.py

# Terminal 3: Monitor MQTT traffic
mosquitto_sub -h localhost -t "iot/sensors/+"
```

### 2. Verify Edge Processing
```bash
# Check edge node logs
tail -f logs/edge_node.log

# Monitor latency metrics
python scripts/monitor_latency.py
```

## 🛍️ Hardware Setup (Physical Deployment)

### Raspberry Pi Configuration
```bash
# Enable I2C and SPI (for sensors)
sudo raspi-config
# Navigate to: Interface Options > I2C > Enable
# Navigate to: Interface Options > SPI > Enable

# Install GPIO libraries
pip install RPi.GPIO gpiozero

# Test GPIO
python -c "from gpiozero import LED; led = LED(2); led.on(); print('GPIO test successful!')"
```

### Sensor Wiring (Example)
```
DHT22 Temperature/Humidity Sensor:
- VCC -> Pin 2 (5V)
- GND -> Pin 6 (Ground)
- DATA -> Pin 7 (GPIO4)

PIR Motion Sensor:
- VCC -> Pin 4 (5V)
- GND -> Pin 9 (Ground)
- OUT -> Pin 11 (GPIO17)
```

## 🚑 Troubleshooting

### Common Issues

**Issue**: MQTT connection failed
```bash
# Solution: Check broker status
sudo systemctl status mosquitto

# Restart if needed
sudo systemctl restart mosquitto
```

**Issue**: Permission denied for GPIO
```bash
# Solution: Add user to gpio group
sudo usermod -a -G gpio $USER
# Log out and log back in
```

**Issue**: Module import errors
```bash
# Solution: Verify virtual environment
which python
pip list

# Reinstall if needed
pip install --force-reinstall -r requirements.txt
```

### Getting Help

1. **Check logs**: `tail -f logs/*.log`
2. **Run diagnostics**: `python scripts/diagnose_system.py`
3. **View system status**: `python scripts/system_status.py`

## 🎆 Next Steps

After successful installation:
1. Review [IoT_requirements.md](IoT_requirements.md) for project specifications
2. Check [Code/](Code/) directory for implementation details
3. Run performance benchmarks: `python scripts/benchmark.py`
4. Set up monitoring dashboard: `python scripts/dashboard.py`

## 📞 Support

For installation issues:
- Create an issue in this repository
- Contact team members listed in README.md
- Check project documentation in `docs/` folder

---

*Installation guide last updated: October 2025*