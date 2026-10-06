# VOLT-IQ ⚡

AI-powered classroom energy-waste detection and smart energy monitoring system.

## 📌 About the Project

VOLT-IQ is an AI-powered classroom energy intelligence system designed to detect unnecessary electricity consumption in educational environments.

The system combines computer vision-based occupancy detection with classroom appliance monitoring to identify situations where electrical appliances such as lights, fans, and projectors remain ON while a classroom is unoccupied.

VOLT-IQ provides classroom monitoring, AI occupancy analysis, energy-waste detection, alerts, and energy analytics through a centralized dashboard.

## 🎯 Problem Statement

Electrical appliances such as lights, fans, and projectors may remain switched ON even when classrooms are empty.

This results in unnecessary electricity consumption, increased operating costs, and avoidable energy wastage.

## 💡 Proposed Solution

VOLT-IQ monitors classroom occupancy and appliance status.

The system uses computer vision to detect people through a classroom camera feed and determines whether the classroom is Occupied or Empty.

It then combines the occupancy result with appliance status to identify possible energy wastage.

### Decision Flow

```text
Camera Feed
     ↓
AI Person Detection
     ↓
Occupancy Detection
     ↓
Appliance Status
     ↓
Decision Engine
     ↓
Energy-Waste Detection
     ↓
Alert + Dashboard + Analytics
