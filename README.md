# VOLT-IQ ⚡
 
AI-powered classroom energy-waste detection and smart energy monitoring system.
 
## 📌 About the Project
 
VOLT-IQ is a smart classroom energy monitoring project designed to identify unnecessary electricity usage when a classroom is unoccupied, using live computer-vision occupancy detection combined with a rule-based decision engine.
 
## 🎯 Problem Statement
 
Electrical appliances such as lights, fans, and projectors may remain switched on even when classrooms are empty. This leads to unnecessary energy consumption and avoidable electricity costs for institutions.
 
## 💡 Proposed Solution
 
VOLT-IQ monitors classroom occupancy (via webcam-based AI person detection) and appliance status (via sensor simulation / IoT telemetry). When a classroom is empty while an appliance is ON, the system detects possible energy wastage, estimates the wattage wasted, and generates a severity-ranked alert.
 
## ✅ Current Features
 
- Live AI occupancy detection (TensorFlow.js COCO-SSD person detection via webcam)
- "Toggle Test Crowd" simulation mode for testing without a physical camera
- Multi-classroom management (add / remove classrooms)
- Per-classroom appliance sensors: Light, Fan, Projector (simulated, with configurable wattage)
- Rule-based Decision Engine: `Occupancy == EMPTY AND any appliance == ON → ENERGY WASTE`
- Real-time dashboard (classrooms, occupied/empty counts, active alerts, wasted load)
- Power analytics: total connected load, wasted load, % wasted
- Alert system with severity levels and clear/turn-off actions
- Fully responsive dark-theme UI
## 🧪 Testing & Error Handling
 
Since VOLT-IQ runs entirely in the browser at this stage (no backend yet), testing and error handling currently focus on the client-side pipeline:
 
- **Camera permission denied / unavailable:** if `getUserMedia` fails or is blocked, the UI falls back to "Camera Idle" state and the user can switch to **Toggle Test Crowd** mode to exercise the full detection → decision → alert pipeline without a physical camera. This was the primary manual test path used to validate the Decision Engine logic.
- **No appliances ON / room empty:** verified that the Decision Engine correctly returns `NORMAL` (no false-positive alerts) when occupancy is EMPTY but all appliance sensors are OFF.
- **Room occupied with appliances ON:** verified that the Decision Engine correctly returns `NORMAL` (not flagged as waste) when occupancy is OCCUPIED, confirming the rule checks occupancy *and* load together, not appliance state alone.
- **Add/Delete classroom edge cases:** manually tested that deleting a classroom also removes its associated camera binding and any pending alerts for that room, and that newly added classrooms initialize with all appliances OFF and occupancy EMPTY by default.
- **Known limitation:** formal automated unit tests (e.g. Jest) are not yet integrated; current validation is manual/scenario-based. Automated test coverage for the Decision Engine's rule logic is planned as the next testing milestone.
## 🗂️ Data Model
 
VOLT-IQ does not yet use a persistent database — classroom and alert state are held in-memory on the client for this stage. The core data structures are:
 
```json
// Classroom object
{
  "101": {
    "name": "Room 101",
    "location": "Science Lab",
    "occupied": false,
    "appliances": {
      "light": false,
      "fan": true,
      "projector": false
    }
  }
}
```
 
```json
// Alert object
{
  "room": "Room 101",
  "appliances": "Fan",
  "watts": 80,
  "severity": "low",
  "time": "11:42 AM"
}
```
 
```json
// Appliance wattage reference (configurable in Settings)
{
  "light": 120,
  "fan": 80,
  "projector": 200
}
```
 
Planned for later reviews: this in-memory structure will be migrated to a persistent database (e.g. Firebase/MongoDB) once backend integration begins, at which point this section will be expanded with actual API endpoints and schema definitions.
 
## 🤖 Planned AI Features
 
- Multi-camera concurrent occupancy detection across all classrooms
- Custom-trained occupancy model (replacing general-purpose COCO-SSD)
- Automated energy-waste detection with historical trend analysis
- AI-based energy usage prediction
- Automated appliance control (auto-shutoff on confirmed waste)
## 🛠️ Technologies Used
 
- HTML, CSS, JavaScript
- TensorFlow.js (COCO-SSD model) for computer-vision person detection
- Lucide Icons
- Planned: backend database, IoT sensor integration, notification service
## 🚀 Future Development
 
The project will be enhanced with persistent backend storage, real IoT appliance sensors, multi-camera deployment, automated unit testing, and notification delivery to facility staff.
 
## 👩‍💻 Project
 
**VOLT-IQ – AI Energy-Waste Detection**
 
Developed as part of the CoE Growth Project.
 
