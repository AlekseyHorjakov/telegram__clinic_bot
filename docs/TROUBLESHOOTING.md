# Troubleshooting

## Проблема

Telegram не отправлял сообщения из n8n.

## Ошибка

ETIMEDOUT

## Диагностика

curl работал корректно.

Node.js не мог подключиться к Telegram API.

## Причина

Особенности маршрутизации через V2Ray.

## Решение

Изменение настроек VPN.
Перезапуск n8n.
Проверка Chat ID.

## Проблема

Telegram node в n8n выдавал:

- ETIMEDOUT
- ECONNRESET

## Диагностика

Проверка Telegram API через браузер и curl показала, что Telegram доступен.

Проверка через Node.js:

node -e "require('https').get('https://api.telegram.org',(r)=>console.log(r.statusCode)).on('error',console.error)"

показала ошибки соединения.

## Причина

Некорректная маршрутизация Telegram через FIClash/V2Ray.

## Решение

Изменение VPN-маршрута и проверка соединения через Node.js.

После получения ответа:

302

Telegram начал корректно работать в n8n.
