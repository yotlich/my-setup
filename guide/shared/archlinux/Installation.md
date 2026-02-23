# Установка Arch Linux

## Получение образа

1. Скачать последний образ с зеркала Яндекса: [archlinux-x86_64.iso](https://mirror.yandex.ru/archlinux/iso/latest/archlinux-x86_64.iso)

2. Проверить достоверность образа

   ```console
   openssl dgst -sha256 ./archlinux-x86_64.iso
   ```

   > Чек-сумма **SHA256** на [официальном сайте загрузок](https://archlinux.org/download/) и в результате команды должны совпадать

## Запись образа на флешку

### Ventoy

1. Скачать последнюю версию [Ventoy](https://github.com/ventoy/Ventoy/releases) для вашей операционной системы, и запустить GUI версию Ventoy2Disk для вашей архитектуры

2. В Device выбрать флешку для записи образа, нажать Install, дождаться завершения установки

3. Скопировать archlinux-x86_64.iso на выбранную флешку

### Альтернативные способы

- Ознакомиться с [руководством](https://wiki.archlinux.org/title/USB_flash_installation_medium) на официальной вики

- Windows, использовать [Rufus](https://github.com/pbatard/rufus/releases) в DD режиме

- Linux, использовать утилиту dd, запуск от имени администратора:

  ```console
  dd bs=4M conv=fsync oflag=direct status=progress \
  if=./archlinux-x86_64.iso of=/dev/disk/by-id/usb-ВЫБРАННАЯ-ФЛЕШКА
  ```

## Запуск установочного образа

1. Настройках BIOS отключить Secure Boot и выставить флешку первой в списке загрузки

2. В появившимся меню выбрать Arch Linux install medium для запуска live-окружения

## Проверки перед установки

1. Система запушена в режиме UEFI и имеет 64-разрядную архитектуру

   ```console
   cat /sys/firmware/efi/fw_platform_size
   ```

   > Результат: `64`

2. Подключение к интернету

   ```console
   ping -c 5 ping.archlinux.org
   ```

   > Если ответы приходят, то подключение к интернету есть

3. Правильные дата и время

   ```console
   timedatectl status
   ```

   > Результат:
   >
   > ```console
   >                Local time: ПРАВИЛЬНОЕ ВРЕМЯ в UTC
   >            Universal time: ПРАВИЛЬНОЕ ВРЕМЯ в UTC
   >                  RTC time: ПРАВИЛЬНОЕ ВРЕМЯ в UTC
   >                 Time zone: UTC (UTC, +0000)
   > System clock synchronized: yes
   >               NTP service: active
   >           RTC in local TZ: no
   > ```
