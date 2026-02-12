# Lab 05: Ignition Automation Platform Installation
**MFET 37400-002 - Spring 2026**

---

## Overview

In this lab you will install the **Ignition Automation platform** to a Raspberry Pi. The Ignition platform is an example of a new form of Industrial Automation software which allows for the mixing of multiple OT (Operational Technology) and IT (Information Technology) technologies in a single development environment. This reduces the traditional requirements for specific industrial devices for specific tasks. With platforms such as Ignition, data ingestion, control, storage, and visualization can all be done within a standard computing device.

### Lab Structure
- **L05-1**: Installing Ignition (20 pts)
- **L05-2**: Getting Started with Ignition (30 pts)
- **L05-3**: OPC UA and Devices (30 pts)
- **L05-4**: Navigating Ignition Demos (20 pts)

**Total Points: 100**

---

## Prerequisites

### Required Equipment
- Raspberry Pi Model 4 (8 GB RAM)
- MicroSD card with Raspberry Pi OS installed
- Internet connection (WiFi or Ethernet)
- Monitor, keyboard, and mouse (or SSH/VNC access)

### Lab WiFi Credentials
- **SSID**: `soetmfg`
- **Password**: `MFETis4Me`

### Resources
- [Introduction to Ignition](https://inductiveautomation.com/ignition/)
- [Inductive University](https://www.inductiveuniversity.com/)
- [Ignition Download Site](https://inductiveautomation.com/downloads/)
- [Ignition Demo Site](https://cloud.inductiveautomation.com/demo)

---

## L05-1: Installing Ignition (20 pts)

### Objective
Install Java runtime and the Ignition Edge Gateway on your Raspberry Pi.

---

### Step 1: Install Java (OpenJDK)

Ignition requires Java to run. We'll install OpenJDK using the Debian package manager.

1. **Open Terminal**
   - Press `Ctrl + Alt + T` or click the terminal icon

2. **Update Package Lists**
   ```bash
   sudo apt update
   ```

3. **Install OpenJDK 17** (Recommended for Ignition 8.1+)
   ```bash
   sudo apt install openjdk-17-jdk -y
   ```

4. **Verify Java Installation**
   ```bash
   java -version
   ```

   Expected output:
   ```
   openjdk version "17.x.x"
   ```

**Note**: The Debian pull instruction set appears to work for most students. If you encounter issues, try OpenJDK 11 instead:
```bash
sudo apt install openjdk-11-jdk -y
```

---

### Step 2: Download Ignition Edge

1. **Navigate to Downloads Directory**
   ```bash
   cd ~/Downloads
   ```

2. **Download Ignition Edge for Linux ARM**

   Visit the [Ignition Download Site](https://inductiveautomation.com/downloads/) and download:
   - **Ignition - Linux AARCH64.zip** (for Raspberry Pi ARM architecture)

   Alternatively, use `wget` if you have the direct link:
   ```bash
   wget https://files.inductiveautomation.com/release/ia/8.1.45/Ignition-linux-aarch-64-8.1.45.zip
   ```

   **Note**: Version number may vary. Use the latest stable release.

---

### Step 3: Extract and Install Ignition

1. **Extract the Archive**
   ```bash
   unzip Ignition-linux-aarch-64-8.1.45.zip
   ```

   This creates a directory with installation files.

2. **Navigate to the Extracted Directory**
   ```bash
   cd Ignition-linux-aarch-64-8.1.45
   ```

   (Replace with actual extracted folder name)

3. **Make Installation Script Executable**
   ```bash
   sudo chmod +x *.sh
   ```

4. **Install and Start Ignition Gateway**
   ```bash
   sudo ./ignition.sh installstart
   ```

   This command will:
   - Install Ignition as a service
   - Start the Ignition Gateway automatically
   - Configure it to start on boot

---

### Step 4: Access the Ignition Gateway

1. **Open Web Browser** on the Raspberry Pi

2. **Navigate to Gateway URL**
   ```
   http://localhost:8088/web/home
   ```

3. **Complete Initial Setup**
   - Follow the on-screen instructions
   - Choose gateway configuration options
   - Set up authentication

4. **Login to Gateway**
   - **Username**: `admin`
   - **Password**: `password` (default - change after first login!)

---

### Step 5: Verify Installation

**Checkoff Requirements:**
- [ ] Java is installed and version displayed
- [ ] Ignition Gateway is running
- [ ] Web interface accessible at `http://localhost:8088`
- [ ] Successfully logged into Gateway homepage

**Raise your hand to demonstrate your progress to the lab instructor.**

---

## L05-2: Getting Started with Ignition (30 pts)

### Objective
Learn the fundamentals of Ignition platform through Inductive University training modules.

---

### Step 1: Create Inductive University Account

1. **Navigate to Inductive University**
   - URL: [https://www.inductiveuniversity.com/](https://www.inductiveuniversity.com/)

2. **Create Account** (if you don't have one)
   - Click "Sign Up"
   - Enter your information
   - Use your Purdue email for verification
   - Activate your account

3. **Login** to your account

---

### Step 2: Complete Ignition Basics Course

1. **Navigate to Course Catalog**

2. **Select "Ignition Basics"**

   This course covers:
   - Ignition Platform Overview
   - Gateway architecture
   - Designer workspace
   - Tag system fundamentals
   - Basic project creation

3. **Complete ALL Course Elements**
   - Watch all video modules
   - Review all documentation
   - Complete hands-on exercises
   - Take all Topic Challenges

---

### Step 3: Topic Challenges

**Important Requirements:**
- Take **ALL Topic Challenges** in the Ignition Basics course
- **100% score required** to proceed
- Retake challenges until you achieve mastery
- Each challenge must show 100% before moving to next topic

**Learning Strategy:**
- Take notes during videos
- Review documentation before challenges
- Use the Ignition Designer to practice concepts
- Don't rush - understanding is more important than speed

---

### Step 4: Optional Certification

**Ignition Core Certification**
- There is a certification available upon course completion
- **Highly recommended** for your resume
- Demonstrates proficiency with Ignition platform
- Free through Inductive University
- Complete on your own time for professional development

---

### Step 5: Demonstrate Completion

**Checkoff Requirements:**
- [ ] Inductive University account created
- [ ] All Ignition Basics modules completed
- [ ] All Topic Challenges passed with 100%
- [ ] Course progress visible on dashboard

**Show your completion status to the lab instructor to receive credit.**

---

## L05-3: OPC UA and Devices (30 pts)

### Objective
Learn about OPC UA protocol and device connectivity in Ignition through structured training.

---

### What is OPC UA?

**OPC Unified Architecture (OPC UA)** is an industrial communication protocol that:
- Provides secure, reliable data exchange
- Enables cross-platform communication
- Supports complex data structures
- Is vendor-independent and standardized
- Used extensively in IIoT (Industrial Internet of Things)

Ignition uses OPC UA as its primary protocol for device connectivity.

---

### Step 1: Access Ignition Gateway Setup Course

1. **Navigate to Course Catalog** in Inductive University

2. **Select "Ignition Gateway Setup"**

3. **Find "OPC-UA and Devices in Ignition" Sub-section**

---

### Step 2: Complete First Two Elements

Complete the following modules:

#### Module 1: OPC UA Overview
- OPC UA fundamentals
- Client-server architecture
- Security concepts
- Data modeling

#### Module 2: Device Connections in Ignition
- Adding OPC UA devices
- Driver configuration
- Tag browsing
- Connection diagnostics

---

### Step 3: Topic Challenges

**Requirements:**
- Take **ALL Topic Challenges** for the first two elements
- **100% score required** for each challenge
- Do not proceed until mastery achieved
- Review material as needed

**Topics Covered:**
- OPC UA addressing
- Device connection parameters
- Tag structure and naming
- Troubleshooting connectivity

---

### Step 4: Practical Understanding

**Key Concepts to Master:**
- How Ignition discovers OPC UA devices
- Configuring device connections
- Browsing and importing tags
- Testing device connectivity
- Understanding connection status

---

### Step 5: Demonstrate Completion

**Checkoff Requirements:**
- [ ] First two OPC UA modules completed
- [ ] All Topic Challenges passed with 100%
- [ ] Can explain OPC UA role in Ignition
- [ ] Progress visible in course dashboard

**Show completion to the lab instructor to receive credit.**

---

## L05-4: Navigating Ignition Demos (20 pts)

### Objective
Explore real-world Ignition applications and design a theoretical application based on your experiences.

---

### Step 1: Access Ignition Demo Site

1. **Navigate to Demo Site**
   - URL: [https://cloud.inductiveautomation.com/demo](https://cloud.inductiveautomation.com/demo)

2. **Login as Operator**
   - **Username**: `operator`
   - **Password**: `password`

3. **Explore the Interface**
   - Note the navigation structure
   - Observe the different application types
   - Understand the layout and design patterns

---

### Step 2: Explore One Feature

**Choose ONE feature to explore in depth:**

Examples of features:
- **Tag History**: Historical data logging and trending
- **Alarming**: Alarm management and notification
- **Reporting**: Automated report generation
- **Scheduling**: Production scheduling tools
- **Mobile**: Mobile-responsive interfaces
- **Security**: User management and permissions

**Exploration Tasks:**
1. Navigate to the feature
2. Interact with all available controls
3. Understand the data flow
4. Note the UI/UX design patterns
5. Consider real-world applications

**Document:**
- Feature name
- Primary purpose
- Key capabilities
- User interaction methods
- Data visualization techniques

---

### Step 3: Explore One Demo App

**Choose ONE demo application:**

Examples of demo apps:
- **Manufacturing Execution System (MES)**
- **Process Control Dashboard**
- **Warehouse Management**
- **Energy Monitoring**
- **Quality Assurance Tracking**
- **Asset Management**

**Exploration Tasks:**
1. Understand the application's purpose
2. Navigate through all screens
3. Identify data sources and I/O
4. Note the workflow structure
5. Observe integration points

**Document:**
- App name and purpose
- Industry/sector application
- Key screens and their functions
- Data inputs and outputs
- Automation logic observed

---

### Step 4: Design Your Theoretical Application

Create a theoretical Ignition application based on your own experiences and interests.

**Application Design Requirements:**

#### 1. Application Concept
- **Name**: Give your application a descriptive name
- **Purpose**: What problem does it solve?
- **Industry**: What sector is it for?
- **Users**: Who will use it and how?

#### 2. Dashboard Design
Create sketches/drawings of your dashboards:
- **Main Dashboard**: Overview screen layout
- **Detail Screens**: Specific monitoring/control views
- **Navigation**: How users move between screens
- **Widgets**: Charts, gauges, indicators, buttons
- **Color Scheme**: Status indicators and branding

**Drawing Tools:**
- Paper and pencil (photograph or scan)
- Digital drawing (tablet, whiteboard app)
- Mockup software (Figma, draw.io, PowerPoint)

#### 3. I/O Specification

**Inputs (from devices/sensors):**
- List all data inputs needed
- Specify data types (analog, digital, string)
- Identify update rates
- Examples:
  - Temperature sensors (analog, 0-100°C, 1 Hz)
  - Conveyor status (digital, ON/OFF, on change)
  - Barcode scanner (string, product ID, event-driven)

**Outputs (to devices/actuators):**
- List all control outputs
- Specify command types
- Identify control methods
- Examples:
  - Motor start/stop (digital, momentary)
  - Valve position (analog, 0-100%, continuous)
  - Status lights (digital, ON/OFF, persistent)

#### 4. Protocols and Communication

**Specify protocols for each device category:**
- **OPC UA**: Industrial devices with native OPC support
- **Modbus TCP/RTU**: PLCs and legacy equipment
- **MQTT**: IoT sensors and cloud integration
- **Database**: SQL for data storage and retrieval
- **REST API**: External system integration

**Example:**
```
- PLC (Allen-Bradley): OPC UA over Ethernet
- Temperature sensors: Modbus TCP, IP: 192.168.1.50
- Cloud analytics: MQTT broker at cloud.example.com
- Historical database: PostgreSQL on local server
```

#### 5. System Architecture Diagram

Include a simple architecture drawing showing:
- Devices/sensors (lowest level)
- Communication protocols
- Ignition Gateway (middle)
- Clients/displays (top level)
- External systems (databases, cloud, ERP)

---

### Step 5: Prepare Your Presentation

**Be ready to explain:**

1. **Application Overview** (1-2 minutes)
   - What it does
   - Who uses it
   - Why it's valuable

2. **Dashboard Walkthrough** (2-3 minutes)
   - Show your drawings
   - Explain each screen's purpose
   - Describe user interactions

3. **Technical Architecture** (2-3 minutes)
   - I/O points and data flow
   - Protocols and connectivity
   - Integration points

4. **Real-World Relevance** (1 minute)
   - Based on your experience where?
   - What existing system could this replace/improve?
   - What challenges might you face in implementation?

---

### Step 6: Demonstrate to TA

**Checkoff Requirements:**
- [ ] Explored one feature in demo site
- [ ] Explored one demo app thoroughly
- [ ] Created application concept document
- [ ] Drew dashboard mockups (at least 2 screens)
- [ ] Specified I/O requirements
- [ ] Identified protocols for communication
- [ ] Prepared architecture diagram
- [ ] Can clearly explain application to TA

**Summon your TA and present your theoretical application to receive a checkoff.**

---

## Application Design Examples

### Example 1: Home Brewing Automation

**Concept**: Automate temperature control and monitoring for home brewing operations.

**Dashboards:**
- Main: Current batch overview, temperature trends, timer
- Detail: Recipe manager, historical batch comparison
- Control: Manual overrides, setpoint adjustments

**I/O:**
- Inputs: Temperature sensors (4x, analog), flow meters (2x, pulse), level switches (3x, digital)
- Outputs: Heating element control (PWM), pump control (2x, ON/OFF), solenoid valves (3x, ON/OFF)

**Protocols:**
- Arduino with Modbus RTU for sensors/actuators
- Local SQLite database for recipes and history
- Mobile app connection via Ignition Perspective

---

### Example 2: Greenhouse Environmental Control

**Concept**: Monitor and control greenhouse climate for optimal plant growth.

**Dashboards:**
- Main: Environmental overview (temp, humidity, CO2, light)
- Zones: Individual zone control (8 greenhouse zones)
- Analytics: Growth trends, energy usage, harvest predictions

**I/O:**
- Inputs: Temp/humidity sensors (8x, I2C), CO2 sensors (2x, analog), light sensors (8x, analog), soil moisture (16x, analog)
- Outputs: HVAC controls (analog dampers, fan VFDs), irrigation valves (16x, digital), shade curtains (8x, analog position), supplemental lighting (8x, dimming)

**Protocols:**
- Raspberry Pi I2C for local sensors
- Modbus TCP for HVAC controllers
- OPC UA for irrigation PLC
- Weather API (REST) for forecast data
- Cloud database (MQTT) for analytics

---

### Example 3: 3D Printer Farm Management

**Concept**: Monitor and manage multiple 3D printers for production efficiency.

**Dashboards:**
- Farm Overview: Status of all printers, queue management
- Printer Detail: Individual printer metrics, camera feed
- Production: Job scheduling, material tracking, quality logs

**I/O:**
- Inputs: Printer status (OctoPrint API), filament sensors, temperature sensors, print completion signals
- Outputs: Print job dispatch, emergency stop, enclosure heaters

**Protocols:**
- REST API to OctoPrint instances
- MQTT for printer telemetry
- USB cameras for monitoring
- MySQL database for job history

---

## Troubleshooting

### Ignition Won't Start

**Symptoms**: Gateway service fails to start

**Solutions:**
1. Check Java installation:
   ```bash
   java -version
   ```
2. Verify service status:
   ```bash
   sudo systemctl status ignition
   ```
3. Check logs:
   ```bash
   tail -f /var/log/ignition/wrapper.log
   ```
4. Restart service:
   ```bash
   sudo systemctl restart ignition
   ```

---

### Cannot Access Gateway Web Interface

**Symptoms**: Browser cannot connect to localhost:8088

**Solutions:**
1. Verify Ignition is running:
   ```bash
   sudo systemctl status ignition
   ```
2. Check port 8088 is listening:
   ```bash
   sudo netstat -tlnp | grep 8088
   ```
3. Try IP address instead:
   ```bash
   hostname -I
   ```
   Then navigate to `http://<IP_ADDRESS>:8088`
4. Check firewall:
   ```bash
   sudo ufw status
   ```

---

### Inductive University Videos Not Playing

**Solutions:**
- Update browser to latest version
- Enable JavaScript
- Disable browser extensions (ad blockers)
- Try different browser (Chromium, Firefox)
- Check internet connectivity

---

### Gateway Performance Issues

**Solutions:**
- Check Raspberry Pi memory usage:
  ```bash
  free -h
  ```
- Monitor CPU temperature:
  ```bash
  vcgencmd measure_temp
  ```
- Ensure adequate cooling
- Close unnecessary applications
- Consider upgrading to 8GB RAM model

---

## Key Concepts Summary

### Ignition Platform Components

1. **Gateway**
   - Central server component
   - Runs on Java
   - Manages connections, tags, projects
   - Web-based configuration

2. **Designer**
   - Development environment
   - WYSIWYG interface builder
   - Scripting and logic editor
   - Launches from Gateway

3. **Clients**
   - Vision: Desktop HMI client
   - Perspective: Web/mobile client
   - Voice: Alexa integration

### Ignition Architecture

```
┌─────────────────────────────────────────┐
│         Clients (Vision/Perspective)     │
│         User Interfaces & Displays       │
└────────────────┬────────────────────────┘
                 │ HTTP/WebSocket
┌────────────────▼────────────────────────┐
│         Ignition Gateway                 │
│  • Tag Engine  • Scripting  • Projects  │
│  • Alarming    • Reporting  • Security  │
└────────┬───────────────┬─────────────────┘
         │ OPC UA        │ SQL/JDBC
┌────────▼──────┐   ┌────▼─────────────────┐
│   Devices     │   │   Databases          │
│   PLCs        │   │   Historians         │
│   Sensors     │   │   ERP Systems        │
└───────────────┘   └──────────────────────┘
```

### OPC UA Benefits

- **Unified**: Single protocol for all device types
- **Architecture**: Platform and vendor independent
- **Secure**: Built-in encryption and authentication
- **Scalable**: From single device to enterprise
- **Semantic**: Self-describing data models

---

## Additional Resources

### Documentation
- [Ignition User Manual](https://docs.inductiveautomation.com/)
- [Scripting Functions Reference](https://docs.inductiveautomation.com/display/DOC81/Scripting+Functions)
- [OPC UA Specification](https://opcfoundation.org/developer-tools/specifications-unified-architecture)

### Community
- [Ignition Forum](https://forum.inductiveautomation.com/)
- [Inductive Automation YouTube](https://www.youtube.com/user/InductiveAutomation)

### Training
- [Inductive University](https://www.inductiveuniversity.com/)
- [ICC 2024 Videos](https://www.inductiveautomation.com/icc)

---

## Lab Completion Checklist

### L05-1: Installing Ignition (20 pts)
- [ ] Java (OpenJDK) installed successfully
- [ ] Ignition Edge downloaded
- [ ] Ignition installed and service running
- [ ] Gateway accessible via web browser
- [ ] Logged into Gateway with admin credentials
- [ ] **Instructor checkoff received**

### L05-2: Getting Started (30 pts)
- [ ] Inductive University account created
- [ ] Ignition Basics course accessed
- [ ] All course modules completed
- [ ] All Topic Challenges passed at 100%
- [ ] Course progress demonstrates completion
- [ ] **Instructor checkoff received**

### L05-3: OPC UA and Devices (30 pts)
- [ ] Gateway Setup course accessed
- [ ] OPC UA module 1 completed
- [ ] OPC UA module 2 completed
- [ ] Topic Challenges for both modules passed at 100%
- [ ] Can explain OPC UA functionality
- [ ] **Instructor checkoff received**

### L05-4: Demo Navigation (20 pts)
- [ ] Logged into Ignition demo site
- [ ] Explored and documented one feature
- [ ] Explored and documented one demo app
- [ ] Designed theoretical application concept
- [ ] Created dashboard mockups (minimum 2)
- [ ] Specified I/O requirements
- [ ] Identified communication protocols
- [ ] Prepared architecture diagram
- [ ] Successfully presented to TA
- [ ] **TA checkoff received**

---

## Submission Notes

**No formal submission required** - this lab is checkoff-based.

All credit is awarded upon successful demonstration to lab instructor or TA.

**Total Lab Points: 100**

---

*Lab Guide Created: February 2026*
*Course: MFET 37400-002 - Manufacturing Integration*
*Institution: Purdue University*
