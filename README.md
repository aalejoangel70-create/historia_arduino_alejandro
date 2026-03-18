# historia_arduino_alejandro
#  Investigación sobre Arduino

> Ejercicio en Clase — Exploración completa de la plataforma Arduino

---

## 1. Historia de Arduino

Arduino nació en **2005** en el Instituto de Diseño Interactivo de Ivrea (IDII), Italia. Fue creado por un equipo liderado por **Massimo Banzi**, David Cuartielles, Tom Igoe, Gianluca Martino y David Mellis, con el objetivo de facilitar el aprendizaje de electrónica y programación para artistas, diseñadores y aficionados.

El nombre *Arduino* proviene de un bar en Ivrea llamado **Bar di Re Arduino**, frecuentado por sus fundadores.

### Línea del tiempo

| Año | Evento |
|-----|--------|
| 2005 | Creación del primer prototipo en el IDII de Ivrea, Italia |
| 2007 | Lanzamiento de Arduino Diecimila con conector USB integrado |
| 2008 | Arduino Duemilanove con microcontrolador ATmega328 |
| 2010 | Arduino Mega 2560 y Arduino Nano. La comunidad crece globalmente |
| 2012 | Arduino Due: primera placa con procesador ARM de 32 bits (84 MHz) |
| 2016 | Arduino MKR1000 con WiFi integrado |
| 2018 | Arduino Nano 33 IoT con conectividad inalámbrica |
| 2021–hoy | Expansión con placas IoT, IA embebida y entornos cloud |

---

## 2. Periféricos de Arduino y su Uso

### Periféricos de Entrada

| Periférico | Descripción | Uso Común |
|-----------|-------------|-----------|
| Sensor de temperatura (DHT11/DHT22) | Mide temperatura y humedad | Monitoreo climático, termostatos |
| Sensor ultrasónico (HC-SR04) | Mide distancias por ultrasonido | Detección de objetos, robótica |
| Sensor de luz (LDR) | Fotorresistencia | Control automático de iluminación |
| Pulsadores / Botones | Push button | Interacción usuario, control de estados |
| Sensor de movimiento (PIR) | HC-SR501 infrarrojo | Alarmas, automatización del hogar |
| Joystick | Módulo KY-023 | Control de dirección, videojuegos DIY |

### Periféricos de Salida

| Periférico | Descripción | Uso Común |
|-----------|-------------|-----------|
| LEDs | Diodos emisores de luz | Indicadores visuales, iluminación |
| Pantalla LCD 16x2 | Display de caracteres | Mostrar mensajes y menús |
| Pantalla OLED | Display gráfico compacto | Interfaces gráficas |
| Buzzer | Emisor de sonido activo/pasivo | Alarmas, melodías, notificaciones |
| Motor DC | Motor de corriente continua | Robótica, vehículos, ventiladores |
| Servo Motor | Control de posición angular | Brazos robóticos, cámaras PTZ |
| Relay | Interruptor electromecánico | Control de cargas de alta potencia (AC) |

### Módulos de Comunicación

| Módulo | Protocolo | Aplicación |
|--------|-----------|-----------|
| HC-05 / HC-06 | Bluetooth | Control inalámbrico desde smartphone |
| ESP8266 / ESP01 | WiFi | IoT, conexión a internet |
| NRF24L01 | RF 2.4 GHz | Comunicación inalámbrica de largo alcance |
| SIM800L | GSM/GPRS | Envío de SMS, internet 2G |
| RFID RC522 | RFID 13.56 MHz | Control de acceso, identificación |
| GPS NEO-6M | UART serial | Rastreo de posición geográfica |

---

## 3. Ficha Técnica y Pines de Conexión

### Arduino UNO R3 — Especificaciones

| Característica | Especificación |
|---------------|---------------|
| Microcontrolador | ATmega328P (8 bits, AVR RISC) |
| Voltaje de operación | 5V |
| Voltaje de entrada recomendado | 7 – 12V |
| Pines digitales de E/S | 14 (6 con PWM: pines 3,5,6,9,10,11) |
| Pines analógicos de entrada | 6 (A0 – A5, resolución 10 bits) |
| Corriente DC por pin de E/S | 40 mA máximo |
| Memoria Flash | 32 KB (0.5 KB bootloader) |
| SRAM | 2 KB |
| EEPROM | 1 KB |
| Velocidad del reloj | 16 MHz |
| Dimensiones | 68.6 mm × 53.4 mm |
| Interfaces de comunicación | UART, SPI, I2C |

### Descripción de los Pines

| Pin / Grupo | Tipo | Descripción |
|------------|------|-------------|
| Vin | Alimentación | Entrada de voltaje externo (7–12V) |
| 5V | Alimentación | Salida regulada de 5V para componentes externos |
| 3.3V | Alimentación | Salida de 3.3V (máx. 50 mA) |
| GND | Tierra | Referencia común (hay 3 pines GND) |
| RESET | Control | Reinicia el microcontrolador al conectarse a GND |
| D0 (RX) – D1 (TX) | Digital / Serial | Comunicación UART. RX=recepción, TX=transmisión |
| D2 – D13 | Digital | E/S digital. D3,5,6,9,10,11 tienen PWM (~) |
| A0 – A5 | Analógico | Entradas analógicas de 10 bits (0–5V → 0–1023) |
| SDA (A4) / SCL (A5) | I2C | Bus de datos/reloj del protocolo I2C |
| MOSI / MISO / SCK / SS | SPI | Bus SPI: pines 11/12/13/10 respectivamente |
| AREF | Referencia | Voltaje de referencia analógico para el ADC |

### Comparativa de Modelos

| Modelo | MCU | Velocidad | Flash | Pines Digitales | Característica |
|--------|-----|-----------|-------|-----------------|----------------|
| UNO R3 | ATmega328P | 16 MHz | 32 KB | 14 | Estándar, más utilizado |
| Mega 2560 | ATmega2560 | 16 MHz | 256 KB | 54 | Gran capacidad E/S |
| Nano | ATmega328P | 16 MHz | 32 KB | 14 | Compacto, breadboard-friendly |
| Due | ARM SAM3X8E | 84 MHz | 512 KB | 54 | 32 bits, alta velocidad |
| MKR WiFi 1010 | SAMD21 | 48 MHz | 256 KB | 22 | WiFi y BLE integrados |
| Nano 33 BLE Sense | nRF52840 | 64 MHz | 1 MB | 22 | BLE + sensores IMU |

---

## 4. Arquitectura, Ventajas y Funcionalidad

### Arquitectura de Hardware

El núcleo de Arduino UNO es el microcontrolador **ATmega328P**, basado en la arquitectura Harvard de 8 bits AVR RISC:

- **CPU:** Procesa instrucciones a 16 MHz con hasta 16 MIPS
- **Flash (32 KB):** Almacena el programa del usuario (sketch)
- **SRAM (2 KB):** Variables y datos en tiempo de ejecución
- **EEPROM (1 KB):** Memoria no volátil, persiste al apagar
- **ADC:** 6 canales de 10 bits para señales analógicas
- **Timers:** 3 timers para PWM, interrupciones y temporización
- **Comunicación:** UART, SPI e I2C integradas en hardware

### Arquitectura de Software

```cpp
void setup() {
  // Se ejecuta UNA sola vez al iniciar
  pinMode(13, OUTPUT);
}

void loop() {
  // Se repite en BUCLE infinito
  digitalWrite(13, HIGH);
  delay(1000);
  digitalWrite(13, LOW);
  delay(1000);
}
```

### Ventajas de Arduino

| Ventaja | Descripción |
|---------|-------------|
| Código abierto | Hardware y software completamente libres |
| Bajo costo | Placas desde ~$3 USD, accesibles para educación |
| Fácil de usar | IDE sencillo y documentación extensa para principiantes |
| Gran comunidad | Millones de usuarios y proyectos compartidos globalmente |
| Multiplataforma | Compatible con Windows, macOS y Linux |
| Extensible | Compatible con cientos de Shields (módulos apilables) |
| Versátil | Robótica, IoT, automatización, arte interactivo y más |
| Prototipado rápido | De idea a prototipo funcional en minutos |

### Áreas de Aplicación

| Área | Aplicaciones |
|------|-------------|
| Robótica | Robots móviles, brazos robóticos, drones |
| IoT | Sensores conectados, monitoreo remoto, control web |
| Automatización del hogar | Luces, temperatura, seguridad inteligente |
| Educación STEM | Aprendizaje práctico de electrónica y programación |
| Arte interactivo | Instalaciones que responden al entorno |
| Agricultura inteligente | Riego automático, monitoreo de cultivos |
| Impresión 3D / CNC | Control de motores, firmware Marlin/GRBL |

---

## 5. Referencias

- https://www.xataka.com/basics/que-arduino-como-funciona-que-puedes-hacer-uno
- https://aprendiendoarduino.wordpress.com/2019/08/28/entradas-y-salidas-en-arduino/
- https://roboticsbackend.com/arduino-uno-pins-a-complete-practical-guide/
- https://www.reddit.com/r/arduino/comments/pmw70q/what_are_these_metal_pins_that_come_with_arduino/?tl=es-419
- https://lab.bricogeek.com/tutorial/guia-de-modelos-arduino-y-sus-caracteristicas/arduino-uno
