# HiveBox – Sensor Configuration

## 1. Overview

This document describes the three environmental sensors selected for the HiveBox project.

The sensors are registered on the **openSenseMap** platform and will be used as data sources for collecting environmental measurements, particularly temperature readings.

## 2. Data Source

- **Platform:** [openSenseMap](https://opensensemap.org/)
- **API Documentation:** [openSenseMap API](https://docs.opensensemap.org/)
- **API Endpoint:** `GET https://api.opensensemap.org/boxes/{boxId}`

## 3. Selected Sensors

### Sensor 1 – Taubenklima

| Property | Value |
|---|---|
| Box ID | `662bdf8cb15a84000780c8c6` |
| Name | Taubenklima |
| Exposure | Outdoor |
| Temperature | 14.20 °C |
| Relative Humidity | 49.36% |
| PM10 | 10.30 µg/m³ |
| PM2.5 | 5.60 µg/m³ |
| Last Measurement | 2026-11-03 13:45:40 UTC |

### Sensor 2 – Feinstaubsensor Baumbachstraße

| Property | Value |
|---|---|
| Box ID | `5d613c92953683001a6933bf` |
| Name | Feinstaubsensor Baumbachstraße |
| Exposure | Outdoor |
| Temperature | 11.31 °C |
| Relative Humidity | 54.65% |
| PM10 | 5.03 µg/m³ |
| PM2.5 | 3.45 µg/m³ |
| Air Pressure | 102585.09 Pa |
| Last Measurement | 2026-11-03 13:44:35 UTC |

### Sensor 3 – Feinstaub-Messung Bessemer

| Property | Value |
|---|---|
| Box ID | `606b46bdb8e635001b93b899` |
| Name | Feinstaub-Messung Bessemer |
| Exposure | Outdoor |
| Temperature | 9.73 °C |
| Relative Humidity | 55.96% |
| PM10 | 3.67 µg/m³ |
| PM2.5 | 2.67 µg/m³ |
| Air Pressure | 102699.41 Pa |
| Last Measurement | 2026-11-03 13:45:27 UTC |

## 4. Sensor Validation

The three selected senseBoxes were validated using the openSenseMap API.

Validation results:

- All three Box IDs returned valid API responses.
- All three devices have temperature sensors.
- All three devices returned temperature measurements.
- All three devices are configured for outdoor exposure.
- Measurement timestamps were available for all devices.

**Geographical proximity:** Pending verification using sensor coordinates.

## 5. Initial Temperature Analysis

The temperature readings retrieved during validation were:

| Sensor | Temperature |
|---|---:|
| Taubenklima | 14.20 °C |
| Baumbachstraße | 11.31 °C |
| Bessemer | 9.73 °C |

Average temperature:

`(14.20 + 11.31 + 9.73) / 3 = 11.7467 °C`

**Initial Average Temperature: 11.75 °C**

This is an initial calculation based on the measurements retrieved during validation. Future application logic will calculate the average dynamically using the latest valid measurements.

## 6. Usage in HiveBox

These three senseBoxes will be used as the initial data sources for the HiveBox application.

Planned usage:

- Retrieve measurements from openSenseMap.
- Extract temperature values from the selected devices.
- Validate measurement timestamps.
- Calculate the average temperature.
- Expose the calculated result through the application's REST API.

## 7. Configuration

The selected Box IDs will be configurable through environment variables in future development phases.

This approach avoids hardcoding sensor identifiers inside the application code and makes the configuration easier to maintain.

## 8. References

- [openSenseMap Website](https://opensensemap.org/)
- [openSenseMap API Documentation](https://docs.opensensemap.org/)
- [HiveBox Project Repository](https://github.com/DevOpsHiveHQ/devops-hands-on-project-hivebox/)