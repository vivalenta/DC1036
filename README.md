# Моніторинг напруги та доробки акумулятора UPS DC1036

Цей проєкт реалізує моніторинг напруги та заряду акумулятора для системи безперебійного живлення (UPS) на базі ESP8266 з використанням ESPHome.

Дані передаються через MQTT для подальшого аналізу та обробки.


Також був розширена емність аккумулятора в 3 рази:

<img src="./IMG/IMG_20240710_201648.jpg" style="width:50%;">
<img src="./IMG/IMG_20240710_201658.jpg" style="width:50%;">
<img src="./IMG/IMG_20240710_202136.jpg" style="width:50%;">


## Обладнання

- ESP8266 (наприклад, плата ESP12F)
- Дільник напруги (резистори 1680 кОм та 100 кОм)
- Бінарний датчик для відстеження живлення від мережі (GPIO5)
- Акумуляторна батарея з діапазоном напруги 11.4 - 16.8 В

<img src="./IMG/IMG_20240729_233728.jpg" style="width:50%;">



## Інструкція зі складання
Залийте прошивку будь яким способом, підключення вигляжає так

<img src="./IMG/esp-12_bb.png" style="width:50%;">

Підключення резисторів: підключіть резистори відповідно до схеми дільника напруги.

<img src="./IMG/IMG_20240729_221603.jpg" style="width:50%;">


Підключення ESP8266:

Дільник напруги до A0 (аналоговий вхід).
Бінарний датчик RE до GPIO5 для відстеження живлення від мережі.
Плюс живлення V (3.3 Вольта) до VCC
Мінус живлення G до GND та IO15

<img src="./IMG/IMG_20240729_221525.jpg" style="width:50%;">
<img src="./IMG/IMG_20240729_221532.jpg" style="width:50%;">
<img src="./IMG/IMG_20240729_235035.jpg" style="width:50%;">



Використання:
Після підключення та налаштування пристрій автоматично з'єднається з WiFi та MQTT-сервером.
Дані про напругу та заряд акумулятора будуть передаватися на MQTT-сервер у темах ups-dc1036/battery_voltage та ups-dc1036/battery_charge.
Стан живлення від мережі буде передаватися у темі ups-dc1036/upsdc_acpower.
Буде запущено веб сервер з статусом.

<img src="./IMG/Screenshot-from-2024-07-30-09-59-47.png" style="width:50%;">
<img src="./IMG/screencapture-home-wuddi-in-ua-history-2024-07-30-14_23_25.png" style="width:50%;">
<img src="./IMG/Screenshot-from-2024-07-30-09-59-48.png" style="width:50%;">



Якщо у вас виникли питання або пропозиції, будь ласка, зв'яжіться з автором проєкту.
