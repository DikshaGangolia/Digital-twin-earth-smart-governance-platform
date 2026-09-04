# Database Architecture

## Semester 1 – MongoDB Foundation

This folder contains the database design and documentation for the Digital Twin Earth + Smart Governance Platform.

## Planned Collections

1. `users` – user accounts, authentication and roles
2. `regions` – major geographical regions
3. `cities` – cities belonging to regions
4. `zones` – smaller administrative or monitoring zones
5. `devices` – registered IoT devices and drone devices
6. `sensors` – sensor metadata and configuration
7. `sensor_readings` – incoming real-time and simulated sensor data
8. `drone_status` – drone telemetry and operational states
9. `alerts` – generated safety and anomaly alerts
10. `predictions` – AI and rule-based prediction results
11. `governance_actions` – actions taken by administrators or authorities
12. `system_logs` – important system events and error logs

## Main Data Flow

```text
Drone / Sensors / Simulators
            ↓
          FastAPI
            ↓
          MongoDB
            ↓
      Dashboard / AI
```

## Next Database Step

Define the fields and relationships for every collection before implementing the MongoDB models.
