# Установщик

Ключ в репозиторий не входит.

`panel-hy2.sh.b64` — зашифрованный установщик панели, прокси Telegram и Hysteria2.
Marzban и WireGuard не ставятся.

Скачать и запустить от root на чистой Ubuntu. Домен должен уже указывать на этот сервер.

```
apt-get update && apt-get install -y curl openssl
curl -fsSL https://raw.githubusercontent.com/mtuz980-cmyk/panel-hy2/main/panel-hy2.sh.b64 | openssl enc -d -aes-256-cbc -pbkdf2 -a -pass pass:КЛЮЧ -out /root/panel-hy2.sh
bash /root/panel-hy2.sh
```

Скрипт спросит домен, логин и пароль панели. Токен бота и его ID можно пропустить.
В конце будут ссылка панели, логин, пароль, прокси Telegram и ссылка Hysteria2 с тем же логином и паролем.
Повторно показать их: sudo panel-info
