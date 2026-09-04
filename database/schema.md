# MongoDB Database Schema

## Digital Twin Earth + Smart Governance Platform

This document defines the initial MongoDB data architecture for Semester 1. It provides a common data foundation for the backend, networking, hardware, AI/ML, and dashboard modules.

---

## 1. Database Overview

The platform will use MongoDB to store:

- User and role information
- Geographic hierarchy
- Devices and sensors
- Real and simulated sensor readings
- Drone operational status
- Alerts and system events
- AI predictions and risk analysis
- Governance actions
- System activity logs

### Core Data Flow

```text
Drone / Sensor / Simulator
            ↓
       FastAPI Backend
            ↓
          MongoDB
            ↓
AI Analysis + Dashboard
```

---

## 2. Collections

| Collection | Purpose |
|---|---|
| `users` | User accounts, authentication, and roles |
| `regions` | Geographic regions managed by the platform |
| `cities` | Cities belonging to regions |
| `zones` | Monitoring zones within cities |
| `devices` | Registered drones and IoT devices |
| `sensors` | Sensors associated with devices or locations |
| `sensor_readings` | Real-time and simulated sensor measurements |
| `drone_status` | Drone telemetry and operational states |
| `alerts` | System-generated and manually created alerts |
| `predictions` | AI predictions and risk scores |
| `governance_actions` | Administrative actions and responses |
| `system_logs` | Application and system activity logs |

---

## 3. Geographic Relationship

```text
Region
  ↓
City
  ↓
Zone
  ↓
Device / Sensor
```

The platform uses this hierarchy to organize monitoring data by location.

---

## 4. Device Data Relationship

```text
Device
  ├── Sensors
  ├── Sensor Readings
  └── Drone Status
```

A device can generate multiple sensor readings and status records over time.

---

## 5. Initial Collection Design Status

The detailed field definitions will be added collection by collection after team requirements are finalized.

### Planned Design Order

1. `users`
2. `regions`
3. `cities`
4. `zones`
5. `devices`
6. `sensors`
7. `sensor_readings`
8. `drone_status`
9. `alerts`
10. `predictions`
11. `governance_actions`
12. `system_logs`

---

## 6. Data Design Principles

- Use MongoDB `ObjectId` values for primary identifiers where appropriate.
- Store timestamps in UTC.
- Include `created_at` and `updated_at` fields where useful.
- Use references between collections when data is shared or grows independently.
- Keep high-volume time-series data such as sensor readings separate from device metadata.
- Support both real hardware data and simulated data.
- Preserve historical records for analysis, alerts, and governance decisions.

---

## 7. Semester 1 Priority

The first implementation milestone is:

```text
Simulated Data
      ↓
FastAPI
      ↓
MongoDB
      ↓
Dashboard
```

The detailed schemas will therefore prioritize `devices`, `sensors`, `sensor_readings`, and `drone_status` while maintaining the full platform architecture.

---

## 8. Next Step

Design the `users` collection, including authentication roles and administrative permissions.
