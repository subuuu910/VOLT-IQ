# VOLT IQ ⚡

AI-powered classroom energy-waste detection and smart energy monitoring system.

## 📌 About the Project

VOLT IQ is a smart classroom energy monitoring system designed to detect unnecessary electricity usage when classrooms are unoccupied.

The completed system combines AI-based occupancy detection with classroom appliance monitoring to identify potential energy wastage from lights, fans, and projectors.

## 🎯 Problem Statement

Electrical appliances such as lights, fans, and projectors may remain switched ON even when classrooms are empty. This can lead to unnecessary energy consumption and energy wastage in educational institutions.

## 💡 Proposed Solution

VOLT IQ monitors classroom occupancy and appliance status. Computer vision is used to detect people through classroom camera feeds and determine whether a classroom is occupied or empty.

The system combines occupancy information with appliance status and uses a decision engine to identify energy-waste conditions.

If a classroom is empty while one or more appliances are ON, VOLT IQ detects potential energy wastage and generates an alert.

## 🤖 AI Features

- Computer Vision based occupancy detection
- TensorFlow.js integration
- COCO-SSD person detection
- Real-time people counting
- Occupied / Empty classification
- Classroom camera monitoring
- AI Detection interface
- Occupancy-based energy analysis

## ⚡ Energy Monitoring

VOLT IQ monitors the status of:

- 💡 Lights
- 🌀 Fans
- 📽 Projectors

The system evaluates appliance usage together with classroom occupancy to identify unnecessary energy consumption.

## 🚨 Energy-Waste Detection

The core detection logic follows:

```text
Classroom Empty
       +
Any Appliance ON
       ↓
Energy Waste Detected
       ↓
Alert Generated
