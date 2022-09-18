# DpkgSoft Tunnel
DpkgSoft Tunnel - утилита, позволяющая показать на публичном адресе содержимое, запущенное на локальном сервере. Это может помочь при разработке программного обеспечения.

## 1. Использование
1. Установите приложение

```npm install dpkgtunnel-client -g```

2. Запустите любой веб-сервер. Например, `npm start`.

3. Запустите DpkgTunnel:

```
env NODE_TLS_REJECT_UNAUTHORIZED=0 \ 
PROXY_HTTP_PROTO=https \ 
PROXY_WS_PROTO=wss \ 
PROXY_HOST=localhost \ 
PROXY_PORT=3000 \ 
PROXY_TIMEOUT=5000 \ 
dpkgtunnel
```

или, используя опции:

```
dpkgtunnel --insecure=1 --http-protocol=https --ws-protocol=wss --host=localhost --port=3000 --timeout=5000
```

Это запустит туннель, который будет слушать localhost:3000.

После авторизации через edwardcode.me в терминале появится ссылка наподобие:

`https://u12345-abcdefabcd.abcdeabc.tunnel.dpkgsoft.com`

Вы можете поделиться этой ссылкой, и по ней откроется содержимое сервера, запущенного на Вашем компьютере на localhost:3000.

## 2. Переменные окружения
| Переменная                   | Опция           | Описание                                                        |
|------------------------------|-----------------|-----------------------------------------------------------------|
| NODE_TLS_REJECT_UNAUTHORIZED | --insecure      | Игнорировать ошибки SSL-сертификатов.                           |
| PROXY_HTTP_PROTO             | --http-protocol | Схема протокола для связи с локальным сервером. http или https. |
| PROXY_HOST                   | --host          | Хост локального сервера, например localhost                     |
| PROXY_POST                   | --port          | Порт локального сервера, например 3000                          |
| PROXY_TIMEOUT                | --timeout       | Тайм-аут ожидания локального сервера                            |