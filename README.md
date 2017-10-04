# LCDs with PCF8574 I2C adapter driver for Android Things

A port of the LiquidCrystal_PCF8574 Arduino library for Android Things.

## Photo

Here using an LCD1602 with a LCM1602 I2C module

![photo][]<br><br>
![photo2][]

## Download

```groovy
dependencies {
    compile 'com.nilhcem.androidthings:driver-lcd-pcf8574:0.0.1'
}
```

## Usage

```java
LcdPcf8574 lcd = new LcdPcf8574(I2C_NAME, I2C_ADDRESS); // e.g. new LcdPcf8574("I2C1", 0x3f);
lcd.begin(16, 2);
lcd.setBacklight(true);

// load custom character to the LCD
int[] heart = {0b00000, 0b01010, 0b11111, 0b11111, 0b11111, 0b01110, 0b00100, 0b00000};
lcd.createChar(0, heart);

lcd.clear();
lcd.print("Hello,");
lcd.setCursor(0, 1);
lcd.print("Android Things!");
lcd.write(0); // write :heart: custom character

// Later on
lcd.close();
```

## Schematic

![schema][]

[photo]: https://raw.githubusercontent.com/Nilhcem/lcd-pcf8574-androidthings/master/assets/photo.jpeg
[photo2]: https://raw.githubusercontent.com/Nilhcem/lcd-pcf8574-androidthings/master/assets/photo2.jpeg
[schema]: https://raw.githubusercontent.com/Nilhcem/lcd-pcf8574-androidthings/master/assets/schematic.png
