# SharpSensor
This library is made for Sharp infrared sensors.
# Библиотека SharpSensor

Библиотека для работы с датчиками расстояния Sharp.

## Поддерживаемые модели

1. **GP2Y0A02YK0F** - 20-150 см
2. **GP2Y0A21YK0F** - 10-80 см
3. **GP2Y0A41SK0F** - 4-30 см
4. **GP2Y0A710K0F** - 100-550 см

## Установка

1. Скачайте библиотеку
2. В Arduino IDE: Скетч → Подключить библиотеку → Добавить .ZIP библиотеку
3. Выберите скачанный папку
4. И выберите архив в папке


#Методы
model(SharpModel) - выбор модели датчика

attach(pin) - подключение к аналоговому пину

get(unit) - получение расстояния (cm, mm, inch, raw)

getCM() - получение расстояния в см

getMM() - получение расстояния в мм

getInch() - получение расстояния в дюймах

getRaw() - получение сырого значения

setAverage(samples) - установка усреднения

calibrate(distance) - калибровка по известному расстоянию


#пример работы библиотеки

#include <SharpSensor.h>

SharpSensor sensor; 
void setup() {
    Serial.begin(9600);
    sensor.model(GP2Y0A21YK0F); 
    sensor.attach(A0);
}

void loop() {
    float distance = sensor.getCM();
    Serial.print("Расстояние: ");
    Serial.print(distance);
    Serial.println(" см");
    delay(100);
}
