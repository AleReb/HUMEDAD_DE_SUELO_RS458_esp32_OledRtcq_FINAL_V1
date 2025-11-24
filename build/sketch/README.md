#line 1 "C:\\Users\\Ale\\Documents\\Arduino\\HUMEDAD_DE_SUELO_RS458_esp32_OledRtcq_FINAL_V1\\README.md"
# Sistema de Monitoreo de Humedad de Suelo con ESP32

Este proyecto implementa un sistema robusto de monitoreo ambiental utilizando un ESP32. El sistema lee la humedad y temperatura del suelo mediante un sensor RS485 (Modbus), muestra los datos en una pantalla OLED, los almacena en una tarjeta SD y mantiene un registro temporal preciso gracias a un RTC DS3231.

## Características

- **Lectura de Sensor RS485**: Comunicación Modbus RTU para sensores de humedad y temperatura de suelo de grado industrial.
- **Registro de Datos (Datalogger)**: Almacenamiento de datos en tarjeta SD en formato CSV (`ActiveSensor_DB.csv`).
- **Reloj en Tiempo Real (RTC)**: Uso de DS3231 para marcas de tiempo precisas incluso sin conexión a internet.
- **Interfaz Visual**: Pantalla OLED SH1106 para visualización de datos en tiempo real.
- **Indicador de Estado**: LED RGB NeoPixel para indicar visualmente el estado del sistema (Conexión, Errores, Grabación).
- **Gestión de Energía**: Monitoreo de voltaje de batería.
- **Robustez**: Sistema de reinicio automático y reintentos de conexión para operación continua.

## Hardware Requerido

- **Microcontrolador**: ESP32 DevKit V1
- **Sensor**: Sensor de humedad y temperatura de suelo RS485 (Modbus RTU)
- **Módulo RS485 a TTL**: Para la comunicación con el sensor (MAX485 o similar)
- **Pantalla**: OLED SH1106 (1.3") I2C
- **RTC**: DS3231 (I2C)
- **Almacenamiento**: Módulo de tarjeta Micro SD (SPI)
- **Indicador**: LED RGB NeoPixel (WS2812B)
- **Batería**: Batería LiPo/Li-Ion con divisor de voltaje para monitoreo

## Conexiones (Pinout)

| Componente | Pin ESP32 | Notas |
|------------|-----------|-------|
| **RS485 RX** | GPIO 18 | SoftwareSerial RX |
| **RS485 TX** | GPIO 19 | SoftwareSerial TX |
| **RS485 RE/DE**| GPIO 33 | Control de dirección |
| **OLED SDA** | GPIO 21 | I2C (Defecto) |
| **OLED SCL** | GPIO 22 | I2C (Defecto) |
| **RTC SDA** | GPIO 21 | I2C (Defecto) |
| **RTC SCL** | GPIO 22 | I2C (Defecto) |
| **SD CS** | GPIO 12 | SPI |
| **SD MOSI** | GPIO 13 | SPI |
| **SD MISO** | GPIO 15 | SPI |
| **SD SCK** | GPIO 2 | SPI |
| **NeoPixel** | GPIO 0 | Datos LED |
| **Batería** | GPIO 34 | Entrada Analógica (Divisor) |

## Librerías Requeridas

Asegúrate de instalar las siguientes librerías en tu IDE de Arduino:

- `FS` y `SD` (Incluidas en el core de ESP32)
- `SPI` y `Wire` (Incluidas en Arduino)
- `EspSoftwareSerial` (para comunicación serial en pines definidos)
- `RTClib` (Adafruit)
- `U8g2` (Olikraus)
- `Adafruit NeoPixel`

## Autor

**Alejandro Rebolledo**  
Correo: [arebolledo@udd.cl](mailto:arebolledo@udd.cl)

## Licencia

Este proyecto está licenciado bajo la **Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)**.
Consulta el archivo `LICENSE` para más detalles.

## DESCARGO DE RESPONSABILIDAD

**El código se ofrece "tal cual", sin garantías de ningún tipo, explícitas o implícitas, incluyendo pero no limitándose a las garantías de comerciabilidad, idoneidad para un propósito particular y no infracción. En ningún caso el autor será responsable de reclamaciones, daños u otras responsabilidades, ya sea en una acción de contrato, agravio o de otro tipo, que surjan de, fuera de o en conexión con el software o el uso u otros tratos en el software. El usuario utiliza este código y el hardware asociado bajo su propio riesgo.**
