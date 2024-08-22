# Список библиотек Arduino

![alt text](imgs/image.png)

Вы уже знаете, что комьюнити Ардуино очень большое и ежедневно растёт. За время своего существования оно родило огромное количество библиотек. Я решил составить список самых необычных, интересных и полезных, ссылки ведут на гитхаб или сайт разработчика. Полного набора специализированных библиотек для работы с модулями и шилдами здесь нет! Ищутся в гугле по названию чипа, здесь я оставлял только универсальные. Библиотеки, помеченные как стандартные, скачивать не нужно!

Список составлен для библиотек, подходящих для UNO, NANO, MEGA, то есть тут нет мощных библиотек для DUE и ZERO подобных плат. Источники:

- <https://www.arduino.cc/en/reference/libraries>
- <https://github.com/Lembed/Awesome-arduino/blob/master/README.md>
- <https://www.arduinolibraries.info/architectures/avr>

## avr-libs

В состав компилятора Arduino IDE входит набор стандартных библиотек под микроконтроллеры AVR (т.н. toolchain – набор инструментов), их можно просто подключить и использовать их возможности. Полный список и документация на все либы находится [здесь](https://nongnu.org/avr-libc/user-manual/modules.html). Тут перечислю самые полезные и интересные (название будет ссылкой на документацию):

- [math.h](https://nongnu.org/avr-libc/user-manual/group__avr__math.html) – библиотека с кучей математических функций. Подключена по умолчанию
- [time.h](https://nongnu.org/avr-libc/user-manual/group__avr__time.html) – библиотека для работы с временем. Счёт, конвертация, временные зоны и прочее
- [avr/eeprom.h](https://nongnu.org/avr-libc/user-manual/group__avr__eeprom.html) – родная библиотека для работы с EEPROM.
- [avr/power.h](https://nongnu.org/avr-libc/user-manual/group__avr__power.html) – библиотека управления потреблением МК: делитель системной частоты и включение/выключение периферии
- [avr/sleep.h](https://nongnu.org/avr-libc/user-manual/group__avr__sleep.html) – библиотека для управления режимом энергопотребления МК
- [avr/wdt.h](https://nongnu.org/avr-libc/user-manual/group__avr__watchdog.html) – управление сторожевым таймером
- [util/delay.h](https://nongnu.org/avr-libc/user-manual/group__util__delay.html) – библиотека с задержками на базе тактов процессора (работает без таймера 0)

## Время, таймеры

- [Time](https://github.com/PaulStoffregen/Time) – счётчик времени для Ардуино, считает часы-минуты-месяцы и всё такое. [Описание](http://playground.arduino.cc/Code/Time)
- [RTCTimer](https://github.com/SodaqMoja/RTCTimer) – таймер для работы в паре с RTC модулем
- [GyverTimer](https://github.com/AlexGyver/GyverLibs) – Есть мс и мкс таймеры, режим периода и таймаута, улучшенный алгоритм счёта периодов.
- [Chrono](https://github.com/SofaPirate/Chrono) – ещё библиотека “таймера с millis()” для эффективного построения логики своего кода
- [elapsedMillis](https://github.com/pfeerick/elapsedMillis) – ещё один простой таймер с millis()
- [buildTime](https://github.com/AlexGyver/GyverLibs) – библиотека для получения даты и времени компиляции в явном виде
- [TimeLord](https://github.com/probonopd/TimeLord) – библиотека, позволяющая узнать время восхода/заката Солнца и Луны, лунные фазы, звёздное время и проч. на основе географического положения
- [GyverTimers](https://github.com/AlexGyver/GyverLibs) – библиотека для управления прерываниями по всем таймерам на ATmega328 и ATmega2560 с возможностью отдельной настройки каналов. Объективно лучше следующих трёх библиотек.
- [TimerOne](https://github.com/PaulStoffregen/TimerOne) – библиотека для удобного ручного контроля за Таймером 1 (прерывания, ШИМ, и.т.д.)
- [MsTimer2](https://github.com/PaulStoffregen/MsTimer2) – библиотека для удобного ручного контроля за Таймером 2. Есть версия [FlexiTimer2](https://github.com/PaulStoffregen/FlexiTimer2), которая чем-то лучше.
- [TimerThree](https://github.com/PaulStoffregen/TimerThree) – библиотека для удобного ручного контроля за Таймером 3

## Коммуникация, интерфейсы

[GyverBus](https://github.com/AlexGyver/GyverLibs) – общение по протоколу GBUS. Двухсторонняя связь сети Ардуинок по одному проводу. [Описание](https://alexgyver.ru/gyverbus/)
[Firmata](https://www.arduino.cc/en/Reference/Firmata) – стандартная библиотека для общения с компьютером по протоколу Firmata. [Описание](https://www.arduino.cc/en/Reference/Firmata)
[SoftwareSerial](https://www.arduino.cc/en/Reference/SoftwareSerial) – стандартная библиотека для создания TTL Serial на любых двух пинах, позволяет создать дополнительный порт для общения с Bluetooth/GPS/GSM и прочими модулями с Serial коммуникацией.
[AltSoftSerial](https://github.com/PaulStoffregen/AltSoftSerial) – самая лучшая версия софтварного Serial, использует системный таймер
[SerialCommand](https://github.com/kroimon/Arduino-SerialCommand) – лёгкая библиотека для общения через порт при помощи команд
[CmdMessenger](https://github.com/thijse/Arduino-CmdMessenger) – мощная библиотека для общения через Serial порт, со своим парсером и кучей приколюх. [Описание](https://playground.arduino.cc/Code/CmdMessenger)
[EasyTransfer](https://github.com/madsci1016/Arduino-EasyTransfer) – библиотека для общения двух Ардуинок через последовательный порт
[Streaming](http://arduiniana.org/libraries/streaming/) – вывод в порт “в стиле C++” при помощи оператора <<
[OneWire](https://github.com/PaulStoffregen/OneWire) – библиотека для общения по протоколу one wire, например с датчиками температуры DS18b20. Ардуино может быть “slave” для общения, [читать тут](https://forum.pjrc.com/threads/23939-Strange-behavior-on-the-Onewireslave-library?p=33608&viewfull=1#post33608)
[SerialControl](https://github.com/UrsusExplorans/SerialControl) – набор примеров для управления состояниями пинов при помощи Serial команд. [Описание](http://playground.arduino.cc/Code/SerialControl)
[MiniPirate](https://github.com/chatelao/MiniPirate) – более мощная версия SerialControl, позволяет командами в порт крутить серво, сканировать i2c и многое другое!
[MIDI_library](https://github.com/FortySevenEffects/arduino_midi_library) – библиотека для работы с музыкальными устройствами по протоколу MIDI (через Serial, подходит любая Ардуина)
[MIDI](https://github.com/PaulStoffregen/MIDI) – MIDI библиотека от великого PaulStoffregen (через Serial, подходит любая Ардуина)
[arcore](https://github.com/rkistner/arcore) – ещё одна библиотека для MIDI (USB-MIDI, только для Леонардо/Микро)
[MIDIUSB](https://github.com/arduino-libraries/MIDIUSB) – ещё одна библиотека для MIDI (USB-MIDI, только для Леонардо/Микро)
[HIDUINO](https://github.com/ddiakopoulos/hiduino) – набор инструментов для создания USB MIDI устройства
[HID](https://github.com/NicoHood/HID) – очень мощная библиотека для создания HID устройств (мыши, клавиатуры, геймпады и другие USB контроллеры)
[ArduinoJoystickLibrary](https://github.com/MHeironimus/ArduinoJoystickLibrary) – ещё одна библиотека для создания полноценного HID геймпада на Leonardo/Micro (ATmega32U4)
[CPPM](https://github.com/jmparatte/jm_CPPM) – библиотека для организации связи по протоколу CPPM (например RC приёмник Orange R615X)
[PPMEncoder](https://github.com/schinken/PPMEncoder) – декодирование и генерация PPM сигнала для RC моделей
[PWMread](https://create.arduino.cc/projecthub/kelvineyeone/read-pwm-decode-rc-receiver-input-and-apply-fail-safe-6b90eb) – статья + библиотека для чтения PWM сигнала с приёмников RC моделей
[TVout](https://github.com/Avamander/arduino-tvout) – библиотека для вывода графики на экран телевизора через вход AV. [Описание](https://playground.arduino.cc/Main/TVout)
[X10](https://github.com/tigoe/x10) – библиотека для общения по протоколу X10 по линии питания 220V. [Описание тут](https://www.arduino.cc/en/tutorial/x10)
[NicoHoodProtocol](https://github.com/NicoHood/NicoHoodProtocol) – универсальный протокол связи по проводу

## Некоторое железо

[GyverStepper](https://alexgyver.ru/gyverstepper/) – высокопроизводительная библиотека для управления шаговым мотором
[AccelStepper](http://www.airspayce.com/mikem/arduino/AccelStepper/) – более интересная и качественная замена стандартной библиотеке [Stepper](https://www.arduino.cc/en/Reference/Stepper) для контроля шаговых моторчиков. Скачать можно со страницы разработчика.
[AccelMotor](https://alexgyver.ru/accelmotor/) – библиотека для управления мотором с энкодером (превращает обычный мотор в “шаговый” или сервомотор)
[ServoSmooth](https://github.com/AlexGyver/GyverLibs) – дополнение к стандартной библиотеке Servo, позволяющее управлять сервоприводом с настройкой максимальной скорости движения и разгона/торможения (как в AccelStepper, только для серво). Must have любого любителя серво манипуляторов!
[CapacitiveSensor](https://github.com/PaulStoffregen/CapacitiveSensor) – библиотека для создания сенсорных кнопок (из пары компонентов рассыпухи). Описание
[ADCTouchSensor](https://github.com/martin2250/ADCTouch) – ещё одна версия библиотеки для создания сенсорных кнопок. Есть ещё одна, так, на всякий случай
[TouchWheel](https://github.com/simap/TouchWheel) – библиотека для создания сенсорных слайдеров и колец
[Buzz](https://github.com/connornishijima/arduino-buzz) – детектор присутствия на основе всего лишь одного провода! (измеряет ЭМ волны)
[Bounce](https://github.com/thomasfredericks/Bounce2) – библиотека антидребезга для кнопок и всего такого. Сомнительная полезность, но почитайте описание
[oneButton](https://github.com/mathertel/OneButton) – библиотека для расширенной работы с кнопкой. На мой взгляд неудобная
[GyverButton](https://github.com/AlexGyver/GyverLibs) – библиотека для расширенной работы с кнопкой. Очень много возможностей!
[AdaEncoder](https://github.com/GreyGnome/AdaEncoder) – библиотека для работы с энкодерами
[GyverEncoder](https://github.com/AlexGyver/GyverLibs) – библиотека для энкодеров с кучей возможностей, поддерживает разные типы энкодеров
[RTCLib](https://github.com/adafruit/RTClib) – лёгкая библиотека, поддерживающая большинство RTC модулей
[OV7670](https://github.com/ComputerNerd/ov7670-no-ram-arduino-uno) – библиотека для работы с камерой на OV7670
[IRremote](https://github.com/z3t0/Arduino-IRremote) – базовая библиотека для работы с ИК пультами и излучателями
[IRLib](https://github.com/cyborg5/IRLib) – более расширенная версия для работы с ИК устройствами
[IRLremote](https://github.com/NicoHood/IRLremote) – самая чёткая библиотека для ИК пультов, работает через прерывания. 100% отработка пульта
[keySweeper](https://github.com/samyk/keysweeper) – почти готовый проект для перехвата нажатий с беспроводных клавиатур
[USB_Host_Shield](https://github.com/felis/USB_Host_Shield_2.0) – позволяет Ардуине работать с геймпадами (PS, XBOX) и другими USB устройствами
[Brain](https://github.com/kitschpatrol/Brain) – библиотека для работы с NeuroSky ЭЭГ модулями
[TinyGPS](https://github.com/mikalhart/TinyGPS) – шустрая библиотека для работы с GPS модулями
[GyverRGB](https://github.com/AlexGyver/GyverLibs) – библиотека для работы с RGB светодиодами и лентами
[FadeLED](https://github.com/septillion-git/FadeLed) – библиотека для плавного (ШИМ) мигания светодиодами с разными периодами
[CurrentTransformer](https://github.com/JChristensen/CurrentTransformer) – измерение силы тока при помощи трансформатора (катушки) на проводе. Читай: токовые клещи
[LiquidCrystal-I2C](https://github.com/fdebrabander/Arduino-LiquidCrystal-I2C-library) – библиотека для LCD дисплеев с I2C контроллером. Разработчик – fdebrabander
[LiquidTWI2](https://github.com/lincomatic/LiquidTWI2) – быстрая библиотека для LCD дисплеев на контроллерах MCP23008 или MCP23017
[LCD_1602_RUS](https://github.com/ssilver2007/LCD_1602_RUS) – библиотека русского шрифта для LCD дисплеев
[LCD_1602_RUS_ALL](https://github.com/ssilver2007/LCD_1602_RUS_ALL) – новая версия предыдущей библиотеки с поддержкой украинского языка
[u8glib](https://github.com/olikraus/u8glib) – библиотека для работы с монохромными LCD и OLED дисплеями
[ucglib](https://github.com/olikraus/ucglib) – библиотека для работы с цветными LCD и OLED дисплеями
[Adafruit_SSD1306](https://github.com/adafruit/Adafruit_SSD1306) – ещё одна библиотека для OLED дисплеев
[Adafruit-GFX-Library](https://github.com/adafruit/Adafruit-GFX-Library) – дополнение для adafruit библиотек дисплеев, позволяет выводить графику
[SSD1306Ascii](https://github.com/greiman/SSD1306Ascii) – самодостаточная и очень лёгкая библиотека для вывода текста на OLEDы
[NeoPixelBus](https://github.com/Makuna/NeoPixelBus) – библиотека для работы с адресной светодиодной лентой, адаптированная под esp8266 (NodeMCU, Wemos и др.).
[microLED](https://alexgyver.ru/microled/) – лёгкая и простая библиотека для работы с адресной лентой
[Gyver433](https://github.com/AlexGyver/GyverLibs#Gyver433) – лёгкая библиотека для отправки любых данных через радио модули 433 МГц
[rc-switch](https://github.com/sui77/rc-switch) – библиотека для работы с радио модулями 433 МГц и разными протоколами связи

## Работа с данными, фильтры
