# a.i-navigation-compass-starter
[README.md](https://github.com/user-attachments/files/32685330/README.md)
# AI Navigation Compass

A high-reliability navigation research project combining GNSS, inertial sensors,
magnetometer data, sensor fusion, integrity monitoring, simulation, and an AI
assistant.

> **Important:** This repository is a research/prototyping project. It is not
> military-certified, safety-certified, or intended as a substitute for
> certified navigation equipment.

## Goals

- Estimate position, heading, velocity, and uncertainty.
- Fuse multiple simulated/real sensor sources.
- Detect degraded or contradictory measurements.
- Provide an explicit confidence/integrity state.
- Keep AI advisory rather than allowing it to override navigation measurements.
- Provide a deterministic simulator for testing.

## Architecture

```text
GNSS ───────────────┐
IMU ────────────────┼──> Sensor Fusion ──> Navigation State
Magnetometer ───────┤                         │
                     └─────────────────────────┤
                                               ↓
                                      Integrity Monitor
                                               ↓
                                      Navigation UI / AI
```

## Initial implementation

The first milestone contains a framework-free TypeScript navigation core and
deterministic simulator. The next milestones can add a Kalman/EKF implementation,
real device sensors, map rendering, persistence, and the AI layer.

## Development

```bash
npm install
npm test
npm run build
```

## Roadmap

- [x] Repository architecture
- [x] Navigation state model
- [x] Deterministic sensor simulator
- [x] Basic sensor-fusion baseline
- [ ] Extended Kalman filter
- [ ] GNSS quality/integrity metrics
- [ ] Magnetometer interference detection
- [ ] Dead reckoning
- [ ] Real device sensor adapters
- [ ] Interactive map UI
- [ ] Fault-injection test suite
- [ ] AI navigation assistant
- [ ] Offline map support
