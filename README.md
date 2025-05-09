# SaltBot

This project uses an Olimex ESP32-POE-ISO microcontroller running ESPHome to monitor Salt Tank levels from a HC-SR04 sensor. The device connects via Ethernet and exposes all readings natively to Home Assistant. An optional onboard web server allows viewing sensor values directly in a browser.

## Features

- **Sensor Monitoring**: Reads from a HC-SR04 sensor.
- **Home Assistant Integration**: Native API support for use in automations and dashboards.
- **OTA Updates**: Firmware can be updated via Home Assistant.
- **Ethernet-Based**: Uses ESP32 LAN8720 interface, no Wi-Fi stack required.
- **Web Server**: Optional local web interface on port 80 for raw sensor viewing.

## Components

- **ESP32-POE-ISO**: Main microcontroller with built-in Ethernet. [Olimex ESP32-POE](https://www.mouser.com/ProductDetail/Olimex-Ltd/ESP32-POE-ISO-EA?qs=%252B6g0mu59x7KfK%2FIl1ERS8Q%3D%3D)
- **HC-SR04**: Up to 4 digital temperature sensors. [Link](https://www.amazon.com/DIYables-HC-SR04-Ultrasonic-Arduino-Raspberry/dp/B0BDFLPZ2R/ref=sr_1_3_pp?crid=337EQ8FXCQ5UY&dib=eyJ2IjoiMSJ9.4VIz8v9wwYeTqEQbVUwOPAwtxyRhETnroFHfs4vAAJNov4gWsa_XysxcgX2wm6ERS0hgUA3fbcJREvu1nLmdwE-_Hm_2NUqWTicYit7hryh9XuFdNQz_AwSz-z805O9163Xl2XG-OFw0uxczSh-rbpZhBMCMV7kW4YRQrerDBu0QGapcJQX_PEg4itRifhBpdrzupDCRUE5TSdEZcNgxr9wPVuEZReisKATNASxbSgmUuJwRjZlMRJplB1zBcG0ftSXzXbc1HviVpb7eFPURoU_vZ5V6uNIHJ_jgu0T2B0Y.rS_uRm4098HzUQ9QdjAxaBkA0W1Jk3NG7LWwU_4MBdI&dib_tag=se&keywords=HC%2BSR04&qid=1746809777&s=industrial&sprefix=hc%2Bsr04%2Cindustrial%2C143&sr=1-3&th=1)

## Pin Assignments

| Component        | Pin         |
|------------------|-------------|
| Trigger Pin      | GPIO13      |
| Echo Pin         | GPIO14      |
| Ethernet MDC     | GPIO23      |
| Ethernet MDIO    | GPIO18      |
| Ethernet CLK     | GPIO17 (OUT)|
| Ethernet Power   | GPIO12      |

## Installation

1. Install Home Assistant with the ESPHome Add-on.
2. Use the ESPHome dashboard to add a new device with the following configuration:
   - Encryption Key
   - OTA Key
3. Flash via USB initially; future updates are handled OTA.

## Contributing

1. Fork the repository.
2. Create your feature branch (`git checkout -b feature/YourFeature`).
3. Commit your changes (`git commit -am 'Add some feature'`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Create a new Pull Request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Thanks to the developers of the libraries used in this project.
- Made this because I really needed to track my salt level in the salt tank.
