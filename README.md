# IEC 62056-21 electricity meter Integration for Home-Assistant

Custom integration for Home Assistant to connect electricity meter ISKRA MT174 via IEC 62056-21 protocol [mode C] (https://github.com/lvzon/dsmr-p1-parser/blob/master/doc/IEC-62056-21-notes.md).

The integration polls every 5 minutes and provides 6 entities:
- Energy consumption total in kWh
- Energy Consumption Tariff 1 in kWh
- Energy Consumption Tariff 2 in kWh
- Energy feed total in kWh
- Energy Feed Tariff 1 in kWh
- Energy Feed Tariff 2 in kWh

## Installation
### a) Install over HACS
- Add `https://github.com/stprehn/ha_iec6205621` repository to HACS integrations
- Add `IEC 62056-21 electricity meter Integration` integration with HACS
### b) Install manual
If you don't have or don't want use HACS, install it over Terminal:
```
cd /config/custom_components
wget https://github.com/stprehn/ha_iec6205621/archive/refs/heads/main.tar.gz
tar --strip-components=3 -xzf main.tar.gz ha_iec6205621-main/custom_components/iec6205621
rm main.tar.gz
```
### Restart 
After install restart Home-Assistant (Configuration -> System -> Restart)

## Setup
- After installation, you should find **iec6205621** under Configuration -> Integrations -> Add integration.
- Enter serial port connected to the electricity meter.

## Debugging
Add the following to `configuration.yaml` to show debugging logs. Please make sure to include debug logs when filing an issue.

See [logger integration docs](https://www.home-assistant.io/integrations/logger/) for more information to configure logging.

```yml
logger:
  default: warning
  logs:
    custom_components.iec6205621: debug
```
