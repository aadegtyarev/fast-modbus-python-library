# Fast Modbus Library

## Description
! This repository is not affiliated with or supported by Wiren Board. All code is written by [DeepSeek](https://chat.deepseek.com/), based on the scripts in the repository https://github.com/aadegtyarev/fast-modbus-python-tools

A library for working with Fast Modbus devices via a serial port (RS-485). It contains modules for configuring event notifications, scanning devices, and working with the Modbus client.

## Features
- **Device Scanning**: Detects Modbus devices on the network.
- **Data Exchange**: Reads and writes Modbus registers for real-time device communication.
- **Event Handling**: Requests and manages events from Modbus devices.
- **Event Configuration**: Sets up event parameters on Modbus devices.

## Installation

### Install Dependencies

```
pip install -r requirements.txt
```

### Install the Module

```
pip install .
```

## Usage

### Running Examples

```
cd ./fast-modbus-python-library
```
#### Device Scanning Example

```
python -m examples.exsample_scan -d /dev/ttyACM0 -b 9600
```

#### Modbus Client Example

```
# Read
python -m examples.exsample_client -d /dev/ttyACM0 -b 9600 -s 4265607340 -c 3 -r 128 -n 1

# Write
python -m examples.exsample_client -d /dev/ttyACM0 -b 9600 -s 4265607340 -c 0x10 -r 128 -w 201

```

#### Event Notifications Configuration Example

```
python -m examples.exsample_config_events --device /dev/ttyACM0 --baud 9600 --slave_id 200 --config "discrete:0:2:1,discrete:4:3:0"
```

#### Event Handling Example

```
python -m examples.exsample_events -d /dev/ttyACM0 -b 9600
```

### Help on Parameters

```
python -m examples.exsample_client --help
```

## Module Descriptions

### fastmodbuslibrary

- **common.py**: Common functions and constants.
- **fast_modbus_client.py**: Modbus client for working with Modbus.
- **fast_modbus_config_events.py**: Module for configuring event notifications.
- **fast_modbus_events.py**: Module for handling events.
- **fast_modbus_scanner.py**: Module for scanning devices.
- **__init__.py**: Package initialization.
- **logging_config.py**: Logging configuration.

## Tests

### Running Tests

```
python -m unittest discover tests
```

### Test Descriptions

- **test_modbus_client_multiple.py**: Tests for working with multiple Modbus clients.
- **test_modbus_client_single.py**: Tests for working with a single Modbus client.
- **test_modbus_client_write.py**: Tests for writing data to Modbus.
- **test_modbus_config_events.py**: Tests for configuring event notifications.
- **test_modbus_events_confirmation.py**: Tests for event confirmation.
- **test_modbus_events.py**: Tests for event handling.
- **test_modbus_scanner.py**: Tests for device scanning.

## License
This project is licensed under the MIT License.
