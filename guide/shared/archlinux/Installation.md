# Установка archlinux

## Получение образа

1. Скачать последний образ с зеркала Яндекса: [archlinux-x86_64.iso](https://mirror.yandex.ru/archlinux/iso/latest/archlinux-x86_64.iso)

2. Проверить достоверность образа

   ```console
   openssl dgst -sha256 ./archlinux-x86_64.iso
   ```

   > Чек-сумма **SHA256** на [официальном сайте загрузок](https://archlinux.org/download/) и в результате команды должны совпадать
