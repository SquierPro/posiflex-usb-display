# posiflex-usb-display
Sending data to display Posiflex PD2601u, usb (without pl2303 chip)
Отправка строк на дисплей Posilex PD2601u, usb версия без чипсета эмуляции ком порта pl2303

##udev
SUBSYSTEM=="usb", ATTRS{idVendor}=="0d3a", ATTRS{idProduct}=="0200", GROUP="YOUR_GROUP", MODE="0660"


##Examples:
python display.py $'\x1B\x40' # Clear display - Очистить дисплей
python display.py $'\x1B\x74\x06' # Select character code page table - Включает поддержку кириллицы cp866

python display.py $'\x1B\x25\x01' # Set user-defined characters - Использование пользовательских символов
python display.py $'\x1B\x26\xB0\x4E\xCA\x27\x9E\xC0' # Russian ruble to \xB0 - Символ рубля в \xB0

python display.py $'\x20\x20\x20\x20\x20\x48\x65\x6c\x6c\x6f\x20\x77\x6f\x72\x6c\x64\x21\x20\x20\x20\x20\x20\x20\x20\x20\x8f\xe0\xa8\xa2\xa5\xe2\x2c\x20\xac\xa8\xe0\x21' # Hello world! - Привет, мир!
