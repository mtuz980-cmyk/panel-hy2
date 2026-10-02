# Установщик

Ключ в репозиторий не входит.

`panel-hy2.sh.b64` — зашифрованный установщик WDTT, панели Blitz, заглушки магазина и прокси Telegram.
Marzban и WireGuard не ставятся.

Скачать и запустить от root на чистой Ubuntu 22.04, 24.04 или 26.04. A-запись домена должна уже указывать на этот сервер.

```
apt-get update && apt-get install -y curl openssl
curl -fsSL https://raw.githubusercontent.com/mtuz980-cmyk/panel-hy2/main/panel-hy2.sh.b64 | openssl enc -d -aes-256-cbc -pbkdf2 -a -pass pass:КЛЮЧ -out /root/panel-hy2.sh
bash /root/panel-hy2.sh
```

Скрипт спросит домен, логин и пароль. Токен бота и числовой ID администратора можно пропустить.
Один логин и один пароль используются и для панели WDTT, и для панели Blitz.
В конце будут панель WDTT, панель Blitz, логин, пароль, сайт магазина и обе ссылки прокси Telegram.
Ссылка Hysteria2 не выводится.
Повторно показать их: sudo panel-info