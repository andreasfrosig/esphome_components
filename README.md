# WORK IN PROGRESS! Not working at the moment.

Original work by Heine K. Madsen (https://github.com/heinekmadsen/esphome_components)

## Genvex component for Optima 270

```yaml
packages:
  remote_package:
    url: https://github.com/MartinLorenzen/esphome_components
    ref: main
    files: [components/genvexv2/optima270.yaml]
    refresh: 0s

uart:
  - id: uart_genvex
    rx_pin: GPIO16
    tx_pin: GPIO17
    parity: EVEN
    baud_rate: 19200
    stop_bits: 1
  
modbus:
    - id: genvex_modbus
      uart_id: uart_genvex
 
modbus_controller:
  id: genvex_modbus_controller
  address: 1
  modbus_id: genvex_modbus
  update_interval: 60s
  command_throttle: 10ms
```

