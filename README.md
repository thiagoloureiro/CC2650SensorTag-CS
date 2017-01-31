## TI CC2650 SensorTag C#

This repository is a port of the [ms-iot/Samples/BluetoothGatt/CS GitHub](https://github.com/ms-iot/samples/tree/develop/BluetoothGATT/CS) code to support the Texas Instrument CC2650STK, the **CC2650 SensorTag**. The Microsoft code only supports the TI CC2451 Sensor Tag. This code has been refactored and extended to only support the CC2650.

The code establishes a connection to the service for each of the BTE characteristics and displays their values in real time. A major difference from the CC2451 is that the Gyroscope, Magnetometer and Accelerometer are one characteristic, Motion. Also this tag has a reed switch.

This code also supports the IO Characteristic enabling turning of the LEDs 1 & 2 as well as the Buzzer on and off.

The supported characteristics/services are:            
- IR_SENSOR
- HUMIDITY
- BAROMETRIC_PRESSURE
- IO_SENSOR
- KEYS
- OPTICAL
- MOVEMENT
- REGISTERS

The code has been specifically refactored so that the CC2650 functionality is defined in a separate class. Whilst the Bluetooth connectivity and UI for displaying data and for user input remains in the MainPage class, characteristic metadata, service code and event handlers are all in the CC2650 class. The class uses a callback mechanism to update data in the UI.

Further versions could implement:
- A Headless version of the code
- An integration with the [Azure IoT Gateway SDK](https://github.com/Azure/azure-iot-gateway-sdk/) This SDK does support the CC2650 tag as an example using the RPI3 but the code is only for Linux running on the RPI3
